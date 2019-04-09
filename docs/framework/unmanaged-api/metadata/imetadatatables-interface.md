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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b2298e2d67e8a50e11d53d864f0e78f3b549e45
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131416"
---
# <a name="imetadatatables-interface"></a>IMetaDataTables-Schnittstelle
Stellt Methoden zum Speichern und Abrufen von Metadateninformationen in Tabellen bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetBlob-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Ruft einen Zeiger auf das binary large Object (BLOB) am Index angegebene Spalte ab.|  
|[GetBlobHeapSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Ruft die Größe des BLOB-Heap in Bytes ab.|  
|[GetCodedTokenInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Ruft einen Zeiger auf ein Array von Token mit dem angegebenen Zeilenindex verknüpft ist.|  
|[GetColumn-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Ruft einen Zeiger auf die Werte in der Spalte auf den angegebenen Spaltenindex in der Tabelle auf den Index der angegebenen Tabelle enthalten sind.|  
|[GetColumnInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Ruft Daten über die angegebene Spalte in der angegebenen Tabelle ab.|  
|[GetGuid-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Ruft eine GUID aus der Zeile am angegebenen Index ab.|  
|[GetGuidHeapSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Ruft die Größe in Bytes der GUID-Heap an.|  
|[GetNextBlob-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Ruft den Index des nächsten BLOBs in der Tabelle ab.|  
|[GetNextGuid-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Ruft den Index der nächsten GUID-Wert in der aktuellen Spalte ab.|  
|[GetNextString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Ruft den Index der nächsten Zeichenfolge in der aktuellen Spalte ab.|  
|[GetNextUserString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Ruft den Index der Zeile, die die nächste hartcodierten Zeichenfolge in der aktuellen Spalte enthält.|  
|[GetNumTables-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Ruft die Anzahl der Tabellen im Bereich des aktuellen `IMetaDataTables` Instanz.|  
|[GetRow-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Ruft die Zeile am angegebenen Zeilenindex, in der Tabelle auf den Index der angegebenen Tabelle.|  
|[GetString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Ruft die Zeichenfolge am angegebenen Index aus der Tabellenspalte in den Gültigkeitsbereich des aktuellen ab.|  
|[GetStringHeapSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Ruft die Größe in Bytes, der dem String-Heap an.|  
|[GetTableIndex-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Ruft den Index für die Tabelle, die durch das angegebene Token verwiesen wird.|  
|[GetTableInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Ruft Name, Größe, Anzahl der Zeilen, die Anzahl der Spalten und Schlüssel Spaltenindex der Tabelle vom Index angegebenen Tabelle ab.|  
|[GetUserString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Ruft die hartcodierten Zeichenfolge am angegebenen Index in die Zeichenfolgenspalte im aktuellen Bereich ab.|  
|[GetUserStringHeapSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Ruft die Größe in Bytes, der dem Benutzer String-Heap an.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
