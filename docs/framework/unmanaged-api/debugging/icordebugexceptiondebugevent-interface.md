---
title: ICorDebugExceptionDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: c280852d421742cf9e8c2f8dcaa9c0f588f8537b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697388"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="e1e3b-102">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e1e3b-102">ICorDebugExceptionDebugEvent Interface</span></span>

<span data-ttu-id="e1e3b-103">Erweitert die [icordebugdebugevent](icordebugdebugevent-interface.md) -Schnittstelle zur Unterstützung von Ausnahme Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1e3b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e1e3b-104">Methods</span></span>  
  
|<span data-ttu-id="e1e3b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e1e3b-105">Method</span></span>|<span data-ttu-id="e1e3b-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1e3b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1e3b-107">GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="e1e3b-107">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="e1e3b-108">Ruft ein Flag ab, das angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="e1e3b-109">GetNativeIP-Methode</span><span class="sxs-lookup"><span data-stu-id="e1e3b-109">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="e1e3b-110">Ruft den systemeigenen Schnittstellenzeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="e1e3b-111">GetStackPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="e1e3b-111">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="e1e3b-112">Ruft den Stapelzeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1e3b-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1e3b-113">Remarks</span></span>  

 <span data-ttu-id="e1e3b-114">Die `ICorDebugExceptionDebugEvent`-Schnittstelle wird durch die folgenden Ereignistypen implementiert:</span><span class="sxs-lookup"><span data-stu-id="e1e3b-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="e1e3b-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e1e3b-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="e1e3b-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e1e3b-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="e1e3b-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="e1e3b-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="e1e3b-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="e1e3b-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="e1e3b-119">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="e1e3b-120">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1e3b-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e1e3b-121">Requirements</span></span>  

 <span data-ttu-id="e1e3b-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1e3b-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1e3b-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1e3b-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1e3b-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1e3b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1e3b-125">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1e3b-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e3b-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1e3b-126">See also</span></span>

- [<span data-ttu-id="e1e3b-127">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e1e3b-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e1e3b-128">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e1e3b-128">Debugging</span></span>](index.md)
