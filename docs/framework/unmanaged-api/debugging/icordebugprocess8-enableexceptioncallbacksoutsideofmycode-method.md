---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: b6bfd258f35f19719be5e5169a1edc22a358371c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123378"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="60675-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode</span><span class="sxs-lookup"><span data-stu-id="60675-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="60675-103">[Wird in der .NET Framework 4,6 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="60675-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="60675-104">Aktiviert oder deaktiviert bestimmte Typen von [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) -Ausnahme Rückrufen.</span><span class="sxs-lookup"><span data-stu-id="60675-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60675-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="60675-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60675-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="60675-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="60675-107">[in]</span><span class="sxs-lookup"><span data-stu-id="60675-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60675-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60675-108">Remarks</span></span>  
 <span data-ttu-id="60675-109">Wenn der Wert von `enableExceptionsOutsideOfJMC``false` ist:</span><span class="sxs-lookup"><span data-stu-id="60675-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="60675-110">Eine DEBUG_EXCEPTION_FIRST_CHANCE-Ausnahme führt nicht zu einem Rückruf an den Debugger.</span><span class="sxs-lookup"><span data-stu-id="60675-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="60675-111">Eine DEBUG_EXCEPTION_CATCH_HANDLER_FOUND-Ausnahme führt nicht zu einem Rückruf an den Debugger, wenn die Ausnahme niemals in den Benutzercode Escapezeichen (d. h., der Pfad von einem Exception-Ursprung zu einem Ausnahme Handler hat keine Methoden, die als JustMyCode oder JMC gekennzeichnet sind).</span><span class="sxs-lookup"><span data-stu-id="60675-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="60675-112">Der Standardwert von `enableExceptionsOutsideOfJMC` ist `true`.</span><span class="sxs-lookup"><span data-stu-id="60675-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60675-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60675-113">Requirements</span></span>  
 <span data-ttu-id="60675-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60675-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60675-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60675-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60675-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60675-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60675-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60675-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60675-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60675-118">See also</span></span>

- [<span data-ttu-id="60675-119">ICorDebugProcess8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60675-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [<span data-ttu-id="60675-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="60675-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
