---
title: Oracle-Datentypzuordnungen
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: 71a85f82ea3535cf7aec8dd92fbda6726a36fb81
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166572"
---
# <a name="oracle-data-type-mappings"></a>Oracle-Datentypzuordnungen

In der folgenden Tabelle werden Oracle-Datentypen und ihre Zuordnungen zum <xref:System.Data.OracleClient.OracleDataReader> aufgelistet.  
  
|Oracle-Datentyp|Von OracleDataReader.GetValue zurückgegebener .NET Framework-Datentyp|Von OracleDataReader.GetOracleValue zurückgegebener OracleClient-Datentyp|Bemerkungen|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte []**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte []**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für den **Number** -Datentyp. er ist so konzipiert, dass <xref:System.Data.OracleClient.OracleDataReader> ein **System. Decimal** oder <xref:System.Data.OracleClient.OracleNumber> anstelle eines Gleit Komma Werts zurückgibt. Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**INTEGER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für den **Number (38)** -Datentyp und ist so konzipiert, dass <xref:System.Data.OracleClient.OracleDataReader> ein **System. Decimal** oder <xref:System.Data.OracleClient.OracleNumber> anstelle eines ganzzahligen Werts zurückgibt. Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVAL DAY TO SECOND**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte []**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**Einigen**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**Stoffes**|**Byte []**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Der Oracle **ref Cursor** -Datentyp wird vom-Objekt nicht unterstützt <xref:System.Data.OracleClient.OracleDataReader> .|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**Zeitstempel mit Zeitzone**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**Ganzzahl ohne Vorzeichen**|**Zahl**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für den **Number (38)** -Datentyp und ist so konzipiert, dass <xref:System.Data.OracleClient.OracleDataReader> ein **System. Decimal** oder anstelle eines ganz Zahl Werts ohne Vorzeichen zurückgibt <xref:System.Data.OracleClient.OracleNumber> . Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 In der folgenden Tabelle werden die Oracle-Datentypen und die .NET Framework Datentypen (**System. Data. DbType** und <xref:System.Data.OracleClient.OracleType> ) aufgelistet, die verwendet werden können, wenn Sie als Parameter gebunden werden.  
  
|Oracle-Datentyp|DbType-Enumeration, die als Parameter gebunden werden soll|OracleType-Enumeration, die als Parameter gebunden werden soll|Bemerkungen|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFILE**|Oracle ermöglicht nur das Binden einer **BFILE** als **BFILE** -Parameter. Der .NET-Datenanbieter für Oracle erstellt nicht automatisch eine für Sie, wenn Sie versuchen, einen anderen als einen**BFILE** -Wert (z. b. **Byte [] oder)** zu binden <xref:System.Data.OracleClient.OracleBinary> .|  
|**BLOB**||**Blob**|Oracle ermöglicht nur das Binden eines **BLOBs** als **BLOB** -Parameter. Der .NET-Datenanbieter für Oracle erstellt nicht automatisch eine für Sie, wenn Sie versuchen, einen nicht-**BLOB** -Wert wie z. b. **Byte []** oder zu binden <xref:System.Data.OracleClient.OracleBinary> .|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**CLOB**|Oracle ermöglicht nur das Binden eines **CLOB** als **CLOB** -Parameter. Der .NET-Datenanbieter für Oracle erstellt nicht automatisch einen für Sie, wenn Sie versuchen, einen nicht-**CLOB** -Wert wie z. b **. System. String** oder zu binden <xref:System.Data.OracleClient.OracleString> .|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> bestimmt den **System. Data. DbType** und <xref:System.Data.OracleClient.OracleType> .|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> bestimmt den **System. Data. DbType** und <xref:System.Data.OracleClient.OracleType> .|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**INTERVAL DAY TO SECOND**|**Object**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binär (Binary)**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NCHAR**||  
|**NCLOB**||**NCLOB**|Oracle ermöglicht nur das Binden eines **NCLOB** als **NCLOB** -Parameter. Der .NET-Datenanbieter für Oracle erstellt nicht automatisch einen für Sie, wenn Sie versuchen, einen nicht-**NCLOB** -Wert wie z. b **. System. String** oder zu binden <xref:System.Data.OracleClient.OracleString> .|  
|**Einigen**|**VarNumeric**|**Zahl**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**Stoffes**|**Binär (Binary)**|**Raw**||  
|**REF CURSOR**||**Cursor**|Weitere Informationen finden Sie unter [Oracle-REF Cursors](oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**ROWID**||  
|**TIMESTAMP**|**DateTime**|**Timestamp**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**Zeitstempel mit Zeitzone**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**Ganzzahl ohne Vorzeichen**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> bestimmt den **System. Data. DbType** und <xref:System.Data.OracleClient.OracleType> .|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 Der input **Output**-, **Output**-und **ReturnValue** - **ParameterDirection** -Wert, der von der-Eigenschaft des-Objekts verwendet wird <xref:System.Data.OracleClient.OracleParameter.Value%2A> <xref:System.Data.OracleClient.OracleParameter> , sind .NET Framework-Datentypen, es sei denn, der Eingabe Wert ist ein Oracle-Datentyp (z. b <xref:System.Data.OracleClient.OracleNumber> <xref:System.Data.OracleClient.OracleString> . oder). Dies gilt nicht für die Datentypen **ref Cursor**, **BFILE**oder **LOB** .  
  
## <a name="see-also"></a>Weitere Informationen

- [Oracle und ADO.NET](oracle-and-adonet.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
