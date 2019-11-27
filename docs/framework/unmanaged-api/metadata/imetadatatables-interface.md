---
title: IMetaDataTables-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
ms.openlocfilehash: 17305f2c088dd6f479da4c823d3db0fd50c0b3d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443219"
---
# <a name="imetadatatables-interface"></a>IMetaDataTables-Schnittstelle
Stellt Methoden zum Speichern und Abrufen von Metadateninformationen in Tabellen bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetBlob-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Ruft einen Zeiger auf den Binary Large Object (BLOB) am angegebenen Spalten Index ab.|  
|[GetBlobHeapSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Ruft die Größe des BLOB-Heaps in Bytes ab.|  
|[GetCodedTokenInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Ruft einen Zeiger auf ein Array von Token ab, die dem angegebenen Zeilen Index zugeordnet sind.|  
|[GetColumn-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Ruft einen Zeiger auf die Werte ab, die in der Spalte am angegebenen Spalten Index in der Tabelle am angegebenen Tabellenindex enthalten sind.|  
|[GetColumnInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Ruft Daten über die angegebene Spalte in der angegebenen Tabelle ab.|  
|[GetGuid-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Ruft eine GUID aus der Zeile am angegebenen Index ab.|  
|[GetGuidHeapSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Ruft die Größe des GUID-Heaps in Bytes ab.|  
|[GetNextBlob-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Ruft den Index des nächsten BLOBs in der Tabelle ab.|  
|[GetNextGuid-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Ruft den Index des nächsten GUID-Werts in der aktuellen Tabellenspalte ab.|  
|[GetNextString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Ruft den Index der nächsten Zeichenfolge in der aktuellen Tabellenspalte ab.|  
|[GetNextUserString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Ruft den Index der Zeile ab, die die nächste hart codierte Zeichenfolge in der aktuellen Tabellenspalte enthält.|  
|[GetNumTables-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Ruft die Anzahl der Tabellen im Gültigkeitsbereich der aktuellen `IMetaDataTables` Instanz ab.|  
|[GetRow-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Ruft die Zeile am angegebenen Zeilen Index in der Tabelle am angegebenen Tabellenindex ab.|  
|[GetString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Ruft die Zeichenfolge am angegebenen Index aus der Tabellenspalte im aktuellen Verweis Bereich ab.|  
|[GetStringHeapSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Ruft die Größe des Zeichen folgen Heaps in Bytes ab.|  
|[GetTableIndex-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Ruft den Index für die Tabelle ab, auf die durch das angegebene Token verwiesen wird.|  
|[GetTableInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Ruft den Namen, die Zeilengröße, die Anzahl der Zeilen, die Anzahl der Spalten und den Schlüssel Spalten Index der Tabelle am angegebenen Tabellenindex ab.|  
|[GetUserString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Ruft die hart codierte Zeichenfolge am angegebenen Index in der Zeichen folgen Spalte im aktuellen Bereich ab.|  
|[GetUserStringHeapSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Ruft die Größe des Benutzer Zeichen folgen Heaps in Bytes ab.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
