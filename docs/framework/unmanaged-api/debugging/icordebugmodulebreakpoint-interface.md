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
ms.openlocfilehash: 7026d135b02563b6c718be4096d2c5cad9d33cec
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212281"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="858f8-102">ICorDebugModuleBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="858f8-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="858f8-103">Ermöglicht den Zugriff auf bestimmte Module.</span><span class="sxs-lookup"><span data-stu-id="858f8-103">Provides access to specific modules.</span></span> <span data-ttu-id="858f8-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugBreakpoint-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="858f8-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="858f8-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="858f8-105">Methods</span></span>  
  
|<span data-ttu-id="858f8-106">Methode</span><span class="sxs-lookup"><span data-stu-id="858f8-106">Method</span></span>|<span data-ttu-id="858f8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="858f8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="858f8-108">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="858f8-108">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="858f8-109">Ruft einen Schnittstellen Zeiger auf ein icordebumodule-Element ab, das auf das Modul verweist, in dem dieser Haltepunkt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="858f8-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="858f8-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="858f8-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="858f8-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="858f8-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="858f8-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="858f8-112">Requirements</span></span>  
 <span data-ttu-id="858f8-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="858f8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="858f8-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="858f8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="858f8-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="858f8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="858f8-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="858f8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="858f8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="858f8-117">See also</span></span>

- [<span data-ttu-id="858f8-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="858f8-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
