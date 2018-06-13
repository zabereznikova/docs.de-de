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
ms.openlocfilehash: d2515e21ec00bd656eafd21a092a27304f7b1769
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419015"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="5854a-102">ICorDebugProcess::ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="5854a-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="5854a-103">Löscht die aktuellen nicht verwalteten Ausnahme für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="5854a-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5854a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5854a-104">Syntax</span></span>  
  
```  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5854a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5854a-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="5854a-106">[in] Die ID des Threads, die auf dem aktuelle nicht verwalteten Ausnahme gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="5854a-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5854a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5854a-107">Remarks</span></span>  
 <span data-ttu-id="5854a-108">Rufen Sie diese Methode vor dem Aufruf [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) Wenn ein Thread eine nicht verwaltete Ausnahme, die von der zu debuggenden Komponente ignoriert werden sollen gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="5854a-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="5854a-109">Hiermit löschen Sie die ausstehenden in-Band-(IB) und die Out-of-Band (OOB) Ereignisse auf den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="5854a-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="5854a-110">Alle OOB-Haltepunkte und einstufiger Ausnahmen werden automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5854a-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="5854a-111">Verwendung [ICorDebugThread2:: InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) verwaltet Sie zum Abfangen von des aktuellen Ausnahme in einem Thread.</span><span class="sxs-lookup"><span data-stu-id="5854a-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5854a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5854a-112">Requirements</span></span>  
 <span data-ttu-id="5854a-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5854a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5854a-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5854a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5854a-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5854a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5854a-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5854a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
