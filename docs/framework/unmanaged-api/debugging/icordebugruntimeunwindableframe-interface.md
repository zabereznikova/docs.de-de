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
ms.openlocfilehash: 26b0c78d5b34b920decc8c549d90ba8147e3f323
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791922"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="d4239-102">ICorDebugRuntimeUnwindableFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4239-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="d4239-103">Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.</span><span class="sxs-lookup"><span data-stu-id="d4239-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4239-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4239-104">Remarks</span></span>  
 <span data-ttu-id="d4239-105">`ICorDebugRuntimeUnwindableFrame` ist eine spezialisierte Version der ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d4239-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="d4239-106">Sie wird von nicht verwalteten Methoden verwendet, die erfordern, dass die Laufzeit einen Frame auf dem aktuellen Stapel lädt.</span><span class="sxs-lookup"><span data-stu-id="d4239-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="d4239-107">Vorhandene Entwicklungs Konventionen funktionieren nicht, da Sie keinen JIT-kompilierten Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4239-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="d4239-108">Wenn der Debugger einen nicht abzurufbaren Frame erkennt, sollte er die [ICorDebugStackWalk:: Next](icordebugstackwalk-next-method.md) -Methode verwenden, um ihn zu entladen, aber er sollte die Überprüfung selbst durchführen.</span><span class="sxs-lookup"><span data-stu-id="d4239-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="d4239-109">Wenn der Debugger eine `ICorDebugRuntimeUnwindableFrame`empfängt, kann er die [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) -Methode aufrufen, um den Kontext des Frames abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d4239-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4239-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4239-110">Requirements</span></span>  
 <span data-ttu-id="d4239-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4239-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4239-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4239-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4239-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4239-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4239-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4239-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4239-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4239-115">See also</span></span>

- [<span data-ttu-id="d4239-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d4239-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d4239-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d4239-117">Debugging</span></span>](index.md)
