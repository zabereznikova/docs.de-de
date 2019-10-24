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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd67d9faafedf4fb92c69618d4464ebb2ce47dcc
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774257"
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

| pType                    | Beschreibung   | Hilfsfunktion                   |
|--------------------------|---------------|-----------------------------------|
| `0`.. `iRidMax`<br>(0.. 63)   | Gesagt           | **Isridtype**<br>**Isridortoken** |
| `iCodedToken`.. `iCodedTokenMax`<br>(64.. 95) | Codiertes Token | **Iscodeddekentype** <br>**Isridortoken** |
| `iSHORT` (96)            | Int16         | **Isfixedtype**                   |
| `iUSHORT` (97)           | UInt16        | **Isfixedtype**                   |
| `iLONG` (98)             | Int32         | **Isfixedtype**                   |
| `iULONG` (99)            | UInt32        | **Isfixedtype**                   |
| `iBYTE` (100)            | Byte          | **Isfixedtype**                   |
| `iSTRING` (101)          | Zeichenfolge        | **Isheaptype**                    |
| `iGUID` (102)            | GUID          | **Isheaptype**                    |
| `iBLOB` (103)            | Blob          | **Isheaptype**                    |

Werte, die im *Heap* gespeichert sind (d. h. `IsHeapType == true`), können mithilfe von gelesen werden:

- `iSTRING`: **IMetadataTables. GetString**
- `iGUID`: **IMetadataTables. GetGuid**
- `iBLOB`: **IMetadataTables. getBlob**

> [!IMPORTANT]
> Um die in der obigen Tabelle definierten Konstanten zu verwenden, schließen Sie die-Direktive `#define _DEFINE_META_DATA_META_CONSTANTS` ein, die von der *Cor. h* -Header Datei bereitgestellt wird

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataTables-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
