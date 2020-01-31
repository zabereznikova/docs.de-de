---
title: ICorDebugStackWalk-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: a6283d699263dc9b79e457010f31923f77443129
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791878"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="66281-102">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66281-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="66281-103">Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.</span><span class="sxs-lookup"><span data-stu-id="66281-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="66281-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="66281-104">Methods</span></span>  
  
|<span data-ttu-id="66281-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="66281-105">Method</span></span>|<span data-ttu-id="66281-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66281-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="66281-107">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="66281-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="66281-108">Gibt den Kontext für den aktuellen Frame im `ICorDebugStackWalk` Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="66281-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="66281-109">SetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="66281-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="66281-110">Legt den aktuellen Kontext des `ICorDebugStackWalk` Objekts auf einen gültigen Kontext für den Thread fest.</span><span class="sxs-lookup"><span data-stu-id="66281-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="66281-111">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="66281-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="66281-112">Verschiebt das `ICorDebugStackWalk` Objekt in den nächsten Frame.</span><span class="sxs-lookup"><span data-stu-id="66281-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="66281-113">GetFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="66281-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="66281-114">Ruft den aktuellen Frame im `ICorDebugStackWalk` Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="66281-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66281-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="66281-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66281-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="66281-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66281-117">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66281-117">Requirements</span></span>  
 <span data-ttu-id="66281-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66281-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66281-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66281-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66281-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66281-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66281-121">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66281-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66281-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66281-122">See also</span></span>

- [<span data-ttu-id="66281-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="66281-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="66281-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="66281-124">Debugging</span></span>](index.md)
