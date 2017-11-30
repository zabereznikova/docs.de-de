---
title: ICorDebugMDA::GetOSThreadId-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetOSThreadId
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6cc53eecadd982d7cea045424de52d8e6f64107b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="42bb6-102">ICorDebugMDA::GetOSThreadId-Methode</span><span class="sxs-lookup"><span data-stu-id="42bb6-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="42bb6-103">Ruft den auf dem das Assistent für verwaltete Debuggen (MDA) dargestellte Betriebssystem (BS)-Threadbezeichner ab [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="42bb6-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42bb6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42bb6-104">Syntax</span></span>  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42bb6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="42bb6-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="42bb6-106">[out] Ein Zeiger auf den Threadbezeichner des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="42bb6-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42bb6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42bb6-107">Remarks</span></span>  
 <span data-ttu-id="42bb6-108">Der Threadbezeichner des Betriebssystems wird anstelle ICorDebugThread verwendet, um Situationen zu ermöglichen, in dem ein MDA ausgelöst wird, entweder auf einen systemeigenen Thread oder auf einem verwalteten Thread, der noch nicht verwalteten Code eingegeben hat.</span><span class="sxs-lookup"><span data-stu-id="42bb6-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42bb6-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42bb6-109">Requirements</span></span>  
 <span data-ttu-id="42bb6-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42bb6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42bb6-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42bb6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42bb6-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42bb6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42bb6-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42bb6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42bb6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42bb6-114">See Also</span></span>  
 [<span data-ttu-id="42bb6-115">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42bb6-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="42bb6-116">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="42bb6-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
