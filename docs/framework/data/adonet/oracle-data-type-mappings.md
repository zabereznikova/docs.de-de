---
title: Oracle-Datentypzuordnungen
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: be478741069e9edd406d73c0b75d5960b9909896
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783421"
---
# <a name="oracle-data-type-mappings"></a>Oracle-Datentypzuordnungen
In der folgenden Tabelle werden Oracle-Datentypen und ihre Zuordnungen zum <xref:System.Data.OracleClient.OracleDataReader> aufgelistet.  
  
|Oracle-Datentyp|Von OracleDataReader.GetValue zurückgegebener .NET Framework-Datentyp|Von OracleDataReader.GetOracleValue zurückgegebener OracleClient-Datentyp|Hinweise|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte[]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte[]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für den **Number** -Datentyp. er ist so konzipiert, <xref:System.Data.OracleClient.OracleDataReader> dass ein **System. Decimal** oder <xref:System.Data.OracleClient.OracleNumber> anstelle eines Gleit Komma Werts zurückgibt. Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**ZAH**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für den **Number (38)** -Datentyp und ist so konzipiert, dass <xref:System.Data.OracleClient.OracleDataReader> ein **System. Decimal** oder <xref:System.Data.OracleClient.OracleNumber> anstelle eines ganzzahligen Werts zurückgibt. Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**INTERVALL JAHR UND MONAT**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVALL (TAG BIS SEKUNDE)**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LANGE ROHDATEN**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**EINIGEN**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Der Oracle **ref Cursor** -Datentyp wird vom <xref:System.Data.OracleClient.OracleDataReader> -Objekt nicht unterstützt.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**ZEITSTEMPEL MIT LOKALER ZEITZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**ZEITSTEMPEL MIT ZEITZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**GANZZAHL OHNE VORZEICHEN**|**Zahl**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für den **Number (38)** -Datentyp und ist so konzipiert, dass <xref:System.Data.OracleClient.OracleDataReader> ein **System. Decimal** oder <xref:System.Data.OracleClient.OracleNumber> anstelle eines ganz Zahl Werts ohne Vorzeichen zurückgibt. Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 In der folgenden Tabelle werden die Oracle-Datentypen und die .NET Framework Datentypen (**System. Data. DbType** und <xref:System.Data.OracleClient.OracleType>) aufgelistet, die verwendet werden können, wenn Sie als Parameter gebunden werden.  
  
|Oracle-Datentyp|DbType-Enumeration, die als Parameter gebunden werden soll|OracleType-Enumeration, die als Parameter gebunden werden soll|Hinweise|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFILE**|Oracle ermöglicht nur das Binden einer **BFILE** als **BFILE** -Parameter. Der .NET-Datenanbieter für Oracle erstellt nicht automatisch eine für Sie, wenn Sie versuchen, einen anderen als einen**BFILE** -Wert (z. b. <xref:System.Data.OracleClient.OracleBinary> **Byte [] oder)** zu binden.|  
|**BLOB**||**Blob**|Oracle ermöglicht nur das Binden eines **BLOBs** als **BLOB** -Parameter. Der .NET-Datenanbieter für Oracle erstellt nicht automatisch eine für Sie, wenn Sie versuchen, einen nicht-**BLOB** -Wert wie z. b. **Byte []** oder <xref:System.Data.OracleClient.OracleBinary>zu binden.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**Clob**|Oracle ermöglicht nur das Binden eines **CLOB** als **CLOB** -Parameter. Der .NET-Datenanbieter für Oracle erstellt nicht automatisch einen für Sie, wenn Sie versuchen, einen nicht-**CLOB** -Wert wie z. b **. System. String** oder <xref:System.Data.OracleClient.OracleString>zu binden.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>bestimmt den **System. Data. DbType** und <xref:System.Data.OracleClient.OracleType>.|  
|**ZAH**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Zahl**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>bestimmt den **System. Data. DbType** und <xref:System.Data.OracleClient.OracleType>.|  
|**INTERVALL JAHR UND MONAT**|**Int32**|**Intervalyeartomonth**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**INTERVALL (TAG BIS SEKUNDE)**|**Objekt**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LANGE ROHDATEN**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle ermöglicht nur das Binden eines **NCLOB** als **NCLOB** -Parameter. Der .NET-Datenanbieter für Oracle erstellt nicht automatisch einen für Sie, wenn Sie versuchen, einen nicht-**NCLOB** -Wert wie z. b **. System. String** oder <xref:System.Data.OracleClient.OracleString>zu binden.|  
|**EINIGEN**|**VarNumeric**|**Zahl**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**RAW**|**Binary**|**Stoffes**||  
|**REF CURSOR**||**Hand**|Weitere Informationen finden Sie unter [Oracle-REF Cursors](oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**ROWID**||  
|**TIMESTAMP**|**DateTime**|**Zeitstempel**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**ZEITSTEMPEL MIT LOKALER ZEITZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**ZEITSTEMPEL MIT ZEITZONE**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**GANZZAHL OHNE VORZEICHEN**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, UInt32, Zahl**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>bestimmt den **System. Data. DbType** und <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 Der input **Output**-, **Output**-und **ReturnValue** - **ParameterDirection** -Wert, <xref:System.Data.OracleClient.OracleParameter.Value%2A> der von der <xref:System.Data.OracleClient.OracleParameter> -Eigenschaft des-Objekts verwendet wird, sind .NET Framework-Datentypen, es sei denn, der Eingabe Wert ist ein Oracle-Datentyp (für Beispiel, <xref:System.Data.OracleClient.OracleNumber> oder <xref:System.Data.OracleClient.OracleString>). Dies gilt nicht für die Datentypen **ref Cursor**, **BFILE**oder **LOB** .  
  
## <a name="see-also"></a>Siehe auch

- [Oracle und ADO.NET](oracle-and-adonet.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
