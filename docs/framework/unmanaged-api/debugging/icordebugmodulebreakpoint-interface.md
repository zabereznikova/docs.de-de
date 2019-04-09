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
ms.openlocfilehash: d6a43a264fcaa94ce4e629d8db504e9d416f6b89
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179711"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="70fc1-102">ICorDebugModuleBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70fc1-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="70fc1-103">Bietet Zugriff auf bestimmte Module.</span><span class="sxs-lookup"><span data-stu-id="70fc1-103">Provides access to specific modules.</span></span> <span data-ttu-id="70fc1-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugBreakpoint-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="70fc1-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70fc1-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="70fc1-105">Methods</span></span>  
  
|<span data-ttu-id="70fc1-106">Methode</span><span class="sxs-lookup"><span data-stu-id="70fc1-106">Method</span></span>|<span data-ttu-id="70fc1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70fc1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70fc1-108">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="70fc1-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="70fc1-109">Ruft einen Schnittstellenzeiger auf ein ICorDebugModule, die das Modul verweist, in dem dieser Haltepunkt festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="70fc1-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70fc1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70fc1-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70fc1-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="70fc1-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70fc1-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70fc1-112">Requirements</span></span>  
 <span data-ttu-id="70fc1-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70fc1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70fc1-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70fc1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70fc1-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70fc1-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="70fc1-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="70fc1-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="70fc1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70fc1-117">See also</span></span>

- [<span data-ttu-id="70fc1-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="70fc1-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
