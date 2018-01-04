---
title: IMetaDataEmit::DeletePinvokeMap-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DeletePinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1479c3fb19feec0e42ee4aec8544a35ce51350a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="bc5b9-102">IMetaDataEmit::DeletePinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="bc5b9-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="bc5b9-103">Zerstört die Zuordnungsmetadaten PInvoke für das Objekt, das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bc5b9-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc5b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc5b9-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc5b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bc5b9-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="bc5b9-106">[in] Ein `mdFieldDef` oder `mdMethodDef` Token, das das Objekt für das Löschen von PInvoke-Zuordnungsmetadaten darstellt.</span><span class="sxs-lookup"><span data-stu-id="bc5b9-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc5b9-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc5b9-107">Requirements</span></span>  
 <span data-ttu-id="bc5b9-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc5b9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc5b9-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bc5b9-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc5b9-110">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="bc5b9-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc5b9-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc5b9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc5b9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc5b9-112">See Also</span></span>  
 [<span data-ttu-id="bc5b9-113">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc5b9-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="bc5b9-114">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc5b9-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
