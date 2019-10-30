---
title: ICorDebugProcess::ClearCurrentException-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
ms.openlocfilehash: 37a7d8fa4439d52db3cddfff22ac6580b19af58a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128913"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="10d2b-102">ICorDebugProcess::ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="10d2b-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="10d2b-103">Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="10d2b-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10d2b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="10d2b-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10d2b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="10d2b-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="10d2b-106">in Die ID des Threads, in dem die aktuelle nicht verwaltete Ausnahme gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="10d2b-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10d2b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10d2b-107">Remarks</span></span>  
 <span data-ttu-id="10d2b-108">Rufen Sie diese Methode auf, bevor Sie [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) aufrufen, wenn ein Thread eine nicht verwaltete Ausnahme gemeldet hat, die von der zu debuggenden Komponente ignoriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="10d2b-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="10d2b-109">Hierdurch werden sowohl die ausstehenden in-Band (IB)-als auch die Out-of-Band-Ereignisse (OOB) für den angegebenen Thread gelöscht.</span><span class="sxs-lookup"><span data-stu-id="10d2b-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="10d2b-110">Alle OOB-Breakpoints und Einzelschritt-Ausnahmen werden automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="10d2b-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="10d2b-111">Verwenden Sie [ICorDebugThread2:: intercepteption TException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) , um die aktuelle verwaltete Ausnahme in einem Thread abzufangen.</span><span class="sxs-lookup"><span data-stu-id="10d2b-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10d2b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10d2b-112">Requirements</span></span>  
 <span data-ttu-id="10d2b-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10d2b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10d2b-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10d2b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10d2b-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10d2b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10d2b-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10d2b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
