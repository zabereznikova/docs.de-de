---
title: ICorDebugExceptionDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: dfa65aa1b63c996068e75ff1165111d5fcfe77eb
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976004"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="28db2-102">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28db2-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="28db2-103">Erweitert die [icordebugdebugevent](icordebugdebugevent-interface.md) -Schnittstelle zur Unterstützung von Ausnahme Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="28db2-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28db2-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="28db2-104">Methods</span></span>  
  
|<span data-ttu-id="28db2-105">Methode</span><span class="sxs-lookup"><span data-stu-id="28db2-105">Method</span></span>|<span data-ttu-id="28db2-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="28db2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28db2-107">GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="28db2-107">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="28db2-108">Ruft ein Flag ab, das angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="28db2-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="28db2-109">GetNativeIP-Methode</span><span class="sxs-lookup"><span data-stu-id="28db2-109">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="28db2-110">Ruft den systemeigenen Schnittstellenzeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="28db2-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="28db2-111">GetStackPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="28db2-111">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="28db2-112">Ruft den Stapelzeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="28db2-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28db2-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28db2-113">Remarks</span></span>  
 <span data-ttu-id="28db2-114">Die `ICorDebugExceptionDebugEvent`-Schnittstelle wird durch die folgenden Ereignistypen implementiert:</span><span class="sxs-lookup"><span data-stu-id="28db2-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="28db2-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="28db2-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="28db2-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="28db2-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="28db2-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="28db2-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="28db2-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="28db2-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="28db2-119">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="28db2-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="28db2-120">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28db2-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28db2-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28db2-121">Requirements</span></span>  
 <span data-ttu-id="28db2-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28db2-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28db2-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28db2-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28db2-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28db2-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28db2-125">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28db2-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28db2-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28db2-126">See also</span></span>

- [<span data-ttu-id="28db2-127">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="28db2-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="28db2-128">Debuggen</span><span class="sxs-lookup"><span data-stu-id="28db2-128">Debugging</span></span>](index.md)
