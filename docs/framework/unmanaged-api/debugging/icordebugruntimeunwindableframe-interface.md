---
title: ICorDebugRuntimeUnwindableFrame-Schnittstelle
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
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 80b4212691784d88c92235a5c5c65acaee165201
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="4f269-102">ICorDebugRuntimeUnwindableFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f269-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="4f269-103">Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.</span><span class="sxs-lookup"><span data-stu-id="4f269-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f269-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f269-104">Remarks</span></span>  
 <span data-ttu-id="4f269-105">`ICorDebugRuntimeUnwindableFrame`ist eine spezielle Version von ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4f269-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="4f269-106">Es wird von der nicht verwaltete Methoden, die die Laufzeit Entladen eines Frames auf dem aktuellen Stapel durch erfordern.</span><span class="sxs-lookup"><span data-stu-id="4f269-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="4f269-107">Vorhandene Entladung Konventionen funktionieren nicht, da keine JIT-kompilierten Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4f269-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="4f269-108">Wenn der Debugger einen entladbaren Frame erkennt, verwenden sie die [ICorDebugStackWalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) Methode, aber es entladen Überprüfung selbst ausführen.</span><span class="sxs-lookup"><span data-stu-id="4f269-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="4f269-109">Wenn der Debugger empfängt eine `ICorDebugRuntimeUnwindableFrame`, Aufrufen der [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) Methode zum Abrufen des Kontexts des Frames.</span><span class="sxs-lookup"><span data-stu-id="4f269-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f269-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f269-110">Requirements</span></span>  
 <span data-ttu-id="4f269-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f269-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f269-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f269-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f269-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f269-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f269-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f269-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f269-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f269-115">See Also</span></span>  
 [<span data-ttu-id="4f269-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4f269-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4f269-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4f269-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
