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
ms.openlocfilehash: fd65de77209f5a981c0a4c291f8573a61cf6335b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645278"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="c2a9a-102">ICorDebugChain::GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="c2a9a-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="c2a9a-103">Ruft die Zertifikatskette, die dieser Kette aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c2a9a-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a9a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2a9a-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2a9a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2a9a-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="c2a9a-106">[out] Ein Zeiger auf die Adresse des ICorDebugChain-Objekts, das die Aufrufkette darstellt.</span><span class="sxs-lookup"><span data-stu-id="c2a9a-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="c2a9a-107">Wenn diese Kette spontan aufgerufen wurde (wie der Fall wäre, wenn diese Kette oder der Debugger die Aufrufliste initialisiert), `ppChain` NULL.</span><span class="sxs-lookup"><span data-stu-id="c2a9a-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2a9a-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2a9a-108">Remarks</span></span>  
 <span data-ttu-id="c2a9a-109">Der Aufrufkette möglicherweise in einem anderen Thread aus, wenn der Aufruf über Threads hinweg gemarshallt wurde.</span><span class="sxs-lookup"><span data-stu-id="c2a9a-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a9a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2a9a-110">Requirements</span></span>  
 <span data-ttu-id="c2a9a-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2a9a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a9a-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2a9a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2a9a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2a9a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2a9a-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a9a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
