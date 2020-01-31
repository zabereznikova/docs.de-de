---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: 2c0da899b3f6f3c229c6f5e5b4cafe48fdc19742
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792170"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="93e7b-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode</span><span class="sxs-lookup"><span data-stu-id="93e7b-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="93e7b-103">[Wird in der .NET Framework 4,6 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="93e7b-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="93e7b-104">Aktiviert oder deaktiviert bestimmte Typen von [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) -Ausnahme Rückrufen.</span><span class="sxs-lookup"><span data-stu-id="93e7b-104">Enables or disables certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93e7b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="93e7b-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93e7b-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="93e7b-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="93e7b-107">[in]</span><span class="sxs-lookup"><span data-stu-id="93e7b-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93e7b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93e7b-108">Remarks</span></span>  
 <span data-ttu-id="93e7b-109">Wenn der Wert von `enableExceptionsOutsideOfJMC``false` ist:</span><span class="sxs-lookup"><span data-stu-id="93e7b-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="93e7b-110">Eine DEBUG_EXCEPTION_FIRST_CHANCEAusnahme führt nicht zu einem Rückruf an den Debugger.</span><span class="sxs-lookup"><span data-stu-id="93e7b-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="93e7b-111">Eine DEBUG_EXCEPTION_CATCH_HANDLER_FOUND-Ausnahme führt nicht zu einem Rückruf an den Debugger, wenn für die Ausnahme kein Escapevorgang in Benutzercode erfolgt (d. h. der Pfad aus einem Ursprung der Ausnahme zu einem Ausnahmehandler über keine Methoden verfügt, die als "JustMyCode" oder "JMC" markiert ist).</span><span class="sxs-lookup"><span data-stu-id="93e7b-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="93e7b-112">Der Standardwert von `enableExceptionsOutsideOfJMC` ist `true`.</span><span class="sxs-lookup"><span data-stu-id="93e7b-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93e7b-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="93e7b-113">Requirements</span></span>  
 <span data-ttu-id="93e7b-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93e7b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93e7b-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93e7b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93e7b-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93e7b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93e7b-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93e7b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e7b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93e7b-118">See also</span></span>

- [<span data-ttu-id="93e7b-119">ICorDebugProcess8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="93e7b-119">ICorDebugProcess8 Interface</span></span>](icordebugprocess8-interface.md)
- [<span data-ttu-id="93e7b-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="93e7b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
