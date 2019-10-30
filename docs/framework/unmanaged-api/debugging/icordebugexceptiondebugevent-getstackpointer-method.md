---
title: 'Icordebugexceptiondebugevent:: getstackpointer-Methode'
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 688f5aec457298a43d95a35fdbc6e04e29a306a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084676"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="f84de-102">Icordebugexceptiondebugevent:: getstackpointer-Methode</span><span class="sxs-lookup"><span data-stu-id="f84de-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="f84de-103">Ruft den Stapelzeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="f84de-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f84de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f84de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f84de-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f84de-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="f84de-106">[out] Ein Zeiger auf die Adresse des Stapelzeigers für dieses Ausnahmedebugereignis.</span><span class="sxs-lookup"><span data-stu-id="f84de-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="f84de-107">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="f84de-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f84de-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f84de-108">Remarks</span></span>  
 <span data-ttu-id="f84de-109">Die Bedeutung dieses Stapelzeigers hängt (wie in der folgenden Tabelle gezeigt) vom Ereignistyp ab.</span><span class="sxs-lookup"><span data-stu-id="f84de-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="f84de-110">Ereignistyp</span><span class="sxs-lookup"><span data-stu-id="f84de-110">Event type</span></span>|<span data-ttu-id="f84de-111">Bedeutung des `pStackPointer`-Werts</span><span class="sxs-lookup"><span data-stu-id="f84de-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="f84de-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="f84de-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="f84de-113">Der Stapelzeiger des Frames, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="f84de-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="f84de-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="f84de-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="f84de-115">Der Stapelzeiger des Benutzercode-Frames, der dem Punkt der ausgelösten Ausnahme am nächsten ist.</span><span class="sxs-lookup"><span data-stu-id="f84de-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="f84de-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="f84de-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="f84de-117">Der Stapelzeiger des Frames, der den Catch-Handler enthält.</span><span class="sxs-lookup"><span data-stu-id="f84de-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="f84de-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="f84de-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="f84de-119">`pStackPointer` ist **NULL**.</span><span class="sxs-lookup"><span data-stu-id="f84de-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="f84de-120">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f84de-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="f84de-121">Der Ereignistyp ist über die [icordebugdebugevent:: geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) -Methode verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f84de-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f84de-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f84de-122">Requirements</span></span>  
 <span data-ttu-id="f84de-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f84de-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f84de-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f84de-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f84de-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f84de-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f84de-126">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f84de-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f84de-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f84de-127">See also</span></span>

- [<span data-ttu-id="f84de-128">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f84de-128">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="f84de-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f84de-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
