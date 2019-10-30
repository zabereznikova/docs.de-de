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
ms.openlocfilehash: 2902744b6af3c7b2bd4def73b04807ce3333a8a1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131890"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="2a7a9-102">ICorDebugRuntimeUnwindableFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a7a9-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="2a7a9-103">Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.</span><span class="sxs-lookup"><span data-stu-id="2a7a9-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a7a9-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2a7a9-104">Remarks</span></span>  
 <span data-ttu-id="2a7a9-105">`ICorDebugRuntimeUnwindableFrame` ist eine spezialisierte Version der ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2a7a9-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="2a7a9-106">Sie wird von nicht verwalteten Methoden verwendet, die erfordern, dass die Laufzeit einen Frame auf dem aktuellen Stapel lädt.</span><span class="sxs-lookup"><span data-stu-id="2a7a9-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="2a7a9-107">Vorhandene Entwicklungs Konventionen funktionieren nicht, da Sie keinen JIT-kompilierten Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a7a9-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="2a7a9-108">Wenn der Debugger einen nicht abzurufbaren Frame erkennt, sollte er die [ICorDebugStackWalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) -Methode verwenden, um ihn zu entladen, aber er sollte die Überprüfung selbst durchführen.</span><span class="sxs-lookup"><span data-stu-id="2a7a9-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="2a7a9-109">Wenn der Debugger eine `ICorDebugRuntimeUnwindableFrame`empfängt, kann er die [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) -Methode aufrufen, um den Kontext des Frames abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2a7a9-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a7a9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2a7a9-110">Requirements</span></span>  
 <span data-ttu-id="2a7a9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a7a9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a7a9-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a7a9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a7a9-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a7a9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a7a9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a7a9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a7a9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a7a9-115">See also</span></span>

- [<span data-ttu-id="2a7a9-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2a7a9-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2a7a9-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2a7a9-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
