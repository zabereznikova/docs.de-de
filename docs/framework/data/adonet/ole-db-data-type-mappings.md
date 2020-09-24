---
title: OLE DB-Datentypzuordnungen
ms.date: 03/30/2017
ms.assetid: 04bcb259-59d3-4fd7-894d-4f0dd0c68069
ms.openlocfilehash: 7f3b498e39feac4a6fe98e739793d20e0268b8f4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150699"
---
# <a name="ole-db-data-type-mappings"></a>OLE DB-Datentypzuordnungen

In der folgenden Tabelle wird der .NET Framework Typ abgeleitet für Datentypen aus der .NET Framework Datenanbieter für ADO und OLE DB ( <xref:System.Data.OleDb> ) angezeigt. Die typisierten Accessormethoden für <xref:System.Data.OleDb.OleDbDataReader> werden ebenfalls aufgelistet.  
  
|ADO-Typ|OLE DB-Typ|.NET Framework-Typ|Typisierter .NET Framework-Accessor|  
|--------------|-----------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------|  
|adBigInt|DBTYPE_I8|Int64|GetInt64()|  
|adBinary|DBTYPE_BYTES|Byte[]|GetBytes()|  
|adBoolean|DBTYPE_BOOL|Boolean|GetBoolean()|  
|adBSTR|DBTYPE_BSTR|String|GetString()|  
|adChapter|DBTYPE_HCHAPTER|Unterstützt durch den `DataReader`. Weitere Informationen finden [Sie unter Abrufen von Daten mit einem DataReader](retrieving-data-using-a-datareader.md).|GetValue()|  
|adChar|DBTYPE_STR|String|GetString()|  
|adCurrency|DBTYPE_CY|Decimal|GetDecimal()|  
|adDate|DBTYPE_DATE|Datetime|GetDateTime()|  
|adDBDate|DBTYPE_DBDATE|Datetime|GetDateTime()|  
|adDBTime|DBTYPE_DBTIME|Datetime|GetDateTime()|  
|adDBTimeStamp|DBTYPE_DBTIMESTAMP|Datetime|GetDateTime()|  
|adDecimal|DBTYPE_DECIMAL|Decimal|GetDecimal()|  
|adDouble|DBTYPE_R8|Double|GetDouble()|  
|adError|DBTYPE_ERROR|ExternalException|GetValue()|  
|adFileTime|DBTYPE_FILETIME|Datetime|GetDateTime()|  
|adGUID|DBTYPE_GUID|Guid|GetGuid()|  
|adIDispatch|DBTYPE_IDISPATCH *|Object|GetValue()|  
|adInteger|DBTYPE_I4|Int32|GetInt32()|  
|adIUnknown|DBTYPE_IUNKNOWN *|Object|GetValue()|  
|adNumeric|DBTYPE_NUMERIC|Decimal|GetDecimal()|  
|adPropVariant|DBTYPE_PROPVARIANT|Object|GetValue()|  
|adSingle|DBTYPE_R4|Single|GetFloat()|  
|adSmallInt|DBTYPE_I2|Int16|GetInt16()|  
|adTinyInt|DBTYPE_I1|Byte|GetByte()|  
|adUnsignedBigInt|DBTYPE_UI8|UInt64|GetValue()|  
|adUnsignedInt|DBTYPE_UI4|UInt32|GetValue()|  
|adUnsignedSmallInt|DBTYPE_UI2|UInt16|GetValue()|  
|adUnsignedTinyInt|DBTYPE_UI1|Byte|GetByte()|  
|adVariant|DBTYPE_VARIANT|Object|GetValue()|  
|adWChar|DBTYPE_WSTR|String|GetString()|  
|adUserDefined|DBTYPE_UDT|Nicht unterstützt||  
|adVarNumeric|DBTYPE_VARNUMERIC|Nicht unterstützt||  
  
 \* Bei den OLE DB Typen `DBTYPE_IUNKNOWN` und `DBTYPE_IDISPATCH` ist der Objekt Verweis eine gemarshallte Darstellung des Zeigers.  
  
## <a name="see-also"></a>Weitere Informationen

- [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
