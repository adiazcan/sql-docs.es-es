---
title: Instalar modelos de aprendizaje automático entrenado previamente en SQL Server | Microsoft Docs
description: Agregar modelos previamente entrenados para características de imagen y el análisis de opinión a SQL Server 2017 Machine Learning Services (R o Python) o SQL Server 2016 R Services.
ms.prod: sql
ms.technology: machine-learning
ms.date: 07/18/2018
ms.topic: conceptual
author: HeidiSteen
ms.author: heidist
manager: cgronlun
ms.openlocfilehash: b2dfee04a7c0c9c39b7969551a85a49d441f30e5
ms.sourcegitcommit: 84cc5ed00833279da3adbde9cb6133a4e788ed3f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2018
ms.locfileid: "39216836"
---
# <a name="install-pre-trained-machine-learning-models-on-sql-server"></a>Instalar previamente entrenado modelos de machine learning en SQL Server
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

En este artículo se explica cómo usar Powershell para agregar la máquina entrenada gratis para los modelos de aprendizaje *análisis de opiniones* y *imagen características* a una instancia del motor de base de datos de SQL Server con R o Python integración. Los modelos previamente entrenados se generan por Microsoft y listos para usar, agregar a una instancia del motor de base de datos como una tarea posterior a la instalación. Para obtener más información acerca de estos modelos, vea el [recursos](#bkmk_resources) sección de este artículo.

Una vez instalado, los modelos previamente entrenados se consideran un detalle de implementación que impulsan funciones específicas en las bibliotecas de microsoftml (Python) y MicrosoftML (R). No debería (y no) ver, personalizar o volver a entrenar los modelos, ni puede se trate como un recurso independiente en el código personalizado o emparejados otras funciones. 

Para utilizar los modelos previamente entrenados, llame a las funciones enumeradas en la tabla siguiente.

| Función de R (MicrosoftML) | Función de Python (microsoftml) | Uso |
|--------------------------|-------------------------------|-------|
| [getSentiment](https://docs.microsoft.com/machine-learning-server/r-reference/microsoftml/getsentiment) | [get_sentiment](https://docs.microsoft.com//machine-learning-server/python-reference/microsoftml/get-sentiment) | Genera la puntuación de opiniones positivas y negativas en las entradas de texto. [Obtenga más información](https://blogs.msdn.microsoft.com/sqlserverstorageengine/2017/11/01/sentiment-analysis-with-python-in-sql-server-machine-learning-services/).|
| [featurizeImage](https://docs.microsoft.com/machine-learning-server/r-reference/microsoftml/featurizeimage) | [featurize_image](https://docs.microsoft.com/machine-learning-server/python-reference/microsoftml/featurize-image) | Extrae información de texto de las entradas del archivo de imagen. [Obtenga más información](https://blogs.msdn.microsoft.com/mlserver/2017/04/12/image-featurization-with-a-pre-trained-deep-neural-network-model/). |

## <a name="prerequisites"></a>Requisitos previos

Algoritmos de aprendizaje automático son intensivos. Se recomienda 16 GB de RAM para cargas de trabajo de baja a moderada, incluida la finalización de los tutoriales de tutorial con todos los datos de ejemplo.

Debe tener derechos de administrador en el equipo y SQL Server para agregar modelos previamente entrenados.

Scripts externos deben estar habilitados y el servicio LaunchPad de SQL Server debe estar ejecutándose. Instrucciones de instalación proporcionan los pasos para habilitar y comprobar estas funcionalidades. 

[Paquete MicrosoftML R](https://docs.microsoft.com/machine-learning-server/r-reference/microsoftml/microsoftml-package) o [paquete de Python microsoftml](https://docs.microsoft.com/machine-learning-server/python-reference/microsoftml/microsoftml-package) contienen los modelos previamente entrenados.

+ [SQL Server 2017 Machine Learning Services](sql-machine-learning-services-windows-install.md) incluye ambas versiones de idioma de la biblioteca de aprendizaje automático, por lo que se cumple este requisito previo con ninguna otra acción por parte del usuario. Dado que las bibliotecas están presentes, puede usar el script de PowerShell descrito en este artículo para agregar los modelos previamente entrenados para estas bibliotecas.

+ [SQL Server 2016 R Services](sql-r-services-windows-install.md), que es solo, R no incluye [paquete MicrosoftML](https://docs.microsoft.com/machine-learning-server/r-reference/microsoftml/microsoftml-package) de fábrica. Para agregar MicrosoftML, que debe hacer una [actualización del componente](../r/use-sqlbindr-exe-to-upgrade-an-instance-of-sql-server.md). Una ventaja de la actualización del componente es que al mismo tiempo puede agregar que los modelos previamente entrenados, lo que hace que se ejecuta el script de PowerShell innecesario. Sin embargo, si ya actualizado, pero se perdió la adición de los modelos previamente entrenados la primera vez, puede ejecutar el script de PowerShell como se describe en este artículo. Funciona en ambas versiones de SQL Server. Antes de realizar, confirme que existe la biblioteca de MicrosoftML en C:\Program Files\Microsoft SQL Server\MSSQL13. MSSQLSERVER\R_SERVICES\library.


<a name="file-location"></a>

## <a name="check-whether-pre-trained-models-are-installed"></a>Compruebe si están instalados los modelos previamente entrenados

Las rutas de acceso de instalación para los modelos de R y Python son los siguientes:

+ R: `C:\Program Files\Microsoft SQL Server\MSSQL14.MSSQLSERVER\R_SERVICES\library\MicrosoftML\mxLibs\x64`

+ Para Python: `C:\Program Files\Microsoft SQL Server\MSSQL14.MSSQLSERVER\PYTHON_SERVICES\Lib\site-packages\microsoftml\mxLibs `

Los nombres de archivo de modelo se enumeran a continuación:

+ AlexNet\_Updated.model
+ ImageNet1K\_mean.xml
+ pretrained.Model
+ ResNet\_101\_Updated.model
+ ResNet\_18\_Updated.model
+ ResNet\_50\_Updated.model

Si los modelos ya están instalados, vaya a la [paso de validación](#verify) para confirmar la disponibilidad.

## <a name="download-the-installation-script"></a>Descargue el script de instalación

Haga clic en [ https://aka.ms/mlm4sql ](https://aka.ms/mlm4sql) para descargar el archivo **Install MLModels.ps1**.

## <a name="execute-with-elevated-privileges"></a>Ejecutar con privilegios elevados

1. Inicie PowerShell. En la barra de tareas, haga clic en el icono de programa de PowerShell y seleccione **ejecutar como administrador**.
2. Escriba una ruta de acceso completa al archivo de script de instalación e incluyen el nombre de instancia. Suponiendo que la carpeta descargas y una instancia predeterminada, el comando sería similar al siguiente:

   ```powershell
   PS C:\WINDOWS\system32> C:\Users\<user-name>\Downloads\Install-MLModels.ps1 MSSQLSERVER
   ```

**Salida**

En una conectada a internet aprendizaje automático de SQL Server 2017 instancia predeterminada con R y Python, verá mensajes similares al siguiente.

   ```powershell
   MSSQL14.MSSQLSERVER
        Verifying R models [9.2.0.24]
        Downloading R models [C:\Users\<user-name>\AppData\Local\Temp]
        Installing R models [C:\Program Files\Microsoft SQL Server\MSSQL14.MSSQLSERVER\R_SERVICES\]
        Verifying Python models [9.2.0.24]
        Installing Python models [C:\Program Files\Microsoft SQL Server\MSSQL14.MSSQLSERVER\PYTHON_SERVICES\]
   PS C:\WINDOWS\system32>
   ```

<a name="verify"> </a>

## <a name="verify-installation"></a>Comprobar la instalación

En primer lugar, busque los nuevos archivos en el [mxlibs carpeta](#file-location). A continuación, ejecute el código de demostración para confirmar que los modelos están instalados y funcionales. 

### <a name="r-verification-steps"></a>Pasos de comprobación de R

1. Iniciar **RGUI. EXE** en C:\Program Files\Microsoft SQL Server\MSSQL14. MSSQLSERVER\R_SERVICES\bin\x64.

2. Pegue el siguiente script de R en el símbolo del sistema.

    ```r
    # Create the data
    CustomerReviews <- data.frame(Review = c(
    "I really did not like the taste of it",
    "It was surprisingly quite good!",
    "I will never ever ever go to that place again!!"),
    stringsAsFactors = FALSE)

    # Get the sentiment scores
    sentimentScores <- rxFeaturize(data = CustomerReviews, 
                                    mlTransforms = getSentiment(vars = list(SentimentScore = "Review")))

    # Let's translate the score to something more meaningful
    sentimentScores$PredictedRating <- ifelse(sentimentScores$SentimentScore > 0.6, 
                                            "AWESOMENESS", "BLAH")

    # Let's look at the results
    sentimentScores
    ```

3. Presione ENTRAR para ver las puntuaciones de opinión. Salida debería ser como sigue:

    ```
    > sentimentScores
                                            Review SentimentScore
    1           I really did not like the taste of it      0.4617899
    2                 It was surprisingly quite good!      0.9601924
    3 I will never ever ever go to that place again!!      0.3103435
    PredictedRating
    1            BLAH
    2     AWESOMENESS
    3            BLAH
    ```

### <a name="python-verification-steps"></a>Pasos de comprobación de Python

1. Iniciar **Python.exe** en C:\Program Files\Microsoft SQL Server\MSSQL14. MSSQLSERVER\PYTHON_SERVICES.

2. Pegue el siguiente script de Python en el símbolo del sistema

    ```python
    import numpy
    import pandas
    from microsoftml import rx_logistic_regression, rx_featurize, rx_predict, get_sentiment

    # Create the data
    customer_reviews = pandas.DataFrame(data=dict(review=[
                "I really did not like the taste of it",
                "It was surprisingly quite good!",
                "I will never ever ever go to that place again!!"]))
                
    # Get the sentiment scores
    sentiment_scores = rx_featurize(
        data=customer_reviews,
        ml_transforms=[get_sentiment(cols=dict(scores="review"))])
        
    # Let's translate the score to something more meaningful
    sentiment_scores["eval"] = sentiment_scores.scores.apply(
                lambda score: "AWESOMENESS" if score > 0.6 else "BLAH")
    print(sentiment_scores)
    ```

3. Presione ENTRAR para imprimir las puntuaciones. Salida debería ser como sigue:

    ```
    >>> print(sentiment_scores)
                                                review    scores         eval
    0            I really did not like the taste of it  0.461790         BLAH
    1                  It was surprisingly quite good!  0.960192  AWESOMENESS
    2  I will never ever ever go to that place again!!  0.310344         BLAH
    >>>
    ```

> [!NOTE]
> Si se producen errores de scripts de demostración, compruebe primero la ubicación del archivo. En sistemas que tiene varias instancias de SQL Server o para las instancias que se ejecutan en paralelo con versiones independientes, es posible que el script de instalación leer el entorno de mal y coloque los archivos en una ubicación incorrecta. Por lo general, copiar manualmente los archivos a la carpeta correcta mxlib corrige el problema.

## <a name="examples-using-pre-trained-models"></a>Ejemplos de uso de modelos previamente entrenados

Los siguientes vínculos incluyen código de ejemplo y tutoriales de invocación de los modelos previamente entrenados.

+ [Análisis de sentimiento con Python en SQL Server Machine Learning Services](https://blogs.msdn.microsoft.com/sqlserverstorageengine/2017/11/01/sentiment-analysis-with-python-in-sql-server-machine-learning-services/)

+ [Características de la imagen con un modelo de red neuronal profunda previamente entrenado](https://blogs.msdn.microsoft.com/mlserver/2017/04/12/image-featurization-with-a-pre-trained-deep-neural-network-model/)

  El modelo previamente entrenado para las imágenes es compatible con características de las imágenes que suministre. Para usar el modelo, llame a la **featurizeImage** transformar. Se carga la imagen, el tamaño y caracterizar el modelo entrenado. La salida de la caracterizador de DNN, a continuación, se usa para entrenar un modelo lineal para la clasificación de imágenes. Para usar este modelo, todas las imágenes deben cambiarse para cumplir los requisitos del modelo entrenado. Por ejemplo, si usa un modelo AlexNet, la imagen debe ajustarse 227 x 227 px.

+ [Ejemplo de código: análisis de sentimiento mediante Caracterizador de texto](https://github.com/Microsoft/microsoft-r/tree/master/microsoft-ml/Samples/101/BinaryClassification/SimpleSentimentAnalysis)

<a name="bkmk_resources"></a> 

## <a name="research-and-resources"></a>Investigación y recursos

Actualmente, los modelos que están disponibles son los modelos de red neuronal profunda (DNN) para la imagen y el análisis de opiniones. Todos los modelos previamente entrenados se entrenan mediante el uso de Microsoft [Kit de herramientas de cálculo red](https://cntk.ai/Features/Index.html), o **CNTK**.

La configuración de cada red se basaba en las implementaciones de referencia siguientes:

+ ResNet-18
+ ResNet-50
+ ResNet-101
+ AlexNet

Para obtener más información acerca de los algoritmos utilizados en estos modelos de aprendizaje profundo y cómo se implementan y se entrena con CNTK, consulte estos artículos:

+ [Algoritmo los investigadores de Microsoft establece ImageNet desafío hito](https://www.microsoft.com/research/blog/microsoft-researchers-algorithm-sets-imagenet-challenge-milestone/)

+ [Kit de herramientas de cálculo red Microsoft ofrece un rendimiento informático de aprendizaje más eficaz profundo distribuido](https://www.microsoft.com/research/blog/microsoft-computational-network-toolkit-offers-most-efficient-distributed-deep-learning-computational-performance/)

## <a name="see-also"></a>Vea también

+ [SQL Server 2016 R Services](sql-r-services-windows-install.md)
+ [SQL Server 2017 Machine Learning Services](sql-machine-learning-services-windows-install.md)
+ [Actualizar los componentes de R y Python en instancias de SQL Server](../r/use-sqlbindr-exe-to-upgrade-an-instance-of-sql-server.md)
+ [Paquete MicrosoftML para R](https://docs.microsoft.com/machine-learning-server/r-reference/microsoftml/microsoftml-package)
+ [paquete microsoftml para Python](https://docs.microsoft.com/machine-learning-server/python-reference/microsoftml/microsoftml-package)
