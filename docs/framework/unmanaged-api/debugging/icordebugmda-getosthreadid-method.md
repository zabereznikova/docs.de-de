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
ms.openlocfilehash: 20833624b4b853a1a56964e11a25f446c6b39053
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414712"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="c20a3-102">ICorDebugMDA::GetOSThreadId-Methode</span><span class="sxs-lookup"><span data-stu-id="c20a3-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="c20a3-103">Ruft den auf dem das Assistent für verwaltete Debuggen (MDA) dargestellte Betriebssystem (BS)-Threadbezeichner ab [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c20a3-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c20a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c20a3-104">Syntax</span></span>  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c20a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c20a3-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="c20a3-106">[out] Ein Zeiger auf den Threadbezeichner des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="c20a3-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c20a3-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c20a3-107">Remarks</span></span>  
 <span data-ttu-id="c20a3-108">Der Threadbezeichner des Betriebssystems wird anstelle ICorDebugThread verwendet, um Situationen zu ermöglichen, in dem ein MDA ausgelöst wird, entweder auf einen systemeigenen Thread oder auf einem verwalteten Thread, der noch nicht verwalteten Code eingegeben hat.</span><span class="sxs-lookup"><span data-stu-id="c20a3-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c20a3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c20a3-109">Requirements</span></span>  
 <span data-ttu-id="c20a3-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c20a3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c20a3-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c20a3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c20a3-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c20a3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c20a3-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c20a3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c20a3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c20a3-114">See Also</span></span>  
 [<span data-ttu-id="c20a3-115">ICorDebugMDA-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c20a3-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="c20a3-116">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="c20a3-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
