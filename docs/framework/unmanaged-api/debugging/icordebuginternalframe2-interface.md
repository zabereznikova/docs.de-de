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
ms.openlocfilehash: 9e333d71505a055cfe27df2c79a102c939bafc9d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788478"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="83686-102">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83686-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="83686-103">Stellt Informationen zu internen Frames bereit, u. a. Stapeladresse und Position in Bezug auf ICorDebugFrame-Objekte.</span><span class="sxs-lookup"><span data-stu-id="83686-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83686-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="83686-104">Methods</span></span>  
  
|<span data-ttu-id="83686-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="83686-105">Method</span></span>|<span data-ttu-id="83686-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83686-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83686-107">GetFrameAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="83686-107">GetFrameAddress Method</span></span>](icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="83686-108">Gibt die Stapel Adresse des internen Frames zurück.</span><span class="sxs-lookup"><span data-stu-id="83686-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="83686-109">IsCloserToLeaf-Methode</span><span class="sxs-lookup"><span data-stu-id="83686-109">IsCloserToLeaf Method</span></span>](icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="83686-110">Überprüft, ob sich der `this` internen Frame näher an dem Blatt als das angegebene ICorDebugFrame-Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="83686-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83686-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83686-111">Remarks</span></span>  
 <span data-ttu-id="83686-112">Diese Schnittstelle erweitert die ICorDebug-internalframe-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="83686-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83686-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="83686-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83686-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83686-114">Requirements</span></span>  
 <span data-ttu-id="83686-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83686-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83686-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83686-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83686-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83686-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83686-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83686-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83686-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83686-119">See also</span></span>

- [<span data-ttu-id="83686-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="83686-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="83686-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="83686-121">Debugging</span></span>](index.md)
