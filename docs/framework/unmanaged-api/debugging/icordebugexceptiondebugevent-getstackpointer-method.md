---
title: ICorDebugExceptionDebugEvent::GetStackPointer-Methode
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b30fae0e0a6b6cca64581ecafe78621c8f0068b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754307"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="e2e24-102">ICorDebugExceptionDebugEvent::GetStackPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="e2e24-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="e2e24-103">Ruft den Stapelzeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="e2e24-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2e24-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2e24-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2e24-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2e24-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="e2e24-106">[out] Ein Zeiger auf die Adresse des Stapelzeigers für dieses Ausnahmedebugereignis.</span><span class="sxs-lookup"><span data-stu-id="e2e24-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="e2e24-107">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="e2e24-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2e24-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2e24-108">Remarks</span></span>  
 <span data-ttu-id="e2e24-109">Die Bedeutung dieses Stapelzeigers hängt (wie in der folgenden Tabelle gezeigt) vom Ereignistyp ab.</span><span class="sxs-lookup"><span data-stu-id="e2e24-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="e2e24-110">Ereignistyp</span><span class="sxs-lookup"><span data-stu-id="e2e24-110">Event type</span></span>|<span data-ttu-id="e2e24-111">Bedeutung des `pStackPointer`-Werts</span><span class="sxs-lookup"><span data-stu-id="e2e24-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="e2e24-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e2e24-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="e2e24-113">Der Stapelzeiger des Frames, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="e2e24-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="e2e24-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e2e24-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="e2e24-115">Der Stapelzeiger des Benutzercode-Frames, der dem Punkt der ausgelösten Ausnahme am nächsten ist.</span><span class="sxs-lookup"><span data-stu-id="e2e24-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="e2e24-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="e2e24-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="e2e24-117">Der Stapelzeiger des Frames, der den Catch-Handler enthält.</span><span class="sxs-lookup"><span data-stu-id="e2e24-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="e2e24-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="e2e24-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="e2e24-119">`pStackPointer` ist **NULL**.</span><span class="sxs-lookup"><span data-stu-id="e2e24-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e2e24-120">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e2e24-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="e2e24-121">Der Ereignistyp ist verfügbar, aus der [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e2e24-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2e24-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2e24-122">Requirements</span></span>  
 <span data-ttu-id="e2e24-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2e24-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2e24-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2e24-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2e24-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2e24-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2e24-126">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2e24-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2e24-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2e24-127">See also</span></span>

- [<span data-ttu-id="e2e24-128">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e2e24-128">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="e2e24-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e2e24-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
