---
title: ICorDebugMDA::GetOSThreadId-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
ms.openlocfilehash: e9846234f8217b822860c2400a54a91a651a0a56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129815"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="667e6-102">ICorDebugMDA::GetOSThreadId-Methode</span><span class="sxs-lookup"><span data-stu-id="667e6-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="667e6-103">Ruft den Thread Bezeichner des Betriebssystems ab, auf dem der von [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) dargestellte Assistent für verwaltetes Debuggen (MDA) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="667e6-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="667e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="667e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="667e6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="667e6-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="667e6-106">vorgenommen Ein Zeiger auf den Thread Bezeichner des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="667e6-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="667e6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="667e6-107">Remarks</span></span>  
 <span data-ttu-id="667e6-108">Der Betriebssystem Thread wird anstelle eines ICorDebugThread verwendet, um Situationen zuzulassen, in denen ein MDA entweder in einem systemeigenen Thread oder in einem verwalteten Thread ausgelöst wird, der noch keinen verwalteten Code eingegeben hat.</span><span class="sxs-lookup"><span data-stu-id="667e6-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="667e6-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="667e6-109">Requirements</span></span>  
 <span data-ttu-id="667e6-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="667e6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="667e6-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="667e6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="667e6-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="667e6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="667e6-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="667e6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="667e6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="667e6-114">See also</span></span>

- [<span data-ttu-id="667e6-115">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="667e6-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="667e6-116">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="667e6-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
