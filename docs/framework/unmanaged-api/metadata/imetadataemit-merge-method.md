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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 899f2ca5ef1b987687f5c065ad3e1965e142d103
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466112"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="e7053-102">IMetaDataEmit::Merge-Methode</span><span class="sxs-lookup"><span data-stu-id="e7053-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="e7053-103">Fügt im angegebenen importierten Bereich der Liste der Bereiche zusammengeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e7053-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7053-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7053-104">Syntax</span></span>  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7053-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7053-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="e7053-106">[in] Ein Zeiger auf ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Objekt, das den importierten Bereich zusammengeführt werden identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e7053-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="e7053-107">[in] Ein Zeiger auf ein [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) Objekt, das das token Berichtscode angibt.</span><span class="sxs-lookup"><span data-stu-id="e7053-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandleer`  
 <span data-ttu-id="e7053-108">[in] Ein Zeiger auf ein [IUnknown](/cpp/atl/iunknown) Objekt, das den Fehler angibt.</span><span class="sxs-lookup"><span data-stu-id="e7053-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7053-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7053-109">Remarks</span></span>  
 <span data-ttu-id="e7053-110">Rufen Sie [IMetaDataEmit:: MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) die Zusammenführung von Metadaten in einem einzelnen Bereich auslösen.</span><span class="sxs-lookup"><span data-stu-id="e7053-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7053-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7053-111">Requirements</span></span>  
 <span data-ttu-id="e7053-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7053-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7053-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e7053-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7053-114">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e7053-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7053-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7053-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7053-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7053-116">See Also</span></span>  
 [<span data-ttu-id="e7053-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7053-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="e7053-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7053-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
