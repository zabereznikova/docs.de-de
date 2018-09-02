---
title: OLE DB-Datentypzuordnungen
ms.date: 03/30/2017
ms.assetid: 04bcb259-59d3-4fd7-894d-4f0dd0c68069
ms.openlocfilehash: 2dbea33140e6cdd7370c1822d2bd6513917a31ea
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43457104"
---
# <a name="ole-db-data-type-mappings"></a>OLE DB-Datentypzuordnungen
In folgender Tabelle ist der abgeleitete [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typ für Datentypen vom .NET Framework-Datenanbieter für ADO und OLE DB (<xref:System.Data.OleDb>) dargestellt. Die typisierten Accessormethoden für den <xref:System.Data.OleDb.OleDbDataReader> sind ebenfalls aufgeführt.  
  
|ADO-Typ|OLE DB-Typ|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typ|Typisierter [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Accessor|  
|--------------|-----------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------|  
|adBigInt|DBTYPE_I8|Int64|GetInt64()|  
|adBinary|DBTYPE_BYTES|Byte[]|GetBytes()|  
|adBoolean|DBTYPE_BOOL|Boolean|GetBoolean()|  
|adBSTR|DBTYPE_BSTR|Zeichenfolge|GetString()|  
|adChapter|DBTYPE_HCHAPTER|Unterstützt durch den `DataReader`. Finden Sie unter [Abrufen von Daten, die mit "DataReader"](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).|GetValue()|  
|adChar|DBTYPE_STR|Zeichenfolge|GetString()|  
|adCurrency|DBTYPE_CY|Decimal|GetDecimal()|  
|adDate|DBTYPE_DATE|DateTime|GetDateTime()|  
|adDBDate|DBTYPE_DBDATE|DateTime|GetDateTime()|  
|adDBTime|DBTYPE_DBTIME|DateTime|GetDateTime()|  
|adDBTimeStamp|DBTYPE_DBTIMESTAMP|DateTime|GetDateTime()|  
|adDecimal|DBTYPE_DECIMAL|Decimal|GetDecimal()|  
|adDouble|DBTYPE_R8|Double|GetDouble()|  
|adError|DBTYPE_ERROR|ExternalException|GetValue()|  
|adFileTime|DBTYPE_FILETIME|DateTime|GetDateTime()|  
|adGUID|DBTYPE_GUID|Guid|GetGuid()|  
|adIDispatch|DBTYPE_IDISPATCH *|Objekt|GetValue()|  
|adInteger|DBTYPE_I4|Int32|GetInt32()|  
|adIUnknown|DBTYPE_IUNKNOWN *|Objekt|GetValue()|  
|adNumeric|DBTYPE_NUMERIC|Decimal|GetDecimal()|  
|adPropVariant|DBTYPE_PROPVARIANT|Objekt|GetValue()|  
|adSingle|DBTYPE_R4|Single|GetFloat()|  
|adSmallInt|DBTYPE_I2|Int16|GetInt16()|  
|adTinyInt|DBTYPE_I1|Byte|GetByte()|  
|adUnsignedBigInt|DBTYPE_UI8|UInt64|GetValue()|  
|adUnsignedInt|DBTYPE_UI4|UInt32|GetValue()|  
|adUnsignedSmallInt|DBTYPE_UI2|UInt16|GetValue()|  
|adUnsignedTinyInt|DBTYPE_UI1|Byte|GetByte()|  
|adVariant|DBTYPE_VARIANT|Objekt|GetValue()|  
|adWChar|DBTYPE_WSTR|Zeichenfolge|GetString()|  
|adUserDefined|DBTYPE_UDT|wird nicht unterstützt||  
|adVarNumeric|DBTYPE_VARNUMERIC|wird nicht unterstützt||  
  
 \* Für die OLE DB-Typen `DBTYPE_IUNKNOWN` und `DBTYPE_IDISPATCH`, der Objektverweis ist eine gemarshallte Darstellung des Zeigers.  
  
## <a name="see-also"></a>Siehe auch  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
