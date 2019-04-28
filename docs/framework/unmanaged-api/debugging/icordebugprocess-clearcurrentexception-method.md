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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f014f9213a4b9a2d5119af9a6dceebb9a9d54b52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775601"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="f53e4-102">ICorDebugProcess::ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="f53e4-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="f53e4-103">Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="f53e4-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f53e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f53e4-104">Syntax</span></span>  
  
```  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f53e4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f53e4-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="f53e4-106">[in] Die ID des Threads auf dem die aktuelle nicht verwaltete Ausnahme wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f53e4-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f53e4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f53e4-107">Remarks</span></span>  
 <span data-ttu-id="f53e4-108">Rufen Sie diese Methode vor dem Aufruf [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) ein Thread hat eine nicht verwaltete Ausnahme, die von der zu debuggenden Komponente ignoriert werden soll wenn gemeldet.</span><span class="sxs-lookup"><span data-stu-id="f53e4-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="f53e4-109">Hierdurch wird die ausstehenden in-Band-(IB) und die Out-of-Band (OOB)-Ereignisse auf den angegebenen Thread gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f53e4-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="f53e4-110">Alle OOB-Haltepunkte und Schritt für Schritt Ausnahmen werden automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f53e4-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="f53e4-111">Verwendung [ICorDebugThread2:: InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) verwaltet sie abgefangen wird die aktuelle Ausnahme in einem Thread.</span><span class="sxs-lookup"><span data-stu-id="f53e4-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f53e4-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f53e4-112">Requirements</span></span>  
 <span data-ttu-id="f53e4-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f53e4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f53e4-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f53e4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f53e4-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f53e4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f53e4-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f53e4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
