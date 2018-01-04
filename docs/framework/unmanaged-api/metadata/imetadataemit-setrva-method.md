---
title: IMetaDataEmit::SetRVA-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetRVA
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a9ea1fe9afdb16f956ff8a0019a9bb607aa87f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="007e6-102">IMetaDataEmit::SetRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="007e6-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="007e6-103">Legt die relative virtuelle Adresse der angegebenen Methode fest.</span><span class="sxs-lookup"><span data-stu-id="007e6-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="007e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="007e6-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="007e6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="007e6-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="007e6-106">[in] Das Token für die Zielmethode oder die Implementierung der Methode.</span><span class="sxs-lookup"><span data-stu-id="007e6-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="007e6-107">[in] Die Adresse des Bereichs Code- oder Datenmenge.</span><span class="sxs-lookup"><span data-stu-id="007e6-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="007e6-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="007e6-108">Requirements</span></span>  
 <span data-ttu-id="007e6-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="007e6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="007e6-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="007e6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="007e6-111">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="007e6-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="007e6-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="007e6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="007e6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="007e6-113">See Also</span></span>  
 [<span data-ttu-id="007e6-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="007e6-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="007e6-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="007e6-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
