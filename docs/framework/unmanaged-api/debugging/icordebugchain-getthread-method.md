---
title: ICorDebugChain::GetThread-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 560f92eaed2d3482ca24d67810a3de6bc6f6fe31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="41382-102">ICorDebugChain::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="41382-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="41382-103">Ruft den physischen Thread, den diese Aufrufkette wird Teil ab.</span><span class="sxs-lookup"><span data-stu-id="41382-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41382-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41382-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41382-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="41382-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="41382-106">[out] Ein Zeiger auf ein ICorDebugThread-Objekt, das den physischen Thread darstellt, ist dieser Aufrufkette Teil.</span><span class="sxs-lookup"><span data-stu-id="41382-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41382-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41382-107">Requirements</span></span>  
 <span data-ttu-id="41382-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41382-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41382-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41382-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41382-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41382-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41382-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41382-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
