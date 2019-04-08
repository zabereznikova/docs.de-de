---
title: Oracle-Datentypzuordnungen
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: c1fb3a6838e6a1b242255d4035c10ab0ec07d536
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104571"
---
# <a name="oracle-data-type-mappings"></a>Oracle-Datentypzuordnungen
In der folgenden Tabelle werden Oracle-Datentypen und ihre Zuordnungen zum <xref:System.Data.OracleClient.OracleDataReader> aufgelistet.  
  
|Oracle-Datentyp|Von OracleDataReader.GetValue zurückgegebener .NET Framework-Datentyp|Von OracleDataReader.GetOracleValue zurückgegebener OracleClient-Datentyp|Hinweise|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte[]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte[]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für die **Anzahl** -Datentyp, und dient, damit die <xref:System.Data.OracleClient.OracleDataReader> gibt eine **"System.Decimal"** oder <xref:System.Data.OracleClient.OracleNumber> anstelle eines Gleitkommawerts. Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**INTEGER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für die **NUMBER(38)** -Datentyp, und dient, damit die <xref:System.Data.OracleClient.OracleDataReader> gibt eine **"System.Decimal"** oder <xref:System.Data.OracleClient.OracleNumber> anstelle einer ganzen Zahl. Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVAL DAY TO SECOND**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleLob>||  
|**NUMBER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**NVARCHAR2**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Die Oracle **REF CURSOR** -Datentyp wird nicht unterstützt, indem die <xref:System.Data.OracleClient.OracleDataReader> Objekt.|  
|**ROWID**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**UNSIGNED INTEGER**|**Anzahl**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für die **NUMBER(38)** -Datentyp, und dient, damit die <xref:System.Data.OracleClient.OracleDataReader> gibt eine **"System.Decimal"** oder <xref:System.Data.OracleClient.OracleNumber> statt einen Ganzzahlwert ohne Vorzeichen. Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**VARCHAR2**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleString>||  
  
 Die folgende Tabelle enthält Oracle-Datentypen und die .NET Framework-Datentypen (**System.Data.DbType** und <xref:System.Data.OracleClient.OracleType>) zu verwenden, wenn sie als Parameter gebunden.  
  
|Oracle-Datentyp|DbType-Enumeration, die als Parameter gebunden werden soll|OracleType-Enumeration, die als Parameter gebunden werden soll|Hinweise|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFile**|Oracle kann nur eine **BFILE** als eine **BFILE** Parameter. Der .NET-Datenanbieter für Oracle wird nicht automatisch erstellt für Sie beim Binden von einer nicht -**BFILE** Wert, z. B. **Byte []** oder <xref:System.Data.OracleClient.OracleBinary>.|  
|**BLOB**||**Blob**|Oracle kann nur eine **BLOB** als eine **BLOB** Parameter. Der .NET-Datenanbieter für Oracle wird nicht automatisch erstellt für Sie beim Binden von einer nicht -**BLOB** Wert, z. B. **Byte []** oder <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**CLOB**|Oracle kann nur eine **CLOB** als eine **CLOB** Parameter. Der .NET-Datenanbieter für Oracle wird nicht automatisch erstellt für Sie beim Binden von einer nicht -**CLOB** Wert, z. B. **System.String** oder <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Bestimmt die **System.Data.DBType** und <xref:System.Data.OracleClient.OracleType>.|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Bestimmt die **System.Data.DBType** und <xref:System.Data.OracleClient.OracleType>.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn die Oracle 9i-Client und Server-Serversoftware verwenden.|  
|**INTERVAL DAY TO SECOND**|**Object**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn die Oracle 9i-Client und Server-Serversoftware verwenden.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binär**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle kann nur eine **NCLOB** als eine **NCLOB** Parameter. Der .NET-Datenanbieter für Oracle wird nicht automatisch erstellt für Sie beim Binden von einer nicht -**NCLOB** Wert, z. B. **System.String** oder <xref:System.Data.OracleClient.OracleString>.|  
|**NUMBER**|**VarNumeric**|**Anzahl**||  
|**NVARCHAR2**|**Zeichenfolge**|**NVarChar**||  
|**RAW**|**Binär**|**Raw**||  
|**REF CURSOR**||**Cursor**|Weitere Informationen finden Sie unter [Oracle-REF CURSORs](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**Rowid**||  
|**TIMESTAMP**|**DateTime**|**Zeitstempel**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn die Oracle 9i-Client und Server-Serversoftware verwenden.|  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn die Oracle 9i-Client und Server-Serversoftware verwenden.|  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn die Oracle 9i-Client und Server-Serversoftware verwenden.|  
|**UNSIGNED INTEGER**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Bestimmt die **System.Data.DBType** und <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 Die **InputOutput**, **Ausgabe**, und **ReturnValue** **ParameterDirection** Werte ein, die die <xref:System.Data.OracleClient.OracleParameter.Value%2A> Eigenschaft der <xref:System.Data.OracleClient.OracleParameter> Objekt sind .NET Framework-Datentypen, es sei denn, der Eingabewert mit dem Oracle-Datentyp ist (z. B. <xref:System.Data.OracleClient.OracleNumber> oder <xref:System.Data.OracleClient.OracleString>). Dies gilt nicht für **REF CURSOR**, **BFILE**, oder **LOB** -Datentypen.  
  
## <a name="see-also"></a>Siehe auch

- [Oracle und ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
