---
title: ICorDebugExceptionDebugEvent::GetStackPointer-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17a7540c25eb1273add430c3a8ae01eea35497e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="12377-102">ICorDebugExceptionDebugEvent::GetStackPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="12377-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="12377-103">Ruft den Stapelzeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="12377-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12377-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12377-104">Syntax</span></span>  
  
```  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12377-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="12377-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="12377-106">[out] Ein Zeiger auf die Adresse des Stapelzeigers für dieses Ausnahmedebugereignis.</span><span class="sxs-lookup"><span data-stu-id="12377-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="12377-107">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="12377-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12377-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12377-108">Remarks</span></span>  
 <span data-ttu-id="12377-109">Die Bedeutung dieses Stapelzeigers hängt (wie in der folgenden Tabelle gezeigt) vom Ereignistyp ab.</span><span class="sxs-lookup"><span data-stu-id="12377-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="12377-110">Ereignistyp</span><span class="sxs-lookup"><span data-stu-id="12377-110">Event type</span></span>|<span data-ttu-id="12377-111">Bedeutung des `pStackPointer`-Werts</span><span class="sxs-lookup"><span data-stu-id="12377-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="12377-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="12377-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="12377-113">Der Stapelzeiger des Frames, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="12377-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="12377-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="12377-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="12377-115">Der Stapelzeiger des Benutzercode-Frames, der dem Punkt der ausgelösten Ausnahme am nächsten ist.</span><span class="sxs-lookup"><span data-stu-id="12377-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="12377-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="12377-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="12377-117">Der Stapelzeiger des Frames, der den Catch-Handler enthält.</span><span class="sxs-lookup"><span data-stu-id="12377-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="12377-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="12377-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="12377-119">`pStackPointer` ist **NULL**.</span><span class="sxs-lookup"><span data-stu-id="12377-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="12377-120">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="12377-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="12377-121">Das Ereignis des Typs steht über den [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="12377-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12377-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="12377-122">Requirements</span></span>  
 <span data-ttu-id="12377-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12377-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12377-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12377-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12377-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12377-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12377-126">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12377-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12377-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12377-127">See Also</span></span>  
 [<span data-ttu-id="12377-128">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12377-128">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="12377-129">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="12377-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
