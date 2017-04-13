---
title: "Oracle-Datentypzuordnungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Oracle-Datentypzuordnungen
In der folgenden Tabelle werden Oracle\-Datentypen und ihre Zuordnungen zum <xref:System.Data.OracleClient.OracleDataReader> aufgelistet.  
  
|Oracle\-Datentyp|Von OracleDataReader.GetValue zurückgegebener .NET Framework\-Datentyp|Von **OracleDataReader.GetOracleValue** zurückgegebener OracleClient\-Datentyp|Hinweise|  
|----------------------|----------------------------------------------------------------------------|------------------------------------------------------------------------------------|--------------|  
|**BFILE**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für den **NUMBER**\-Datentyp. Er ist so gestaltet, dass der <xref:System.Data.OracleClient.OracleDataReader> anstelle eines Gleitkommawerts **System.Decimal** oder <xref:System.Data.OracleClient.OracleNumber> zurückgibt.  Die Verwendung des .NET Framework\-Datentyps kann zu einem Überlauf führen.|  
|**INTEGER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für den **NUMBER \(38\)**\-Datentyp. Er ist so gestaltet, dass der <xref:System.Data.OracleClient.OracleDataReader> anstelle einer ganzen Zahl **System.Decimal** oder <xref:System.Data.OracleClient.OracleNumber> zurückgibt.  Die Verwendung des .NET Framework\-Datentyps kann zu einem Überlauf führen.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVAL DAY TO SECOND**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleLob>||  
|**NUMBER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Die Verwendung des .NET Framework\-Datentyps kann zu einem Überlauf führen.|  
|**NVARCHAR2**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Der Oracle\-**REF CURSOR**\-Datentyp wird vom <xref:System.Data.OracleClient.OracleDataReader>\-Objekt nicht unterstützt.|  
|**ROWID**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**UNSIGNED INTEGER**|**Nummer**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für den **NUMBER\(38\)**\-Datentyp. Er ist so gestaltet, dass der <xref:System.Data.OracleClient.OracleDataReader> anstelle einer ganzen Zahl ohne Vorzeichen **System.Decimal** oder <xref:System.Data.OracleClient.OracleNumber> zurückgibt.  Die Verwendung des .NET Framework\-Datentyps kann zu einem Überlauf führen.|  
|**VARCHAR2**|**Zeichenfolge**|<xref:System.Data.OracleClient.OracleString>||  
  
 In der folgenden Tabelle werden Oracle\-Datentypen und die .NET Framework\-Datentypen \(**System.Data.DbType** und <xref:System.Data.OracleClient.OracleType>\) aufgelistet, die verwendet werden können, wenn sie als Parameter gebunden werden.  
  
|Oracle\-Datentyp|DbType\-Enumeration, die als Parameter gebunden werden soll|OracleType\-Enumeration, die als Parameter gebunden werden soll|Hinweise|  
|----------------------|-----------------------------------------------------------------|---------------------------------------------------------------------|--------------|  
|**BFILE**||**BFile**|In Oracle kann ein **BFILE**\-Parameter nur als **BFILE**\-Parameter gebunden werden.  Der .NET\-Datenanbieter für Oracle erstellt einen solchen Parameter nicht automatisch für Sie, wenn Sie versuchen, einen anderen als einen **BFILE**\-Wert \(z. B. **byte\[\]** oder <xref:System.Data.OracleClient.OracleBinary>\) zu binden.|  
|**BLOB**||**Blob**|In Oracle kann ein **BLOB**\-Parameter nur als **BLOB**\-Parameter gebunden werden.  Der .NET\-Datenanbieter für Oracle erstellt einen solchen Parameter nicht automatisch für Sie, wenn Sie versuchen, einen anderen als einen **BLOB**\-Wert \(z. B. **byte\[\]** oder <xref:System.Data.OracleClient.OracleBinary>\) zu binden.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**CLOB**|In Oracle kann ein **CLOB**\-Parameter nur als **CLOB**\-Parameter gebunden werden.  Der .NET\-Datenanbieter für Oracle erstellt einen solchen Parameter nicht automatisch für Sie, wenn Sie versuchen, einen anderen als einen **CLOB**\-Wert \(z. B. **System.String** oder <xref:System.Data.OracleClient.OracleString>\) zu binden.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, Number**|[Size](frlrfSystemDataOracleClientOracleParameterClassSizeTopic) bestimmt den **System.Data.DBType** und den <xref:System.Data.OracleClient.OracleType>.|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|[Size](frlrfSystemDataOracleClientOracleParameterClassSizeTopic) bestimmt den **System.Data.DBType** und den <xref:System.Data.OracleClient.OracleType>.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i\-Client\- als auch die Oracle 9i\-Serversoftware verwendet wird.|  
|**INTERVAL DAY TO SECOND**|**Objekt**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i\-Client\- als auch die Oracle 9i\-Serversoftware verwendet wird.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binär**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|In Oracle kann ein **NBLOB**\-Parameter nur als **NBLOB**\-Parameter gebunden werden.  Der .NET\-Datenanbieter für Oracle erstellt einen solchen Parameter nicht automatisch für Sie, wenn Sie versuchen, einen anderen als einen **NCLOB**\-Wert \(z. B. **System.String** oder <xref:System.Data.OracleClient.OracleString>\) zu binden.|  
|**NUMBER**|**VarNumeric**|**Nummer**||  
|**NVARCHAR2**|**Zeichenfolge**|**NVarChar**||  
|**RAW**|**Binär**|**Raw**||  
|**REF CURSOR**||**Cursor**|Weitere Informationen finden Sie unter [Oracle\-REF CURSORs](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**Rowid**||  
|**TIMESTAMP**|**DateTime**|**Timestamp**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i\-Client\- als auch die Oracle 9i\-Serversoftware verwendet wird.|  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i\-Client\- als auch die Oracle 9i\-Serversoftware verwendet wird.|  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i\-Client\- als auch die Oracle 9i\-Serversoftware verwendet wird.|  
|**UNSIGNED INTEGER**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|[Size](frlrfSystemDataOracleClientOracleParameterClassSizeTopic) bestimmt den **System.Data.DBType** und den <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 Die **ParameterDirection**\-Werte **InputOutput**, **Output** und **ReturnValue**, die von der <xref:System.Data.OracleClient.OracleParameter.Value%2A>\-Eigenschaft des <xref:System.Data.OracleClient.OracleParameter>\-Objekts verwendet werden, sind .NET Framework\-Datentypen, es sei denn, der Eingabewert ist ein Oracle\-Datentyp \(wie <xref:System.Data.OracleClient.OracleNumber> oder <xref:System.Data.OracleClient.OracleString>\).  Dies gilt nicht für die Datentypen **REF CURSOR**, **BFILE** und **LOB**.  
  
## Siehe auch  
 [Oracle und ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)