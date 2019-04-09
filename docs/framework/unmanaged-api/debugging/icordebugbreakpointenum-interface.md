---
title: ICorDebugBreakpointEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fd42f13f699b0b79fd69311186f2b2ca0c9998a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149070"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="567c1-102">ICorDebugBreakpointEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="567c1-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="567c1-103">ICorDebugEnum-Methoden implementiert, und listet ICorDebugBreakpoint-Arrays.</span><span class="sxs-lookup"><span data-stu-id="567c1-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="567c1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="567c1-104">Methods</span></span>  
  
|<span data-ttu-id="567c1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="567c1-105">Method</span></span>|<span data-ttu-id="567c1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="567c1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="567c1-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="567c1-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="567c1-108">Ruft die angegebene Anzahl von `ICorDebugBreakpoint` Instanzen aus der Enumeration, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="567c1-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="567c1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="567c1-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="567c1-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="567c1-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="567c1-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="567c1-111">Requirements</span></span>  
 <span data-ttu-id="567c1-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="567c1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="567c1-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="567c1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="567c1-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="567c1-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="567c1-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="567c1-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="567c1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="567c1-116">See also</span></span>

- [<span data-ttu-id="567c1-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="567c1-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
