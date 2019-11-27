---
title: IMetaDataEmit::Merge-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: 06894f238f9fda3111d5484bb1b2add183a5abb2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448055"
---
# <a name="imetadataemitmerge-method"></a>IMetaDataEmit::Merge-Methode
Fügt der Liste der zusammen zuführenden Bereiche den angegebenen importierten Bereich hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pImport`  
 in Ein Zeiger auf ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Objekt, das den importierten Bereich identifiziert, der zusammengeführt werden soll.  
  
 `pIMap`  
 in Ein Zeiger auf ein [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) -Objekt, das die erneute Zuordnung des Tokens angibt.  
  
 `pHandler`  
 in Ein Zeiger auf ein [IUnknown](/cpp/atl/iunknown) -Objekt, das die Fehler angibt.  
  
## <a name="remarks"></a>Hinweise  
 Aufrufen von [IMetaDataEmit:: MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) , um die Zusammenführung von Metadaten in einem einzelnen Bereich zu initiieren.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
