---
title: ICorDebugProcess::ClearCurrentException-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.ClearCurrentException
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8c6204f8906a29f7e8541d548872b6e84fd883bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="6d7bc-102">ICorDebugProcess::ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="6d7bc-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="6d7bc-103">Löscht die aktuellen nicht verwalteten Ausnahme für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="6d7bc-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d7bc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d7bc-104">Syntax</span></span>  
  
```  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d7bc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d7bc-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="6d7bc-106">[in] Die ID des Threads, die auf dem aktuelle nicht verwalteten Ausnahme gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="6d7bc-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d7bc-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d7bc-107">Remarks</span></span>  
 <span data-ttu-id="6d7bc-108">Rufen Sie diese Methode vor dem Aufruf [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) Wenn ein Thread eine nicht verwaltete Ausnahme, die von der zu debuggenden Komponente ignoriert werden sollen gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="6d7bc-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="6d7bc-109">Hiermit löschen Sie die ausstehenden in-Band-(IB) und die Out-of-Band (OOB) Ereignisse auf den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="6d7bc-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="6d7bc-110">Alle OOB-Haltepunkte und einstufiger Ausnahmen werden automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6d7bc-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="6d7bc-111">Verwendung [ICorDebugThread2:: InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) verwaltet Sie zum Abfangen von des aktuellen Ausnahme in einem Thread.</span><span class="sxs-lookup"><span data-stu-id="6d7bc-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d7bc-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d7bc-112">Requirements</span></span>  
 <span data-ttu-id="6d7bc-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d7bc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d7bc-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d7bc-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d7bc-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d7bc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d7bc-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d7bc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
