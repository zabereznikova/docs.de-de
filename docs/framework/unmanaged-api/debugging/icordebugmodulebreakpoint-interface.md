---
title: ICorDebugModuleBreakpoint-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint
helpviewer_keywords:
- ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03616f2756830e180155102492b15e18fee1085c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965119"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="85898-102">ICorDebugModuleBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85898-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="85898-103">Ermöglicht den Zugriff auf bestimmte Module.</span><span class="sxs-lookup"><span data-stu-id="85898-103">Provides access to specific modules.</span></span> <span data-ttu-id="85898-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugBreakpoint-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="85898-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85898-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="85898-105">Methods</span></span>  
  
|<span data-ttu-id="85898-106">Methode</span><span class="sxs-lookup"><span data-stu-id="85898-106">Method</span></span>|<span data-ttu-id="85898-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85898-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85898-108">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="85898-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="85898-109">Ruft einen Schnittstellen Zeiger auf ein icordebumodule-Element ab, das auf das Modul verweist, in dem dieser Haltepunkt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="85898-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85898-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85898-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85898-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="85898-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85898-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85898-112">Requirements</span></span>  
 <span data-ttu-id="85898-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85898-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85898-114">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="85898-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85898-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85898-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85898-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85898-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85898-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85898-117">See also</span></span>

- [<span data-ttu-id="85898-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="85898-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
