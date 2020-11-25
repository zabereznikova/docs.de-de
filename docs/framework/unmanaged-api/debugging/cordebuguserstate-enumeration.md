---
title: CorDebugUserState-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
ms.openlocfilehash: 968874a46279b7eac651d45c3890429a326651b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726950"
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="cfd0d-102">CorDebugUserState-Enumeration</span><span class="sxs-lookup"><span data-stu-id="cfd0d-102">CorDebugUserState Enumeration</span></span>

<span data-ttu-id="cfd0d-103">Gibt den Benutzerzustand eines Threads an.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfd0d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfd0d-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="cfd0d-105">Member</span><span class="sxs-lookup"><span data-stu-id="cfd0d-105">Members</span></span>  
  
|<span data-ttu-id="cfd0d-106">Wert</span><span class="sxs-lookup"><span data-stu-id="cfd0d-106">Value</span></span>|<span data-ttu-id="cfd0d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cfd0d-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="cfd0d-108">Die Beendigung des Threads wurde angefordert.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="cfd0d-109">Es wurde eine Unterbrechung des Threads angefordert.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="cfd0d-110">Der Thread wird im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="cfd0d-111">Der Thread wurde nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="cfd0d-112">Der Thread wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="cfd0d-113">Der Thread wartet auf den Abschluss einer Aufgabe durch einen anderen Thread.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="cfd0d-114">Der Thread wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="cfd0d-115">Der Thread befindet sich an einem unsicheren Punkt.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="cfd0d-116">Das heißt, der Thread befindet sich an einem Punkt in der Ausführung, an dem er Garbage Collection blockieren kann.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="cfd0d-117">Debugereignisse können von unsicheren Punkten aus verteilt werden, aber das Anhalten eines Threads an einem unsicheren Punkt führt wahrscheinlich zu einem Deadlock, bis der Thread fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="cfd0d-118">Die sicheren und unsicheren Punkte werden durch die Just-in-time (JIT)-und Garbage Collection-Implementierung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="cfd0d-119">Der Thread wird aus dem Thread Pool entfernt.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfd0d-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cfd0d-120">Remarks</span></span>  

 <span data-ttu-id="cfd0d-121">Der Benutzer Zustand eines Threads ist der Zustand, den der Thread aufweist, wenn er vom Debugger überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="cfd0d-122">Ein Thread kann eine Kombination aus Benutzer Zuständen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="cfd0d-123">Verwenden Sie die [ICorDebugThread:: GetUserState](icordebugthread-getuserstate-method.md) -Methode, um den Benutzer Zustand eines Threads abzurufen.</span><span class="sxs-lookup"><span data-stu-id="cfd0d-123">Use the [ICorDebugThread::GetUserState](icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfd0d-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cfd0d-124">Requirements</span></span>  

 <span data-ttu-id="cfd0d-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfd0d-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfd0d-126">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cfd0d-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfd0d-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfd0d-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfd0d-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfd0d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfd0d-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cfd0d-129">See also</span></span>

- [<span data-ttu-id="cfd0d-130">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="cfd0d-130">Debugging Enumerations</span></span>](debugging-enumerations.md)
