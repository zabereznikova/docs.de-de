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
ms.openlocfilehash: b37a89c0a86df49c894dc43676f8feafb80f5c95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687514"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="9d7d6-102">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d7d6-102">ICorDebugStackWalk Interface</span></span>

<span data-ttu-id="9d7d6-103">Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d7d6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9d7d6-104">Methods</span></span>  
  
|<span data-ttu-id="9d7d6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="9d7d6-105">Method</span></span>|<span data-ttu-id="9d7d6-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9d7d6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d7d6-107">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="9d7d6-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="9d7d6-108">Gibt den Kontext für den aktuellen Frame im- `ICorDebugStackWalk` Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="9d7d6-109">SetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="9d7d6-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="9d7d6-110">Legt den `ICorDebugStackWalk` aktuellen Kontext des Objekts auf einen gültigen Kontext für den Thread fest.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="9d7d6-111">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="9d7d6-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="9d7d6-112">Verschiebt das- `ICorDebugStackWalk` Objekt in den nächsten Frame.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="9d7d6-113">GetFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="9d7d6-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="9d7d6-114">Ruft den aktuellen Frame im- `ICorDebugStackWalk` Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d7d6-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d7d6-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d7d6-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9d7d6-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d7d6-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9d7d6-117">Requirements</span></span>  

 <span data-ttu-id="9d7d6-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d7d6-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d7d6-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d7d6-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d7d6-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d7d6-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d7d6-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d7d6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d7d6-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d7d6-122">See also</span></span>

- [<span data-ttu-id="9d7d6-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="9d7d6-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9d7d6-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="9d7d6-124">Debugging</span></span>](index.md)
