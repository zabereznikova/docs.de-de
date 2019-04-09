---
title: ICorDebugRuntimeUnwindableFrame-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf6bc73683a6c37ceaaffc635a58803b71c3b6cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134198"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="20c53-102">ICorDebugRuntimeUnwindableFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20c53-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="20c53-103">Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.</span><span class="sxs-lookup"><span data-stu-id="20c53-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20c53-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20c53-104">Remarks</span></span>  
 `ICorDebugRuntimeUnwindableFrame` <span data-ttu-id="20c53-105">ist eine spezialisierte Version der ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="20c53-105">is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="20c53-106">Es wird von nicht verwalteten Methoden verwendet, die die Laufzeit Entladen eines Frames auf dem aktuellen Stapel erfordern.</span><span class="sxs-lookup"><span data-stu-id="20c53-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="20c53-107">Vorhandene Entladung Konventionen funktionieren nicht, da keine JIT-kompiliertem Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="20c53-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="20c53-108">Wenn der Debugger einen entladbaren Frame erkennt, muss bei Verwendung der [ICorDebugStackWalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) Methode entladen, aber sie sollten die Überprüfung selbst durchführen.</span><span class="sxs-lookup"><span data-stu-id="20c53-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="20c53-109">Wenn der Debugger empfängt eine `ICorDebugRuntimeUnwindableFrame`, Aufrufen der [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) Methode zum Abrufen des Kontexts des Frames.</span><span class="sxs-lookup"><span data-stu-id="20c53-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20c53-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20c53-110">Requirements</span></span>  
 <span data-ttu-id="20c53-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20c53-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20c53-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20c53-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20c53-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20c53-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="20c53-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="20c53-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="20c53-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20c53-115">See also</span></span>

- [<span data-ttu-id="20c53-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="20c53-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="20c53-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="20c53-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
