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
ms.openlocfilehash: 14f2b6822744070e649cf9a6722272992c0bf1c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709517"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="22dde-102">ICorDebugModuleBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22dde-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="22dde-103">Ermöglicht den Zugriff auf bestimmte Module.</span><span class="sxs-lookup"><span data-stu-id="22dde-103">Provides access to specific modules.</span></span> <span data-ttu-id="22dde-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugBreakpoint-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="22dde-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22dde-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="22dde-105">Methods</span></span>  
  
|<span data-ttu-id="22dde-106">Methode</span><span class="sxs-lookup"><span data-stu-id="22dde-106">Method</span></span>|<span data-ttu-id="22dde-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="22dde-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22dde-108">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="22dde-108">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="22dde-109">Ruft einen Schnittstellen Zeiger auf ein icordebumodule-Element ab, das auf das Modul verweist, in dem dieser Haltepunkt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="22dde-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22dde-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22dde-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22dde-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="22dde-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22dde-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="22dde-112">Requirements</span></span>  

 <span data-ttu-id="22dde-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22dde-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22dde-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22dde-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22dde-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22dde-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22dde-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22dde-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22dde-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22dde-117">See also</span></span>

- [<span data-ttu-id="22dde-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="22dde-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
