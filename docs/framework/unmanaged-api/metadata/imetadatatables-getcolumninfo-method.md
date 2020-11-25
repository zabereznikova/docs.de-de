---
title: IMetaDataTables::GetColumnInfo-Methode
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
ms.openlocfilehash: 227d9ab67ab3091508232be3018ca520a6b5dcc6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711051"
---
# <a name="imetadatatablesgetcolumninfo-method"></a>IMetaDataTables::GetColumnInfo-Methode

Ruft Daten über die angegebene Spalte in der angegebenen Tabelle ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetColumnInfo (
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a>Parameter

=======

 `ixTbl`  
 in Der Index der gewünschten Tabelle.  
  
 `ixCol`  
 in Der Index der gewünschten Spalte.  
  
 `poCol`  
 vorgenommen Ein Zeiger auf den Offset der Spalte in der Zeile.  
  
 `pcbCol`  
 vorgenommen Ein Zeiger auf die Größe der Spalte in Bytes.  
  
 `pType`  
 vorgenommen Ein Zeiger auf den Typ der Werte in der Spalte.  
  
 `ppName`  
 vorgenommen Ein Zeiger auf einen Zeiger auf den Spaltennamen.  

## <a name="remarks"></a>Hinweise

Der zurückgegebene Spaltentyp liegt innerhalb eines Wertebereichs:

| pType                    | BESCHREIBUNG   | Hilfsfunktion                   |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0.. 63)   | Gesagt           | **Isridtype**<br>**Isridortoken** |
| `iCodedToken`..`iCodedTokenMax`<br>(64.. 95) | Codiertes Token | **Iscodeddekentype** <br>**Isridortoken** |
| `iSHORT` (96)            | Int16         | **Isfixedtype**                   |
| `iUSHORT` (97)           | UInt16        | **Isfixedtype**                   |
| `iLONG` (98)             | Int32         | **Isfixedtype**                   |
| `iULONG` (99)            | UInt32        | **Isfixedtype**                   |
| `iBYTE` (100)            | Byte          | **Isfixedtype**                   |
| `iSTRING` (101)          | String        | **Isheaptype**                    |
| `iGUID` (102)            | Guid          | **Isheaptype**                    |
| `iBLOB` (103)            | Blob          | **Isheaptype**                    |

Werte, die im *Heap* gespeichert sind (d. h. `IsHeapType == true` ), können mithilfe von gelesen werden:

- `iSTRING`: **IMetadataTables. GetString**
- `iGUID`: **IMetadataTables. GetGuid**
- `iBLOB`: **IMetadataTables. getBlob**

> [!IMPORTANT]
> Um die in der obigen Tabelle definierten Konstanten zu verwenden, schließen Sie die-Anweisung ein, `#define _DEFINE_META_DATA_META_CONSTANTS` die von der-Header Datei *Cor. h* bereitgestellt wird

## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataTables-Schnittstelle](imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](imetadatatables2-interface.md)
