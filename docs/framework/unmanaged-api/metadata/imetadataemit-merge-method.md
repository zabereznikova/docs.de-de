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
ms.openlocfilehash: e64d644b511f7c3249c48b9642bfd3163142af3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722010"
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
 in Ein Zeiger auf ein [IMetaDataImport](imetadataimport-interface.md) -Objekt, das den importierten Bereich identifiziert, der zusammengeführt werden soll.  
  
 `pIMap`  
 in Ein Zeiger auf ein [IMapToken](imaptoken-interface.md) -Objekt, das die erneute Zuordnung des Tokens angibt.  
  
 `pHandler`  
 in Ein Zeiger auf ein [IUnknown](/cpp/atl/iunknown) -Objekt, das die Fehler angibt.  
  
## <a name="remarks"></a>Hinweise  

 Aufrufen von [IMetaDataEmit:: MergeEnd](imetadataemit-mergeend-method.md) , um die Zusammenführung von Metadaten in einem einzelnen Bereich zu initiieren.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
