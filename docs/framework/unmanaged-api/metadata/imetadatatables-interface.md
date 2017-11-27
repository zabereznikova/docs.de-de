---
title: IMetaDataTables-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables
helpviewer_keywords: IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c89d615fbeeff4a60eb386d58c573ee7905f538d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatables-interface"></a>IMetaDataTables-Schnittstelle
Stellt Methoden zum Speichern und Abrufen von Metadateninformationen in Tabellen bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetBlob-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Ruft einen Zeiger auf das binary large Object (BLOB) am angegebenen Spaltenindex.|  
|[GetBlobHeapSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Ruft die Größe des BLOB-Heap in Bytes ab.|  
|[GetCodedTokenInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Ruft einen Zeiger auf ein Array von Token, die der Index der angegebenen Zeile zugeordnet.|  
|[GetColumn-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Ruft einen Zeiger auf die Werte in der Spalte an der angegebenen Spaltenindex in der Tabelle am angegebenen Index ab.|  
|[GetColumnInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Ruft Daten über die angegebene Spalte in der angegebenen Tabelle ab.|  
|[GetGuid-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Ruft eine GUID aus der Zeile am angegebenen Index ab.|  
|[GetGuidHeapSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Ruft die Größe in Bytes der GUID-Heap.|  
|[GetNextBlob-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Ruft den Index des nächsten BLOBs in der Tabelle ab.|  
|[GetNextGuid-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Ruft den Index des nächsten GUID-Wert in der aktuellen Spalte ab.|  
|[GetNextString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Ruft den Index der nächsten Zeichenfolge in der aktuellen Spalte ab.|  
|[GetNextUserString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Ruft den Index der Zeile, die die nächste hartcodierte Zeichenfolge in der aktuellen Spalte enthält.|  
|[GetNumTables-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Ruft die Anzahl der Tabellen im Bereich des aktuellen `IMetaDataTables` Instanz.|  
|[GetRow-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Ruft die Zeile im angegebenen Zeilenindex, in der Tabelle am angegebenen Index ab.|  
|[GetString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Ruft die Zeichenfolge am angegebenen Index aus der Tabellenspalte im aktuellen Verweisbereich.|  
|[GetStringHeapSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Ruft die Größe des dem String-Heap in Bytes ab.|  
|[GetTableIndex-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Ruft den Index für die Tabelle, die durch das angegebene Token verwiesen wird.|  
|[GetTableInfo-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Ruft den Namen, Zeilengröße, Anzahl der Zeilen, die Anzahl der Spalten und Schlüssel Spaltenindex der Tabelle am angegebenen Index ab.|  
|[GetUserString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Ruft die hartcodierte Zeichenfolge am angegebenen Index in der Zeichenfolgenspalte im aktuellen Bereich ab.|  
|[GetUserStringHeapSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Ruft die Größe des dem Benutzer String-Heap in Bytes ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
