---
title: ICorDebugModuleBreakpoint Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cec51a7efe17c2188f12039333dd90f557b1e724
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulebreakpoint-interface1"></a><span data-ttu-id="0229e-102">ICorDebugModuleBreakpoint Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="0229e-102">ICorDebugModuleBreakpoint Interface1</span></span>
<span data-ttu-id="0229e-103">Bietet Zugriff auf bestimmte Module.</span><span class="sxs-lookup"><span data-stu-id="0229e-103">Provides access to specific modules.</span></span> <span data-ttu-id="0229e-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugBreakpoint-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0229e-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0229e-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="0229e-105">Methods</span></span>  
  
|<span data-ttu-id="0229e-106">Methode</span><span class="sxs-lookup"><span data-stu-id="0229e-106">Method</span></span>|<span data-ttu-id="0229e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0229e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0229e-108">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="0229e-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="0229e-109">Ruft einen Schnittstellenzeiger auf ein ICorDebugModule, die das Modul verweist, in dem dieser Haltepunkt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0229e-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0229e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0229e-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0229e-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0229e-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0229e-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0229e-112">Requirements</span></span>  
 <span data-ttu-id="0229e-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0229e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0229e-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0229e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0229e-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0229e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0229e-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0229e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0229e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0229e-117">See Also</span></span>  
 [<span data-ttu-id="0229e-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0229e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
