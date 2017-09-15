---
title: CHAR (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- char_TSQL
- char
dev_langs:
- TSQL
helpviewer_keywords:
- converting int ACSII code to character
- control characters
- tab
- ASCII conversions
- CHAR function
- carriage return
- inserting control characters
- characters [SQL Server], control
- line feed
- printing ASCII values
ms.assetid: 955afe94-539c-465d-af22-16ec45da432a
caps.latest.revision: 39
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: fc6b6100060c8af5b4e1a1a08b97ba515af699e5
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="char-transact-sql"></a>CHAR (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

Convierte un **int** código ASCII en un carácter.
  
![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Sintaxis  
  
```sql
CHAR ( integer_expression )  
```  
  
## <a name="arguments"></a>Argumentos  
*integer_expression*  
Entero entre 0 y 255. `NULL`se devuelve si la expresión de entero no está en este intervalo.
  
## <a name="return-types"></a>Tipos de valor devuelto
**Char (1)**
  
## <a name="remarks"></a>Comentarios  
`CHAR`puede utilizarse para insertar caracteres de control en cadenas de caracteres. En la siguiente tabla se muestran algunos caracteres de control utilizados con frecuencia.
  
|Carácter de control|Valor|  
|---|---|
|Pestaña|**Char (9)**|  
|Avance de línea|**Char (10)**|  
|Retorno de carro|**Char (13)**|  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-using-ascii-and-char-to-print-ascii-values-from-a-string"></a>A. Usar ASCII y CHAR para imprimir los valores ASCII de una cadena  
En el siguiente ejemplo se imprimen el valor y el carácter ASCII de cada carácter de la cadena `New Moon`.
  
```sql
SET TEXTSIZE 0;  
-- Create variables for the character string and for the current   
-- position in the string.  
DECLARE @position int, @string char(8);  
-- Initialize the current position and the string variables.  
SET @position = 1;  
SET @string = 'New Moon';  
WHILE @position <= DATALENGTH(@string)  
   BEGIN  
   SELECT ASCII(SUBSTRING(@string, @position, 1)),   
      CHAR(ASCII(SUBSTRING(@string, @position, 1)))  
   SET @position = @position + 1  
   END;  
GO  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
----------- -
78          N  
----------- -  
101         e  
----------- -  
119         w  
----------- -  
32  
----------- -  
77          M  
----------- -  
111         o  
----------- -  
111         o  
----------- - 
110         n  
```
  
### <a name="b-using-char-to-insert-a-control-character"></a>B. Usar CHAR para insertar un carácter de control  
En el siguiente ejemplo se utiliza `CHAR(13)` para imprimir el nombre y la dirección de correo electrónico en líneas independientes cuando los resultados se devuelven en texto. En este ejemplo se usa la base de datos [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].
  
```sql
SELECT p.FirstName + ' ' + p.LastName, + CHAR(13)  + pe.EmailAddress   
FROM Person.Person p JOIN Person.EmailAddress pe  
ON p.BusinessEntityID = pe.BusinessEntityID  
AND p.BusinessEntityID = 1;  
GO  
```sql
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
`Ken Sanchez`
  
`ken0@adventure-works.com`
  
`(1 row(s) affected)`
  
## Examples: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] and [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### C. Using ASCII and CHAR to print ASCII values from a string  
The following example assumes an ASCII character set and returns the character value for 6 ASCII character numbers.
  
```sql
SELECT CHAR(65) AS [65], CHAR(66) AS [66],   
CHAR(97) AS [97], CHAR(98) AS [98],   
CHAR(49) AS [49], CHAR(50) AS [50];  
```
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
65   66   97   98   49   50  
---- ---- ---- ---- ---- ----  
A    B    a    b    1    2  
```
  
### <a name="d-using-char-to-insert-a-control-character"></a>D. Usar CHAR para insertar un carácter de control  
En el ejemplo siguiente se utiliza `CHAR(13)` para devolver información acerca de las bases de datos en líneas independientes cuando los resultados se devuelven en texto.
  
```sql
SELECT name, 'was created on ', create_date, CHAR(13), name, 'is currently ', state_desc   
FROM sys.databases;  
GO  
```
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
name     create_date    name    state_desc  
------------------------------------------------------------  
master                   was created on  2003-04-08 09:13:36.390   
master                   is currently  ONLINE  
tempdb                   was created on  2014-01-10 17:24:24.023   
tempdb                   is currently  ONLINE  
AdventureWorksPDW2012    was created on  2014-05-07 09:05:07.083 
AdventureWorksPDW2012    is currently  ONLINE  
```
  
## <a name="see-also"></a>Vea también
[+ &#40; Concatenación de cadenas &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/string-concatenation-transact-sql.md)  
[Funciones de cadena &#40; Transact-SQL &#41;](../../t-sql/functions/string-functions-transact-sql.md)
  
  

