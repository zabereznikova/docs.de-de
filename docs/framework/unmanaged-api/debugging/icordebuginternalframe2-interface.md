---
title: ICorDebugInternalFrame2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
ms.openlocfilehash: a17c46d5ef08963bb0d7fc280ba8b90531e41c5b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719631"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="ff793-102">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff793-102">ICorDebugInternalFrame2 Interface</span></span>

<span data-ttu-id="ff793-103">Stellt Informationen zu internen Frames bereit, u. a. Stapeladresse und Position in Bezug auf ICorDebugFrame-Objekte.</span><span class="sxs-lookup"><span data-stu-id="ff793-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff793-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ff793-104">Methods</span></span>  
  
|<span data-ttu-id="ff793-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ff793-105">Method</span></span>|<span data-ttu-id="ff793-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ff793-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff793-107">GetFrameAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="ff793-107">GetFrameAddress Method</span></span>](icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="ff793-108">Gibt die Stapel Adresse des internen Frames zurück.</span><span class="sxs-lookup"><span data-stu-id="ff793-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="ff793-109">IsCloserToLeaf-Methode</span><span class="sxs-lookup"><span data-stu-id="ff793-109">IsCloserToLeaf Method</span></span>](icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="ff793-110">Überprüft, ob sich der `this` interne Frame näher an dem Blatt als das angegebene ICorDebugFrame-Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="ff793-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff793-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff793-111">Remarks</span></span>  

 <span data-ttu-id="ff793-112">Diese Schnittstelle erweitert die ICorDebug-internalframe-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ff793-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff793-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ff793-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff793-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ff793-114">Requirements</span></span>  

 <span data-ttu-id="ff793-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff793-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff793-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff793-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff793-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff793-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff793-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff793-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff793-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff793-119">See also</span></span>

- [<span data-ttu-id="ff793-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ff793-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ff793-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ff793-121">Debugging</span></span>](index.md)
