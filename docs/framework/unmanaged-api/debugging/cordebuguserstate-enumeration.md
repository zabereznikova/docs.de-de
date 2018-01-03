---
title: CorDebugUserState-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugUserState
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugUserState
helpviewer_keywords: CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57fd9df27b1911c90bd11712b67e6e64588c2b5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="d9046-102">CorDebugUserState-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d9046-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="d9046-103">Gibt den Benutzerzustand eines Threads an.</span><span class="sxs-lookup"><span data-stu-id="d9046-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9046-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9046-104">Syntax</span></span>  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a><span data-ttu-id="d9046-105">Member</span><span class="sxs-lookup"><span data-stu-id="d9046-105">Members</span></span>  
  
|<span data-ttu-id="d9046-106">Wert</span><span class="sxs-lookup"><span data-stu-id="d9046-106">Value</span></span>|<span data-ttu-id="d9046-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9046-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="d9046-108">Beenden des Threads wurde angefordert.</span><span class="sxs-lookup"><span data-stu-id="d9046-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="d9046-109">Eine Unterbrechung des Threads wurde angefordert.</span><span class="sxs-lookup"><span data-stu-id="d9046-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="d9046-110">Der Thread wird im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d9046-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="d9046-111">Der Thread wurde nicht gestartet, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d9046-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="d9046-112">Der Thread wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="d9046-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="d9046-113">Der Thread wartet darauf, dass ein anderer Thread eine Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d9046-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="d9046-114">Der Thread wurde angehalten.</span><span class="sxs-lookup"><span data-stu-id="d9046-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="d9046-115">Der Thread ist an einem unsicheren Punkt.</span><span class="sxs-lookup"><span data-stu-id="d9046-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="d9046-116">Also der Thread an einem Punkt in der Ausführung, in denen es möglicherweise Garbagecollection verhindert.</span><span class="sxs-lookup"><span data-stu-id="d9046-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="d9046-117">Debuggen von Ereignissen können von unsicheren Punkten weitergeleitet werden, aber das Anhalten eines Threads an einem unsicheren Punkt wird sehr wahrscheinlich einen Deadlock bis der Thread fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d9046-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="d9046-118">Die sicheren und unsicheren Punkte werden durch den Just-in-Time (JIT) und die Garbage Collection Implementierung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d9046-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="d9046-119">Der Thread wird aus dem Threadpool.</span><span class="sxs-lookup"><span data-stu-id="d9046-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9046-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9046-120">Remarks</span></span>  
 <span data-ttu-id="d9046-121">Der Benutzerzustand eines Threads ist der Zustand, den der Thread hat, wenn der Debugger untersucht.</span><span class="sxs-lookup"><span data-stu-id="d9046-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="d9046-122">Ein Thread möglicherweise eine Kombination des Benutzerstatus.</span><span class="sxs-lookup"><span data-stu-id="d9046-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="d9046-123">Verwenden der [ICorDebugThread:: GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) Methode, um Benutzerzustand eines Threads abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d9046-123">Use the [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9046-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9046-124">Requirements</span></span>  
 <span data-ttu-id="d9046-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9046-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9046-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9046-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9046-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9046-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9046-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9046-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9046-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9046-129">See Also</span></span>  
 [<span data-ttu-id="d9046-130">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d9046-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
