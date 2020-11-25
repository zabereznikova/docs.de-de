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
ms.openlocfilehash: 073e73f082416308b893974471e39cbf5243d01c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708854"
---
# <a name="imetadatatables-interface"></a>IMetaDataTables-Schnittstelle

Stellt Methoden zum Speichern und Abrufen von Metadateninformationen in Tabellen bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetBlob-Methode](imetadatatables-getblob-method.md)|Ruft einen Zeiger auf den Binary Large Object (BLOB) am angegebenen Spalten Index ab.|  
|[GetBlobHeapSize-Methode](imetadatatables-getblobheapsize-method.md)|Ruft die Größe des BLOB-Heaps in Bytes ab.|  
|[GetCodedTokenInfo-Methode](imetadatatables-getcodedtokeninfo-method.md)|Ruft einen Zeiger auf ein Array von Token ab, die dem angegebenen Zeilen Index zugeordnet sind.|  
|[GetColumn-Methode](imetadatatables-getcolumn-method.md)|Ruft einen Zeiger auf die Werte ab, die in der Spalte am angegebenen Spalten Index in der Tabelle am angegebenen Tabellenindex enthalten sind.|  
|[GetColumnInfo-Methode](imetadatatables-getcolumninfo-method.md)|Ruft Daten über die angegebene Spalte in der angegebenen Tabelle ab.|  
|[GetGuid-Methode](imetadatatables-getguid-method.md)|Ruft eine GUID aus der Zeile am angegebenen Index ab.|  
|[GetGuidHeapSize-Methode](imetadatatables-getguidheapsize-method.md)|Ruft die Größe des GUID-Heaps in Bytes ab.|  
|[GetNextBlob-Methode](imetadatatables-getnextblob-method.md)|Ruft den Index des nächsten BLOBs in der Tabelle ab.|  
|[GetNextGuid-Methode](imetadatatables-getnextguid-method.md)|Ruft den Index des nächsten GUID-Werts in der aktuellen Tabellenspalte ab.|  
|[GetNextString-Methode](imetadatatables-getnextstring-method.md)|Ruft den Index der nächsten Zeichenfolge in der aktuellen Tabellenspalte ab.|  
|[GetNextUserString-Methode](imetadatatables-getnextuserstring-method.md)|Ruft den Index der Zeile ab, die die nächste hart codierte Zeichenfolge in der aktuellen Tabellenspalte enthält.|  
|[GetNumTables-Methode](imetadatatables-getnumtables-method.md)|Ruft die Anzahl der Tabellen im Gültigkeitsbereich der aktuellen `IMetaDataTables` Instanz ab.|  
|[GetRow-Methode](imetadatatables-getrow-method.md)|Ruft die Zeile am angegebenen Zeilen Index in der Tabelle am angegebenen Tabellenindex ab.|  
|[GetString-Methode](imetadatatables-getstring-method.md)|Ruft die Zeichenfolge am angegebenen Index aus der Tabellenspalte im aktuellen Verweis Bereich ab.|  
|[GetStringHeapSize-Methode](imetadatatables-getstringheapsize-method.md)|Ruft die Größe des Zeichen folgen Heaps in Bytes ab.|  
|[GetTableIndex-Methode](imetadatatables-gettableindex-method.md)|Ruft den Index für die Tabelle ab, auf die durch das angegebene Token verwiesen wird.|  
|[GetTableInfo-Methode](imetadatatables-gettableinfo-method.md)|Ruft den Namen, die Zeilengröße, die Anzahl der Zeilen, die Anzahl der Spalten und den Schlüssel Spalten Index der Tabelle am angegebenen Tabellenindex ab.|  
|[GetUserString-Methode](imetadatatables-getuserstring-method.md)|Ruft die hart codierte Zeichenfolge am angegebenen Index in der Zeichen folgen Spalte im aktuellen Bereich ab.|  
|[GetUserStringHeapSize-Methode](imetadatatables-getuserstringheapsize-method.md)|Ruft die Größe des Benutzer Zeichen folgen Heaps in Bytes ab.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenschnittstellen](metadata-interfaces.md)
- [IMetaDataTables2-Schnittstelle](imetadatatables2-interface.md)
