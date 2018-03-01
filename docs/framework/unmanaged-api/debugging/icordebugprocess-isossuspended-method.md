---
title: ICorDebugProcess::IsOSSuspended-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 97c394e3084007227cf157c62a12df3f5cfac8e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="2f841-102">ICorDebugProcess::IsOSSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="2f841-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="2f841-103">Ruft einen Wert, der angibt, ob die angegebene Thread aufgrund der Debugger, beenden diesen Prozess angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="2f841-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f841-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f841-104">Syntax</span></span>  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f841-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2f841-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="2f841-106">[in] Die ID des betreffenden Threads.</span><span class="sxs-lookup"><span data-stu-id="2f841-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="2f841-107">[out] Ein Zeiger auf einen booleschen Wert, der `true` Wenn der angegebene Thread angehalten, und andernfalls wurde \*`pbSuspended` ist `false`.</span><span class="sxs-lookup"><span data-stu-id="2f841-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f841-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f841-108">Remarks</span></span>  
 <span data-ttu-id="2f841-109">Wenn der angegebenen Threads als Ergebnis der Debugger, beenden diesen Prozess angehalten wurde, den angegebenen Thread Win32 Unterbrechungszähler wird um eins erhöht.</span><span class="sxs-lookup"><span data-stu-id="2f841-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="2f841-110">Die Debugger-Benutzeroberfläche (UI) sollten diese Informationen berücksichtigt werden, wenn angezeigt wird das Betriebssystem (BS) Unterbrechungszähler des Threads für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2f841-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="2f841-111">Die `IsOSSuspended` Methode ist sinnvoll, nur im Kontext von nicht verwaltetem Debuggen.</span><span class="sxs-lookup"><span data-stu-id="2f841-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="2f841-112">Während des verwalteten Debuggens werden Threads kooperativ und nicht OS angehalten.</span><span class="sxs-lookup"><span data-stu-id="2f841-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f841-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f841-113">Requirements</span></span>  
 <span data-ttu-id="2f841-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f841-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f841-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f841-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f841-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f841-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f841-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f841-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
