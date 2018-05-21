---
title: ICorDebugChain::GetThread-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 291c8129a790c235ee6e7f163c49c4e1e726cce5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="0e3ae-102">ICorDebugChain::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="0e3ae-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="0e3ae-103">Ruft den physischen Thread, den diese Aufrufkette wird Teil ab.</span><span class="sxs-lookup"><span data-stu-id="0e3ae-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e3ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e3ae-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e3ae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0e3ae-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="0e3ae-106">[out] Ein Zeiger auf ein ICorDebugThread-Objekt, das den physischen Thread darstellt, ist dieser Aufrufkette Teil.</span><span class="sxs-lookup"><span data-stu-id="0e3ae-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e3ae-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e3ae-107">Requirements</span></span>  
 <span data-ttu-id="0e3ae-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e3ae-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e3ae-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e3ae-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e3ae-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e3ae-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e3ae-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e3ae-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
