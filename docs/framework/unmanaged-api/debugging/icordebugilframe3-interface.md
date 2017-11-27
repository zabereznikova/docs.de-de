---
title: ICorDebugILFrame3-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame3
api_location: mscordbi.dll
api_type: COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fe6affcf82a16a4fd51a5e5a4bf33b247dae0688
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="3452a-102">ICorDebugILFrame3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3452a-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="3452a-103">Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="3452a-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="3452a-104">`ICorDebugILFrame3`ist eine logische Erweiterung von die ICorDebugILFrame und ICorDebugILFrame2-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3452a-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3452a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3452a-105">Methods</span></span>  
  
|<span data-ttu-id="3452a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="3452a-106">Method</span></span>|<span data-ttu-id="3452a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3452a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3452a-108">GetReturnValueForILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="3452a-108">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="3452a-109">Ruft ein ICorDebugValue-Objekt, das den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="3452a-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3452a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3452a-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3452a-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3452a-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3452a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3452a-112">Requirements</span></span>  
 <span data-ttu-id="3452a-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3452a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3452a-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3452a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3452a-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3452a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3452a-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3452a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3452a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3452a-117">See Also</span></span>  
 [<span data-ttu-id="3452a-118">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3452a-118">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="3452a-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3452a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
