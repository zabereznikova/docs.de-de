---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08937e87b8bd2249b8608f8ec1ed1f7734961b3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948563"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="af982-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode-Methode</span><span class="sxs-lookup"><span data-stu-id="af982-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="af982-103">[Unterstützt in [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] und höheren Versionen]</span><span class="sxs-lookup"><span data-stu-id="af982-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="af982-104">Aktiviert oder deaktiviert bestimmte Typen von [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) ausnahmerückrufen.</span><span class="sxs-lookup"><span data-stu-id="af982-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af982-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="af982-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af982-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="af982-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="af982-107">[in]</span><span class="sxs-lookup"><span data-stu-id="af982-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af982-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af982-108">Remarks</span></span>  
 <span data-ttu-id="af982-109">Wenn der Wert von `enableExceptionsOutsideOfJMC``false` ist:</span><span class="sxs-lookup"><span data-stu-id="af982-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="af982-110">Eine Ausnahme DEBUG_EXCEPTION_FIRST_CHANCE führt nicht in einem Rückruf an den Debugger.</span><span class="sxs-lookup"><span data-stu-id="af982-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="af982-111">Eine Ausnahme DEBUG_EXCEPTION_CATCH_HANDLER_FOUND nicht führt einen Rückruf an den Debugger, wenn die Ausnahme in Benutzercode nie zum Abbruch (d. h. der Pfad aus einem Ursprung der Ausnahme zu einem Ausnahmehandler verfügt über keine Methoden als JustMyCode oder "JMC" markiert).</span><span class="sxs-lookup"><span data-stu-id="af982-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="af982-112">Der Standardwert von `enableExceptionsOutsideOfJMC` ist `true`.</span><span class="sxs-lookup"><span data-stu-id="af982-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af982-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af982-113">Requirements</span></span>  
 <span data-ttu-id="af982-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af982-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af982-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af982-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af982-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af982-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af982-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af982-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af982-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af982-118">See also</span></span>

- [<span data-ttu-id="af982-119">ICorDebugProcess8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af982-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [<span data-ttu-id="af982-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="af982-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
