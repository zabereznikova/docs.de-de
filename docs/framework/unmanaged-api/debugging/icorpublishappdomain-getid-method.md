---
title: ICorPublishAppDomain::GetID-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomain.GetID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfbde806f409f2639b2468e0ba962b1659d1ffc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="0b25d-102">ICorPublishAppDomain::GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="0b25d-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="0b25d-103">Ruft den eindeutigen Bezeichner für diese [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0b25d-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b25d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b25d-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b25d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b25d-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="0b25d-106">[out] Ein Zeiger auf den Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="0b25d-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b25d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b25d-107">Remarks</span></span>  
 <span data-ttu-id="0b25d-108">Der Bezeichner ist nur im Bereich des enthaltenden Prozesses eindeutig.</span><span class="sxs-lookup"><span data-stu-id="0b25d-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b25d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0b25d-109">Requirements</span></span>  
 <span data-ttu-id="0b25d-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b25d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b25d-111">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="0b25d-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0b25d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b25d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b25d-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b25d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b25d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b25d-114">See Also</span></span>  
 [<span data-ttu-id="0b25d-115">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b25d-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
