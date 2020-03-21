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
ms.openlocfilehash: cc8aac32149fed952737d928e16a8f6efc448c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177119"
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
 [in] Der Index der gewünschten Tabelle.  
  
 `ixCol`  
 [in] Der Index der gewünschten Spalte.  
  
 `poCol`  
 [out] Ein Zeiger auf den Versatz der Spalte in der Zeile.  
  
 `pcbCol`  
 [out] Ein Zeiger auf die Größe der Spalte in Bytes.  
  
 `pType`  
 [out] Ein Zeiger auf den Typ der Werte in der Spalte.  
  
 `ppName`  
 [out] Ein Zeiger auf einen Zeiger auf den Spaltennamen.  

## <a name="remarks"></a>Bemerkungen

Der zurückgegebene Spaltentyp liegt innerhalb eines Wertebereichs:

| pType                    | Beschreibung   | Hilfsfunktion                   |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0..63)   | los           | **IsRidType**<br>**IsridorToken** |
| `iCodedToken`..`iCodedTokenMax`<br>(64..95) | Codiertes Token | **IsCodedTokenType** <br>**IsridorToken** |
| `iSHORT`(96)            | Int16         | **IsFixedType**                   |
| `iUSHORT`(97)           | UInt16        | **IsFixedType**                   |
| `iLONG`(98)             | Int32         | **IsFixedType**                   |
| `iULONG`(99)            | UInt32        | **IsFixedType**                   |
| `iBYTE`(100)            | Byte          | **IsFixedType**                   |
| `iSTRING`(101)          | String        | **IsHeapType**                    |
| `iGUID`(102)            | Guid          | **IsHeapType**                    |
| `iBLOB`(103)            | Blob          | **IsHeapType**                    |

Werte, die im Heap gespeichert `IsHeapType == true`sind (d. *h.,* ) können mit folgenden Werten gelesen werden:

- `iSTRING`: **IMetadataTables.GetString**
- `iGUID`: **IMetadataTables.GetGUID**
- `iBLOB`: **IMetadataTables.GetBlob**

> [!IMPORTANT]
> Um die in der obigen Tabelle definierten `#define _DEFINE_META_DATA_META_CONSTANTS` Konstanten zu verwenden, schließen Sie die Direktive ein, die von der *cor.h-Headerdatei* bereitgestellt wird.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataTables-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
