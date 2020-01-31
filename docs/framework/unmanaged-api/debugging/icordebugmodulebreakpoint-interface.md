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
ms.openlocfilehash: df3ad3fa4ef4eeee7e23ca1629da7a8b8ce09711
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792924"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="b274e-102">ICorDebugModuleBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b274e-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="b274e-103">Ermöglicht den Zugriff auf bestimmte Module.</span><span class="sxs-lookup"><span data-stu-id="b274e-103">Provides access to specific modules.</span></span> <span data-ttu-id="b274e-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugBreakpoint-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b274e-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b274e-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b274e-105">Methods</span></span>  
  
|<span data-ttu-id="b274e-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="b274e-106">Method</span></span>|<span data-ttu-id="b274e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b274e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b274e-108">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="b274e-108">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="b274e-109">Ruft einen Schnittstellen Zeiger auf ein icordebumodule-Element ab, das auf das Modul verweist, in dem dieser Haltepunkt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b274e-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b274e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b274e-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b274e-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b274e-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b274e-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b274e-112">Requirements</span></span>  
 <span data-ttu-id="b274e-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b274e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b274e-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b274e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b274e-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b274e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b274e-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b274e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b274e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b274e-117">See also</span></span>

- [<span data-ttu-id="b274e-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b274e-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
