---
title: ICorDebugModuleBreakpoint Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModuleBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModuleBreakpoint
helpviewer_keywords: ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3e3937c6c0baef4cc927b5c5d789826c70beebf2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulebreakpoint-interface1"></a><span data-ttu-id="154a7-102">ICorDebugModuleBreakpoint Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="154a7-102">ICorDebugModuleBreakpoint Interface1</span></span>
<span data-ttu-id="154a7-103">Bietet Zugriff auf bestimmte Module.</span><span class="sxs-lookup"><span data-stu-id="154a7-103">Provides access to specific modules.</span></span> <span data-ttu-id="154a7-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugBreakpoint-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="154a7-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="154a7-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="154a7-105">Methods</span></span>  
  
|<span data-ttu-id="154a7-106">Methode</span><span class="sxs-lookup"><span data-stu-id="154a7-106">Method</span></span>|<span data-ttu-id="154a7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="154a7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="154a7-108">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="154a7-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="154a7-109">Ruft einen Schnittstellenzeiger auf ein ICorDebugModule, die das Modul verweist, in dem dieser Haltepunkt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="154a7-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="154a7-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="154a7-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="154a7-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="154a7-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="154a7-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="154a7-112">Requirements</span></span>  
 <span data-ttu-id="154a7-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="154a7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="154a7-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="154a7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="154a7-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="154a7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="154a7-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="154a7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="154a7-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="154a7-117">See Also</span></span>  
 [<span data-ttu-id="154a7-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="154a7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
