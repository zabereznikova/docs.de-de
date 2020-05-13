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
ms.openlocfilehash: b8d20de990ff4a27a82590342494a307c986457e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207395"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="44089-102">ICorDebugProcess::ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="44089-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="44089-103">Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="44089-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44089-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44089-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44089-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44089-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="44089-106">in Die ID des Threads, in dem die aktuelle nicht verwaltete Ausnahme gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="44089-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44089-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44089-107">Remarks</span></span>  
 <span data-ttu-id="44089-108">Rufen Sie diese Methode auf, bevor Sie [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) aufrufen, wenn ein Thread eine nicht verwaltete Ausnahme gemeldet hat, die von der zu debuggenden Komponente ignoriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="44089-108">Call this method before calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="44089-109">Hierdurch werden sowohl die ausstehenden in-Band (IB)-als auch die Out-of-Band-Ereignisse (OOB) für den angegebenen Thread gelöscht.</span><span class="sxs-lookup"><span data-stu-id="44089-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="44089-110">Alle OOB-Breakpoints und Einzelschritt-Ausnahmen werden automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="44089-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="44089-111">Verwenden Sie [ICorDebugThread2:: intercepteption TException](icordebugthread2-interceptcurrentexception-method.md) , um die aktuelle verwaltete Ausnahme in einem Thread abzufangen.</span><span class="sxs-lookup"><span data-stu-id="44089-111">Use [ICorDebugThread2::InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44089-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="44089-112">Requirements</span></span>  
 <span data-ttu-id="44089-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44089-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44089-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44089-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44089-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44089-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44089-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44089-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
