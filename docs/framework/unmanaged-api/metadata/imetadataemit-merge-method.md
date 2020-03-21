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
ms.openlocfilehash: 759358822ed865c89f6f55084d1e7f6143506e93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175706"
---
# <a name="imetadataemitmerge-method"></a>IMetaDataEmit::Merge-Methode
Fügt den angegebenen importierten Bereich zur Liste der zusammenzuführenden Bereiche hinzu.  
  
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
 [in] Ein Zeiger auf ein [IMetaDataImport-Objekt,](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) das den importierten Bereich identifiziert, der zusammengeführt werden soll.  
  
 `pIMap`  
 [in] Ein Zeiger auf ein [IMapToken-Objekt,](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) das die Neuzuordnung des Tokens angibt.  
  
 `pHandler`  
 [in] Ein Zeiger auf ein [IUnknown-Objekt,](/cpp/atl/iunknown) das die Fehler angibt.  
  
## <a name="remarks"></a>Bemerkungen  
 Rufen Sie [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) auf, um die Zusammenführung von Metadaten in einen einzelnen Bereich auszulösen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
