---
title: ICorDebugExceptionDebugEvent::GetNativeIP-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 616f0a9787220aba0cc4d460c80b856076e1e437
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="6b9f0-102">ICorDebugExceptionDebugEvent::GetNativeIP-Methode</span><span class="sxs-lookup"><span data-stu-id="6b9f0-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="6b9f0-103">Ruft den systemeigenen Anweisungszeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="6b9f0-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b9f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b9f0-104">Syntax</span></span>  
  
```  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b9f0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b9f0-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="6b9f0-106">[out] Ein Zeiger auf den Anweisungszeiger für dieses Ausnahmedebugereignis.</span><span class="sxs-lookup"><span data-stu-id="6b9f0-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="6b9f0-107">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="6b9f0-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b9f0-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b9f0-108">Remarks</span></span>  
 <span data-ttu-id="6b9f0-109">Die Bedeutung dieses Anweisungszeigers hängt (wie in der folgenden Tabelle gezeigt) vom Ereignistyp ab.</span><span class="sxs-lookup"><span data-stu-id="6b9f0-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="6b9f0-110">Ereignistyp</span><span class="sxs-lookup"><span data-stu-id="6b9f0-110">Event type</span></span>|<span data-ttu-id="6b9f0-111">Bedeutung des `pStackPointer`-Werts</span><span class="sxs-lookup"><span data-stu-id="6b9f0-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="6b9f0-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="6b9f0-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="6b9f0-113">Die Adresse der fehlerhaften Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6b9f0-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="6b9f0-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="6b9f0-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="6b9f0-115">Die Codeadresse im Frame angegeben wird, durch die [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) Methode, in dem die Ausführung fortgesetzt würde, wenn keine Ausnahme ausgelöst worden wäre.</span><span class="sxs-lookup"><span data-stu-id="6b9f0-115">The code address in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="6b9f0-116">Die Ausnahme kann ggf. bewirken, dass anderer Code (z. B. der Catch-Block einer nicht verursachen eine `try/catch/finally`-Klausel) in diesem Frame ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6b9f0-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="6b9f0-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="6b9f0-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="6b9f0-118">Der Codeadresse `catch` Handler Ausführung beginnt in der Rahmen, angegeben durch die [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="6b9f0-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="6b9f0-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="6b9f0-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="6b9f0-120">`pIP` ist 0.</span><span class="sxs-lookup"><span data-stu-id="6b9f0-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="6b9f0-121">Das Ereignis des Typs steht über den [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="6b9f0-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b9f0-122">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6b9f0-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b9f0-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b9f0-123">Requirements</span></span>  
 <span data-ttu-id="6b9f0-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b9f0-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b9f0-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b9f0-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b9f0-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b9f0-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b9f0-127">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b9f0-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b9f0-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b9f0-128">See Also</span></span>  
 [<span data-ttu-id="6b9f0-129">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b9f0-129">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="6b9f0-130">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6b9f0-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
