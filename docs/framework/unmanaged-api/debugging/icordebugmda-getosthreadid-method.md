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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c38aa9cc891514a7f37dba47402c168060ec3727
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486094"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="120ba-102">ICorDebugMDA::GetOSThreadId-Methode</span><span class="sxs-lookup"><span data-stu-id="120ba-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="120ba-103">Ruft die Betriebssystem (OS) Thread-ID, die auf dem der Assistent für verwaltete Debuggen (MDA) durch dargestellt ab [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="120ba-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="120ba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="120ba-104">Syntax</span></span>  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="120ba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="120ba-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="120ba-106">[out] Ein Zeiger auf den Threadbezeichner des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="120ba-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="120ba-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="120ba-107">Remarks</span></span>  
 <span data-ttu-id="120ba-108">Der BS-Thread wird anstelle von ICorDebugThread verwendet, können für Situationen, in dem ein MDA ausgelöst wird, an einen nativen Thread oder für einen verwalteten Thread, der noch keinen verwalteten Code eingegeben hat.</span><span class="sxs-lookup"><span data-stu-id="120ba-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="120ba-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="120ba-109">Requirements</span></span>  
 <span data-ttu-id="120ba-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="120ba-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="120ba-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="120ba-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="120ba-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="120ba-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="120ba-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="120ba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="120ba-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="120ba-114">See also</span></span>
- [<span data-ttu-id="120ba-115">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="120ba-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="120ba-116">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="120ba-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
