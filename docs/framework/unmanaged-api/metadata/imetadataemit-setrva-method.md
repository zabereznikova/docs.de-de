---
title: IMetaDataEmit::SetRVA-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1a9df30ae11b13c052c75b05b0850d9f4754620
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470093"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="842ad-102">IMetaDataEmit::SetRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="842ad-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="842ad-103">Legt fest, die relative virtuelle Adresse der angegebenen Methode.</span><span class="sxs-lookup"><span data-stu-id="842ad-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="842ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="842ad-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="842ad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="842ad-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="842ad-106">[in] Das Token für die Zielmethode oder die Implementierung der Methode.</span><span class="sxs-lookup"><span data-stu-id="842ad-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="842ad-107">[in] Die Adresse des Bereichs, Code oder Daten.</span><span class="sxs-lookup"><span data-stu-id="842ad-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="842ad-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="842ad-108">Requirements</span></span>  
 <span data-ttu-id="842ad-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="842ad-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="842ad-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="842ad-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="842ad-111">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="842ad-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="842ad-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="842ad-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="842ad-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="842ad-113">See also</span></span>
- [<span data-ttu-id="842ad-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="842ad-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="842ad-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="842ad-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
