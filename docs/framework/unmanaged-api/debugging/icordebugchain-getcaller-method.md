---
title: ICorDebugChain::GetCaller-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d11693473dc4ed4438bbcad7f95c1b20adc1062b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744975"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="fd6bd-102">ICorDebugChain::GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="fd6bd-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="fd6bd-103">Ruft die Zertifikatskette, die dieser Kette aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fd6bd-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd6bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd6bd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd6bd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd6bd-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="fd6bd-106">[out] Ein Zeiger auf die Adresse des ICorDebugChain-Objekts, das die Aufrufkette darstellt.</span><span class="sxs-lookup"><span data-stu-id="fd6bd-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="fd6bd-107">Wenn diese Kette spontan aufgerufen wurde (wie der Fall wäre, wenn diese Kette oder der Debugger die Aufrufliste initialisiert), `ppChain` NULL.</span><span class="sxs-lookup"><span data-stu-id="fd6bd-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd6bd-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd6bd-108">Remarks</span></span>  
 <span data-ttu-id="fd6bd-109">Der Aufrufkette möglicherweise in einem anderen Thread aus, wenn der Aufruf über Threads hinweg gemarshallt wurde.</span><span class="sxs-lookup"><span data-stu-id="fd6bd-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd6bd-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd6bd-110">Requirements</span></span>  
 <span data-ttu-id="fd6bd-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd6bd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd6bd-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd6bd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd6bd-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd6bd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd6bd-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd6bd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
