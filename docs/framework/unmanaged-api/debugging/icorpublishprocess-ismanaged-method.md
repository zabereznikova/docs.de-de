---
title: ICorPublishProcess::IsManaged-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.IsManaged
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21fdb09820acb6357fe1457d2f96c3319b3152a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="5f6a6-102">ICorPublishProcess::IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="5f6a6-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="5f6a6-103">Ruft einen Wert, der angibt, ob dies der Prozess verweist [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) wird durch verwalteten Code bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f6a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f6a6-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f6a6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f6a6-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="5f6a6-106">[out] Ein Zeiger auf einen booleschen Wert, der angibt, ob der Prozess verwalteten Code hat.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="5f6a6-107">Der Wert ist `true` weist der Prozess durch Code enthalten ist verwalteten, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f6a6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f6a6-108">Remarks</span></span>  
 <span data-ttu-id="5f6a6-109">Da die aktuelle Version des `ICorPublishProcess` ermöglicht den Zugriff nur für Prozesse, die durch Code verwalteten, `IsManaged` gibt immer `true`.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f6a6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f6a6-110">Requirements</span></span>  
 <span data-ttu-id="5f6a6-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f6a6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f6a6-112">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="5f6a6-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5f6a6-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f6a6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f6a6-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f6a6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f6a6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f6a6-115">See Also</span></span>  
 [<span data-ttu-id="5f6a6-116">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f6a6-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
