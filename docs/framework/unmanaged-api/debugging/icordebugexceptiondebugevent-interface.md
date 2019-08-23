---
title: ICorDebugExceptionDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 522bccb4a424da620063995d02ae15d09ecbf2fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929882"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="57367-102">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57367-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="57367-103">Erweitert die [icordebugdebugevent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) -Schnittstelle zur Unterstützung von Ausnahme Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="57367-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57367-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="57367-104">Methods</span></span>  
  
|<span data-ttu-id="57367-105">Methode</span><span class="sxs-lookup"><span data-stu-id="57367-105">Method</span></span>|<span data-ttu-id="57367-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57367-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57367-107">GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="57367-107">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="57367-108">Ruft ein Flag ab, das angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="57367-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="57367-109">GetNativeIP-Methode</span><span class="sxs-lookup"><span data-stu-id="57367-109">GetNativeIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="57367-110">Ruft den systemeigenen Schnittstellenzeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="57367-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="57367-111">GetStackPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="57367-111">GetStackPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="57367-112">Ruft den Stapelzeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="57367-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57367-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57367-113">Remarks</span></span>  
 <span data-ttu-id="57367-114">Die `ICorDebugExceptionDebugEvent`-Schnittstelle wird durch die folgenden Ereignistypen implementiert:</span><span class="sxs-lookup"><span data-stu-id="57367-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="57367-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="57367-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="57367-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="57367-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="57367-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="57367-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="57367-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="57367-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="57367-119">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="57367-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="57367-120">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="57367-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57367-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57367-121">Requirements</span></span>  
 <span data-ttu-id="57367-122">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57367-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57367-123">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="57367-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57367-124">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57367-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57367-125">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57367-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57367-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57367-126">See also</span></span>

- [<span data-ttu-id="57367-127">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="57367-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="57367-128">Debuggen</span><span class="sxs-lookup"><span data-stu-id="57367-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
