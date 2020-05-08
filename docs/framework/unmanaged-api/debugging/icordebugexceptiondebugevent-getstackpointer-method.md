---
title: ICorDebugExceptionDebugEvent::GetStackPointer-Methode
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 4f84183dfc23ebc0d0fee9feeb21329c217b9cca
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976017"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="d6500-102">ICorDebugExceptionDebugEvent::GetStackPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="d6500-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="d6500-103">Ruft den Stapelzeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="d6500-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6500-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6500-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6500-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6500-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="d6500-106">[out] Ein Zeiger auf die Adresse des Stapelzeigers für dieses Ausnahmedebugereignis.</span><span class="sxs-lookup"><span data-stu-id="d6500-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="d6500-107">Weitere Informationen finden Sie im Abschnitt zu den Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="d6500-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6500-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6500-108">Remarks</span></span>  
 <span data-ttu-id="d6500-109">Die Bedeutung dieses Stapelzeigers hängt (wie in der folgenden Tabelle gezeigt) vom Ereignistyp ab.</span><span class="sxs-lookup"><span data-stu-id="d6500-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="d6500-110">Ereignistyp</span><span class="sxs-lookup"><span data-stu-id="d6500-110">Event type</span></span>|<span data-ttu-id="d6500-111">Bedeutung des `pStackPointer`-Werts</span><span class="sxs-lookup"><span data-stu-id="d6500-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="d6500-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d6500-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="d6500-113">Der Stapelzeiger des Frames, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="d6500-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="d6500-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d6500-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="d6500-115">Der Stapelzeiger des Benutzercode-Frames, der dem Punkt der ausgelösten Ausnahme am nächsten ist.</span><span class="sxs-lookup"><span data-stu-id="d6500-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="d6500-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="d6500-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="d6500-117">Der Stapelzeiger des Frames, der den Catch-Handler enthält.</span><span class="sxs-lookup"><span data-stu-id="d6500-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="d6500-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="d6500-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="d6500-119">`pStackPointer` ist **NULL**.</span><span class="sxs-lookup"><span data-stu-id="d6500-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d6500-120">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d6500-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="d6500-121">Der Ereignistyp ist über die [icordebugdebugevent:: geteventkind](icordebugdebugevent-geteventkind-method.md) -Methode verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d6500-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6500-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d6500-122">Requirements</span></span>  
 <span data-ttu-id="d6500-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6500-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6500-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6500-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6500-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6500-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6500-126">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6500-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6500-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6500-127">See also</span></span>

- [<span data-ttu-id="d6500-128">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d6500-128">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="d6500-129">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d6500-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
