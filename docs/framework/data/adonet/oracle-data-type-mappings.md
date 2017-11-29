---
title: Oracle Data Type Mappings1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 746013a11d10162a78116ff41d0b09d942f7651b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="oracle-data-type-mappings"></a>Oracle-Datentypzuordnungen
In der folgenden Tabelle werden Oracle-Datentypen und ihre Zuordnungen zum <xref:System.Data.OracleClient.OracleDataReader> aufgelistet.  
  
|Oracle-Datentyp|Von OracleDataReader.GetValue zurückgegebener .NET Framework-Datentyp|Von OracleDataReader.GetOracleValue zurückgegebener OracleClient-Datentyp|Hinweise|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für die **Anzahl** -Datentyp und dient, damit die <xref:System.Data.OracleClient.OracleDataReader> gibt eine **System.Decimal** oder <xref:System.Data.OracleClient.OracleNumber> anstelle eines Gleitkommawerts. Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**GANZE ZAHL**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für die **NUMBER(38)** -Datentyp und dient, damit die <xref:System.Data.OracleClient.OracleDataReader> gibt eine **System.Decimal** oder <xref:System.Data.OracleClient.OracleNumber> anstelle einer Ganzzahl. Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**INTERVALL JAHR, MONAT**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVALL TAG ZWEITEN**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**ANZAHL**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**ROHDATEN**|**Byte]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Die Oracle **REF CURSOR** -Datentyp wird nicht unterstützt, indem Sie die <xref:System.Data.OracleClient.OracleDataReader> Objekt.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**ZEITSTEMPEL**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**ZEITSTEMPEL MIT DER LOKALEN ZEITZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**ZEITSTEMPEL MIT ZEITZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**GANZE ZAHL OHNE VORZEICHEN**|**Zahl**|<xref:System.Data.OracleClient.OracleNumber>|Dieser Datentyp ist ein Alias für die **NUMBER(38)** -Datentyp und dient, damit die <xref:System.Data.OracleClient.OracleDataReader> gibt eine **System.Decimal** oder <xref:System.Data.OracleClient.OracleNumber> statt unsigned Integer-Wert. Die Verwendung des .NET Framework-Datentyps kann zu einem Überlauf führen.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 Die folgende Tabelle enthält Oracle-Datentypen und die .NET Framework-Datentypen (**System.Data.DbType** und <xref:System.Data.OracleClient.OracleType>) zu verwenden, wenn sie als Parameter gebunden.  
  
|Oracle-Datentyp|DbType-Enumeration, die als Parameter gebunden werden soll|OracleType-Enumeration, die als Parameter gebunden werden soll|Hinweise|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFile**|Oracle lässt nur die Bindung einer **BFILE** als eine **BFILE** Parameter. Der .NET-Datenanbieter für Oracle wird nicht automatisch erstellt für Sie, wenn Sie versuchen, einen nicht-binden**BFILE** Wert, z. B. **Byte []** oder <xref:System.Data.OracleClient.OracleBinary>.|  
|**BLOB**||**BLOB**|Oracle lässt nur die Bindung einer **BLOB** als eine **BLOB** Parameter. Der .NET-Datenanbieter für Oracle wird nicht automatisch erstellt für Sie, wenn Sie versuchen, einen nicht-binden**BLOB** Wert, z. B. **Byte []** oder <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**CLOB**|Oracle lässt nur die Bindung einer **CLOB** als eine **CLOB** Parameter. Der .NET-Datenanbieter für Oracle wird nicht automatisch erstellt für Sie, wenn Sie versuchen, einen nicht-binden**CLOB** Wert, z. B. **System.String** oder <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, Zahl**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Bestimmt die **System.Data.DBType** und <xref:System.Data.OracleClient.OracleType>.|  
|**GANZE ZAHL**|**SByte, Int16, Int32, Int64, Dezimal**|**SByte, Int16, Int32, Zahl**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Bestimmt die **System.Data.DBType** und <xref:System.Data.OracleClient.OracleType>.|  
|**INTERVALL JAHR, MONAT**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**INTERVALL TAG ZWEITEN**|**Objekt**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle lässt nur die Bindung einer **NCLOB** als eine **NCLOB** Parameter. Der .NET-Datenanbieter für Oracle wird nicht automatisch erstellt für Sie, wenn Sie versuchen, einen nicht-binden**NCLOB** Wert, z. B. **System.String** oder <xref:System.Data.OracleClient.OracleString>.|  
|**ANZAHL**|**VarNumeric**|**Zahl**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**ROHDATEN**|**Binary**|**Rohdaten**||  
|**REF CURSOR**||**Cursor**|Weitere Informationen finden Sie unter [Oracle-REF CURSORs](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**ROWID**||  
|**ZEITSTEMPEL**|**DateTime**|**Zeitstempel**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**ZEITSTEMPEL MIT DER LOKALEN ZEITZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**ZEITSTEMPEL MIT ZEITZONE**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> ist nur verfügbar, wenn sowohl die Oracle 9i-Client- als auch die Oracle 9i-Serversoftware verwendet wird.|  
|**GANZE ZAHL OHNE VORZEICHEN**|**Byte, UInt16, UInt32, UInt64, Dezimal**|**Byte, UInt16, Uint32, Zahl**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Bestimmt die **System.Data.DBType** und <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 Die **InputOutput**, **Ausgabe**, und **ReturnValue** **"ParameterDirection"** vom verwendeten Werten die <xref:System.Data.OracleClient.OracleParameter.Value%2A> Eigenschaft von der <xref:System.Data.OracleClient.OracleParameter> Objekt sind .NET Framework-Datentypen, es sei denn, der Eingabewert mit dem Oracle-Datentyp ist (z. B. <xref:System.Data.OracleClient.OracleNumber> oder <xref:System.Data.OracleClient.OracleString>). Dies gilt nicht für **REF CURSOR**, **BFILE**, oder **LOB** Datentypen.  
  
## <a name="see-also"></a>Siehe auch  
 [Oracle und ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
