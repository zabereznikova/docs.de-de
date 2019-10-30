---
title: 'Icordebugexceptiondebugevent:: getnativeip-Methode'
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: 42fedd20d7560dd84a2abf0efce227393035bc38
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084743"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="d9467-102">Icordebugexceptiondebugevent:: getnativeip-Methode</span><span class="sxs-lookup"><span data-stu-id="d9467-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="d9467-103">Ruft den systemeigenen Anweisungszeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="d9467-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9467-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9467-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9467-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d9467-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="d9467-106">[out] Ein Zeiger auf den Anweisungszeiger für dieses Ausnahmedebugereignis.</span><span class="sxs-lookup"><span data-stu-id="d9467-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="d9467-107">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="d9467-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9467-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9467-108">Remarks</span></span>  
 <span data-ttu-id="d9467-109">Die Bedeutung dieses Anweisungszeigers hängt (wie in der folgenden Tabelle gezeigt) vom Ereignistyp ab.</span><span class="sxs-lookup"><span data-stu-id="d9467-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="d9467-110">Ereignistyp</span><span class="sxs-lookup"><span data-stu-id="d9467-110">Event type</span></span>|<span data-ttu-id="d9467-111">Bedeutung des `pStackPointer`-Werts</span><span class="sxs-lookup"><span data-stu-id="d9467-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="d9467-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d9467-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="d9467-113">Die Adresse der fehlerhaften Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d9467-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="d9467-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d9467-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="d9467-115">Die Code Adresse im Frame, der durch die [getstackpointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) -Methode angegeben wird, in der die Ausführung fortgesetzt wird, wenn keine Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="d9467-115">The code address in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="d9467-116">Die Ausnahme kann ggf. bewirken, dass anderer Code (z. B. der Catch-Block einer nicht verursachen eine `try/catch/finally`-Klausel) in diesem Frame ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d9467-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="d9467-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="d9467-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="d9467-118">Die Code Adresse, an der `catch` handlerausführung in dem Frame gestartet wird, der von der [getstackpointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) -Methode angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d9467-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="d9467-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="d9467-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="d9467-120">`pIP` ist 0.</span><span class="sxs-lookup"><span data-stu-id="d9467-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="d9467-121">Der Ereignistyp ist über die [icordebugdebugevent:: geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) -Methode verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d9467-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9467-122">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d9467-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9467-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9467-123">Requirements</span></span>  
 <span data-ttu-id="d9467-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9467-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9467-125">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9467-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9467-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9467-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9467-127">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9467-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9467-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9467-128">See also</span></span>

- [<span data-ttu-id="d9467-129">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9467-129">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="d9467-130">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d9467-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
