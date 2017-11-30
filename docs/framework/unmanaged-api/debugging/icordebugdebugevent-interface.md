---
title: ICorDebugDebugEvent-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b4422b165f06b60dedff95fc3de58e5627db7fac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="fb3aa-102">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb3aa-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="fb3aa-103">Definiert die Basisschnittstelle, von der alle `ICorDebug` Debug-Ereignisse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="fb3aa-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fb3aa-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fb3aa-104">Methods</span></span>  
  
|<span data-ttu-id="fb3aa-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fb3aa-105">Method</span></span>|<span data-ttu-id="fb3aa-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb3aa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb3aa-107">GetEventKind-Methode</span><span class="sxs-lookup"><span data-stu-id="fb3aa-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="fb3aa-108">Gibt an, welche Art von Ereignis dieses `ICorDebugDebugEvent`-Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="fb3aa-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="fb3aa-109">GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="fb3aa-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="fb3aa-110">Ruft den Thread auf, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fb3aa-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb3aa-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb3aa-111">Remarks</span></span>  
 <span data-ttu-id="fb3aa-112">Die folgenden Schnittstellen sind aus der `ICorDebugDebugEvent`-Schnittstelle abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="fb3aa-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
-   [<span data-ttu-id="fb3aa-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="fb3aa-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
-   [<span data-ttu-id="fb3aa-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="fb3aa-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="fb3aa-115">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fb3aa-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="fb3aa-116">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fb3aa-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb3aa-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb3aa-117">Requirements</span></span>  
 <span data-ttu-id="fb3aa-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb3aa-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb3aa-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb3aa-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb3aa-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb3aa-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb3aa-121">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb3aa-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb3aa-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb3aa-122">See Also</span></span>  
 [<span data-ttu-id="fb3aa-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fb3aa-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="fb3aa-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fb3aa-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
