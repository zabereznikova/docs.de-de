---
title: ICorDebugILFrame3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b46c74ec0bfc1fc44bcaca07439c472b0fd8393f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113762"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="71642-102">ICorDebugILFrame3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71642-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="71642-103">Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="71642-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="71642-104">`ICorDebugILFrame3` ist eine logische Erweiterung von die ICorDebugILFrame und ICorDebugILFrame2-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="71642-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71642-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="71642-105">Methods</span></span>  
  
|<span data-ttu-id="71642-106">Methode</span><span class="sxs-lookup"><span data-stu-id="71642-106">Method</span></span>|<span data-ttu-id="71642-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71642-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71642-108">GetReturnValueForILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="71642-108">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="71642-109">Ruft ein ICorDebugValue-Objekt, das den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="71642-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71642-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71642-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71642-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="71642-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71642-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71642-112">Requirements</span></span>  
 <span data-ttu-id="71642-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71642-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71642-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71642-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71642-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71642-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71642-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71642-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71642-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71642-117">See also</span></span>

- [<span data-ttu-id="71642-118">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71642-118">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="71642-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="71642-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
