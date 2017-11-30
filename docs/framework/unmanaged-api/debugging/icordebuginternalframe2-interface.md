---
title: ICorDebugInternalFrame2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame2
helpviewer_keywords: ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b612cb2fb8b2a84555ccf36a8537ebecff673d47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="ee52c-102">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee52c-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="ee52c-103">Enthält Informationen zu internen Frames, u. a. Stapeladresse und Position in Bezug auf ICorDebugFrame-Objekte.</span><span class="sxs-lookup"><span data-stu-id="ee52c-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee52c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ee52c-104">Methods</span></span>  
  
|<span data-ttu-id="ee52c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ee52c-105">Method</span></span>|<span data-ttu-id="ee52c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee52c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee52c-107">GetFrameAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="ee52c-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="ee52c-108">Gibt die Stapeladresse des internen Frames zurück.</span><span class="sxs-lookup"><span data-stu-id="ee52c-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="ee52c-109">IsCloserToLeaf-Methode</span><span class="sxs-lookup"><span data-stu-id="ee52c-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="ee52c-110">Überprüft, ob die `this` internen Frames ähnelt, das Blatt als das angegebene ICorDebugFrame-Objekt.</span><span class="sxs-lookup"><span data-stu-id="ee52c-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee52c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee52c-111">Remarks</span></span>  
 <span data-ttu-id="ee52c-112">Diese Schnittstelle erweitert die ICorDebugInternalFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ee52c-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee52c-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ee52c-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee52c-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee52c-114">Requirements</span></span>  
 <span data-ttu-id="ee52c-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee52c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee52c-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee52c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee52c-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee52c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee52c-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee52c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee52c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee52c-119">See Also</span></span>  
 [<span data-ttu-id="ee52c-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ee52c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ee52c-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ee52c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
