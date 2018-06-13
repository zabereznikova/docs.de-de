---
title: ICorDebugExceptionDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cedbbf2067a94aa73e40bd4651fc97b72aa9afef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416301"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="ca068-102">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca068-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="ca068-103">Erweitert die [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) Schnittstelle, um die Unterstützung von Ausnahmeereignissen.</span><span class="sxs-lookup"><span data-stu-id="ca068-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca068-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ca068-104">Methods</span></span>  
  
|<span data-ttu-id="ca068-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ca068-105">Method</span></span>|<span data-ttu-id="ca068-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca068-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca068-107">GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="ca068-107">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="ca068-108">Ruft ein Flag ab, das angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ca068-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="ca068-109">GetNativeIP-Methode</span><span class="sxs-lookup"><span data-stu-id="ca068-109">GetNativeIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="ca068-110">Ruft den systemeigenen Schnittstellenzeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="ca068-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="ca068-111">GetStackPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="ca068-111">GetStackPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="ca068-112">Ruft den Stapelzeiger für dieses Ausnahmedebugereignis ab.</span><span class="sxs-lookup"><span data-stu-id="ca068-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca068-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca068-113">Remarks</span></span>  
 <span data-ttu-id="ca068-114">Die `ICorDebugExceptionDebugEvent`-Schnittstelle wird durch die folgenden Ereignistypen implementiert:</span><span class="sxs-lookup"><span data-stu-id="ca068-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
-   [<span data-ttu-id="ca068-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="ca068-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [<span data-ttu-id="ca068-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="ca068-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [<span data-ttu-id="ca068-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="ca068-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [<span data-ttu-id="ca068-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="ca068-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
>  <span data-ttu-id="ca068-119">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ca068-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="ca068-120">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ca068-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca068-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca068-121">Requirements</span></span>  
 <span data-ttu-id="ca068-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca068-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca068-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca068-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca068-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca068-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca068-125">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca068-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca068-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca068-126">See Also</span></span>  
 [<span data-ttu-id="ca068-127">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ca068-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ca068-128">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ca068-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
