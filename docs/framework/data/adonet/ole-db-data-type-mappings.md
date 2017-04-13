---
title: "OLE DB-Datentypzuordnungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 04bcb259-59d3-4fd7-894d-4f0dd0c68069
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# OLE DB-Datentypzuordnungen
In folgender Tabelle ist der abgeleitete [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Typ für Datentypen vom .NET Framework\-Datenanbieter für ADO und OLE DB \(<xref:System.Data.OleDb>\) dargestellt.  Außerdem werden die typisierten Accessormethoden für den <xref:System.Data.OleDb.OleDbDataReader> aufgeführt.  
  
|ADO\-Typ|OLE DB\-Typ|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Typ|Typisierter [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Accessor|  
|--------------|-----------------|----------------------------------------------------------------------|---------------------------------------------------------------------------------------|  
|adBigInt|DBTYPE\_I8|Int64|GetInt64\(\)|  
|adBinary|DBTYPE\_BYTES|Byte\[\]|GetBytes\(\)|  
|adBoolean|DBTYPE\_BOOL|Boolean|GetBoolean\(\)|  
|adBSTR|DBTYPE\_BSTR|Zeichenfolge|GetString\(\)|  
|adChapter|DBTYPE\_HCHAPTER|Unterstützt durch den `DataReader`.  Siehe [Abrufen von Daten mit einem DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).|GetValue\(\)|  
|adChar|DBTYPE\_STR|Zeichenfolge|GetString\(\)|  
|adCurrency|DBTYPE\_CY|Decimal|GetDecimal\(\)|  
|adDate|DBTYPE\_DATE|DateTime|GetDateTime\(\)|  
|adDBDate|DBTYPE\_DBDATE|DateTime|GetDateTime\(\)|  
|adDBTime|DBTYPE\_DBTIME|DateTime|GetDateTime\(\)|  
|adDBTimeStamp|DBTYPE\_DBTIMESTAMP|DateTime|GetDateTime\(\)|  
|adDecimal|DBTYPE\_DECIMAL|Decimal|GetDecimal\(\)|  
|adDouble|DBTYPE\_R8|Double|GetDouble\(\)|  
|adError|DBTYPE\_ERROR|ExternalException|GetValue\(\)|  
|adFileTime|DBTYPE\_FILETIME|DateTime|GetDateTime\(\)|  
|adGUID|DBTYPE\_GUID|Guid|GetGuid\(\)|  
|adIDispatch|DBTYPE\_IDISPATCH \*|Objekt|GetValue\(\)|  
|adInteger|DBTYPE\_I4|Int32|GetInt32\(\)|  
|adIUnknown|DBTYPE\_IUNKNOWN \*|Objekt|GetValue\(\)|  
|adNumeric|DBTYPE\_NUMERIC|Decimal|GetDecimal\(\)|  
|adPropVariant|DBTYPE\_PROPVARIANT|Objekt|GetValue\(\)|  
|adSingle|DBTYPE\_R4|Single|GetFloat\(\)|  
|adSmallInt|DBTYPE\_I2|Int16|GetInt16\(\)|  
|adTinyInt|DBTYPE\_I1|Byte|GetByte\(\)|  
|adUnsignedBigInt|DBTYPE\_UI8|UInt64|GetValue\(\)|  
|adUnsignedInt|DBTYPE\_UI4|UInt32|GetValue\(\)|  
|adUnsignedSmallInt|DBTYPE\_UI2|UInt16|GetValue\(\)|  
|adUnsignedTinyInt|DBTYPE\_UI1|Byte|GetByte\(\)|  
|adVariant|DBTYPE\_VARIANT|Objekt|GetValue\(\)|  
|adWChar|DBTYPE\_WSTR|Zeichenfolge|GetString\(\)|  
|adUserDefined|DBTYPE\_UDT|wird nicht unterstützt||  
|adVarNumeric|DBTYPE\_VARNUMERIC|wird nicht unterstützt||  
  
 \* Bei den OLE DB\-Typen `DBTYPE_IUNKNOWN` und `DBTYPE_IDISPATCH` ist der Objektverweis eine gemarshallte Darstellung des Zeigers.  
  
## Siehe auch  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)