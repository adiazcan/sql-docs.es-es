---
title: Instrucciones SET (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SET
- SET_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- ISO SET statements
- queries [SQL Server], executing
- dates [SQL Server], SET statements
- time [SQL Server], SET statements
- SET statement, about SET statement
- SET statement
- statistical information [SQL Server], SET statements
- locking [SQL Server], SET statements
ms.assetid: f7e107f8-0fcf-408b-b30f-da2323eeb714
caps.latest.revision: 38
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: f0426730b33f0b70fda11a8cb07242a365d10fae
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="set-statements-transact-sql"></a>Instrucciones SET (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  El lenguaje de programación [!INCLUDE[tsql](../../includes/tsql-md.md)] ofrece varias instrucciones SET que cambian el tratamiento de información específica por parte de la sesión actual. Las instrucciones SET se agrupan en las categorías que figuran en la siguiente tabla.  
  
 Para obtener información acerca de cómo establecer variables locales con la instrucción SET, vea [establecer @local_variable &#40; Transact-SQL &#41; ](../../t-sql/language-elements/set-local-variable-transact-sql.md).  
  
|Categoría|Instrucciones|  
|--------------|----------------|  
|Instrucciones de fecha y hora|[SET DATEFIRST](../../t-sql/statements/set-datefirst-transact-sql.md)<br /><br /> [SET DATEFORMAT](../../t-sql/statements/set-dateformat-transact-sql.md)|  
|Instrucciones de bloqueo|[SET DEADLOCK_PRIORITY](../../t-sql/statements/set-deadlock-priority-transact-sql.md)<br /><br /> [SET LOCK_TIMEOUT](../../t-sql/statements/set-lock-timeout-transact-sql.md)|  
|Otras instrucciones|[SET CONCAT_NULL_YIELDS_NULL](../../t-sql/statements/set-concat-null-yields-null-transact-sql.md)<br /><br /> [SET CURSOR_CLOSE_ON_COMMIT](../../t-sql/statements/set-cursor-close-on-commit-transact-sql.md)<br /><br /> [SET FIPS_FLAGGER](../../t-sql/statements/set-fips-flagger-transact-sql.md)<br /><br /> [SET IDENTITY_INSERT](../../t-sql/statements/set-identity-insert-transact-sql.md)<br /><br /> [DEFINIR IDIOMA](../../t-sql/statements/set-language-transact-sql.md)<br /><br /> [DESPLAZAMIENTOS DE CONJUNTO](../../t-sql/statements/set-offsets-transact-sql.md)<br /><br /> [SET QUOTED_IDENTIFIER](../../t-sql/statements/set-quoted-identifier-transact-sql.md)|  
|Instrucciones de ejecución de consultas|[SET ARITHABORT](../../t-sql/statements/set-arithabort-transact-sql.md)<br /><br /> [SET ARITHIGNORE](../../t-sql/statements/set-arithignore-transact-sql.md)<br /><br /> [SET FMTONLY](../../t-sql/statements/set-fmtonly-transact-sql.md)<br /><br /> Nota:[!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]<br /><br /> [SET NOCOUNT](../../t-sql/statements/set-nocount-transact-sql.md)<br /><br /> [SET NOEXEC](../../t-sql/statements/set-noexec-transact-sql.md)<br /><br /> [SET NUMERIC_ROUNDABORT](../../t-sql/statements/set-numeric-roundabort-transact-sql.md)<br /><br /> [SET PARSEONLY](../../t-sql/statements/set-parseonly-transact-sql.md)<br /><br /> [SET QUERY_GOVERNOR_COST_LIMIT](../../t-sql/statements/set-query-governor-cost-limit-transact-sql.md)<br /><br /> [SET ROWCOUNT](../../t-sql/statements/set-rowcount-transact-sql.md)<br /><br /> [SET TEXTSIZE](../../t-sql/statements/set-textsize-transact-sql.md)|  
|Instrucciones de configuración de ISO|[SET ANSI_DEFAULTS](../../t-sql/statements/set-ansi-defaults-transact-sql.md)<br /><br /> [SET ANSI_NULL_DFLT_OFF](../../t-sql/statements/set-ansi-null-dflt-off-transact-sql.md)<br /><br /> [SET ANSI_NULL_DFLT_ON](../../t-sql/statements/set-ansi-null-dflt-on-transact-sql.md)<br /><br /> [SET ANSI_NULLS](../../t-sql/statements/set-ansi-nulls-transact-sql.md)<br /><br /> [SET ANSI_PADDING](../../t-sql/statements/set-ansi-padding-transact-sql.md)<br /><br /> [SET ANSI_WARNINGS](../../t-sql/statements/set-ansi-warnings-transact-sql.md)|  
|Instrucciones de estadísticas|[SET FORCEPLAN](../../t-sql/statements/set-forceplan-transact-sql.md)<br /><br /> [SET SHOWPLAN_ALL](../../t-sql/statements/set-showplan-all-transact-sql.md)<br /><br /> [SET SHOWPLAN_TEXT](../../t-sql/statements/set-showplan-text-transact-sql.md)<br /><br /> [SET SHOWPLAN_XML](../../t-sql/statements/set-showplan-xml-transact-sql.md)<br /><br /> [SET STATISTICS IO](../../t-sql/statements/set-statistics-io-transact-sql.md)<br /><br /> [SET STATISTICS XML](../../t-sql/statements/set-statistics-xml-transact-sql.md)<br /><br /> [SET STATISTICS PROFILE](../../t-sql/statements/set-statistics-profile-transact-sql.md)<br /><br /> [ESTABLECER TIEMPO DE ESTADÍSTICAS](../../t-sql/statements/set-statistics-time-transact-sql.md)|  
|Instrucciones de transacciones|[SET IMPLICIT_TRANSACTIONS](../../t-sql/statements/set-implicit-transactions-transact-sql.md)<br /><br /> [SET REMOTE_PROC_TRANSACTIONS](../../t-sql/statements/set-remote-proc-transactions-transact-sql.md)<br /><br /> [SET TRANSACTION ISOLATION LEVEL](../../t-sql/statements/set-transaction-isolation-level-transact-sql.md)<br /><br /> [SET XACT_ABORT](../../t-sql/statements/set-xact-abort-transact-sql.md)|  
  
## <a name="considerations-when-you-use-the-set-statements"></a>Consideraciones al utilizar las instrucciones SET  
  
-   Todas las instrucciones SET se implementan en tiempo de ejecución, salvo SET FIPS_FLAGGER, SET OFFSETS, SET PARSEONLY y SET QUOTED_IDENTIFIER. Estas instrucciones se implementan en tiempo de análisis.  
  
-   Si se ejecuta una instrucción SET en un procedimiento almacenado o desencadenador, el valor de la opción SET se restaura cuando el control vuelve del procedimiento almacenado o desencadenador. Además, si se especifica una instrucción SET en una cadena SQL dinámica que se ejecuta usando **sp_executesql** o EXECUTE, el valor de la opción SET se restaura cuando el control vuelve del lote especificado en la cadena SQL dinámica.  
  
-   Los procedimientos almacenados se ejecutan con las opciones de SET especificadas en tiempo de ejecución, excepto en el caso de SET ANSI_NULLS y SET QUOTED_IDENTIFIER. Los procedimientos almacenados que utilizan SET ANSI_NULLS o SET QUOTED_IDENTIFIER usan las opciones especificadas en el momento de crear el procedimiento almacenado. Si se usan dentro de un procedimiento almacenado, las opciones SET no tienen ningún efecto.  
  
-   El **opciones de usuario** de **sp_configure** permite la configuración del servidor y funciona a través de varias bases de datos. Además, esta opción se comporta como una instrucción SET explícita, pero con la diferencia de que tiene lugar en el momento de iniciar la sesión.  
  
-   Las opciones de base de datos establecidas con ALTER DATABASE solo son válidas en el nivel de base de datos y solo tienen efecto cuando se establecen explícitamente. Opciones de base de datos invalidar la configuración de opción de instancia que se han establecido con **sp_configure**.  
  
-   En cualquiera de las instrucciones SET con opciones ON y OFF, puede especificar ON u OFF para múltiples opciones de SET.  
  
    > [!NOTE]  
    >  Esto no se aplica a las opciones SET relacionadas con estadísticas.  
  
     Por ejemplo, `SET QUOTED_IDENTIFIER, ANSI_NULLS ON` establece QUOTED_IDENTIFIER y ANSI_NULLS en ON.  
  
-   Las opciones de las instrucciones SET anulan las opciones de base de datos equivalentes que se establecen mediante ALTER DATABASE. Por ejemplo, el valor especificado en una instrucción SET ANSI_NULLS anulará la opción de la base de datos de ANSI_NULLS. Además, algunas opciones de conexión se establecen ON automáticamente cuando un usuario se conecta a una base de datos según los valores efectivos mediante el uso anterior de la **opciones de usuario de sp_configure** configuración o los valores que se aplican a todos los ODBC y Conexiones de OLE/DB.  
  
-   Las instrucciones ALTER, CREATE y DROP DATABASE no respetan la opción SET LOCK_TIMEOUT.  
  
-   Cuando una instrucción SET global o abreviada, como SET ANSI_DEFAULTS, establece varias opciones, al ejecutar la instrucción SET abreviada se restablecen los valores anteriores de todas las opciones a las que afecta. Si una opción individual de SET afectada por una instrucción SET abreviada se establece explícitamente después de ejecutar la instrucción SET abreviada, la instrucción SET individual tiene precedencia sobre las opciones correspondientes de la instrucción abreviada.  
  
-   Al utilizar lotes, el lote establecido mediante la instrucción USE determina el contexto de la base de datos. Las consultas "ad hoc" y todas las demás instrucciones que se ejecuten fuera del procedimiento almacenado y que se encuentren en lotes heredan las opciones de base de datos y conexión establecidas mediante la instrucción USE.  
  
-   Las solicitudes MARS (conjuntos de resultados activos múltiples) comparten un estado global que contiene los valores de SET de la sesión más reciente. Al ejecutar una solicitud, se pueden modificar las opciones de SET. Los cambios son específicos al contexto de solicitud en el que se encuentran, y no afectan a otras solicitudes MARS simultáneas. No obstante, una vez ejecutada la solicitud, las nuevas opciones de SET se copian en el estado de sesión global. Las nuevas solicitudes que se ejecuten en la misma sesión después de este cambio utilizarán estas nuevas opciones de SET.  
  
-   Cuando se ejecuta un procedimiento almacenado desde un lote o desde otro procedimiento almacenado, la ejecución se realiza con las opciones establecidas en ese momento en la base de datos que contiene el procedimiento almacenado. Por ejemplo, cuando se almacenan procedimiento **db1.dbo.sp1** llama a procedimiento almacenado **db2.dbo.sp2**, procedimiento almacenado **sp1** se ejecuta en el nivel de compatibilidad actual configuración de base de datos **db1**y el procedimiento almacenado **sp2** se ejecuta en la configuración de nivel de compatibilidad actual de la base de datos **db2**.  
  
-   Cuando una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] hace referencia a objetos que residen en varias bases de datos, el contexto de la base de datos actual y el contexto de la conexión actual se aplican a la instrucción. En este caso, si la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] está en un lote, el contexto de conexión actual es la base de datos definida mediante la instrucción USE; si la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] está en un procedimiento almacenado, el contexto de conexión es la base de datos que contiene el procedimiento almacenado.  
  
-   Cuando se crean o manipulan índices en columnas calculadas o vistas indizadas, las opciones SET ARITHABORT, CONCAT_NULL_YIELDS_NULL, QUOTED_IDENTIFIER, ANSI_NULLS, ANSI_PADDING y ANSI_WARNINGS deben establecerse en ON. La opción NUMERIC_ROUNDABORT debe ser OFF.  
  
     Si alguna de estas opciones no tiene los valores exigidos, se producirá un error en las acciones INSERT, UPDATE, DELETE, DBCC CHECKDB y DBCC CHECKTABLE en las tablas o vistas indizadas con índices en las columnas calculadas. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generará un error indicando las opciones que no se han establecido correctamente. Además, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] procesará las instrucciones SELECT en estas tablas o vistas indizadas como si no existieran los índices en las columnas calculadas ni en las vistas.  
  
  