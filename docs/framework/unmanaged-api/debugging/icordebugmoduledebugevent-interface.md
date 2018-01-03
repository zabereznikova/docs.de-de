---
title: ICorDebugModuleDebugEvent-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86cf571180b2df15077547fac3d5dd058dbee83b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="3bebd-102">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bebd-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="3bebd-103">Erweitert die [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) -Schnittstelle zur Unterstützung der Ereignisse auf Modulebene.</span><span class="sxs-lookup"><span data-stu-id="3bebd-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3bebd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3bebd-104">Methods</span></span>  
  
|<span data-ttu-id="3bebd-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3bebd-105">Method</span></span>|<span data-ttu-id="3bebd-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bebd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3bebd-107">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="3bebd-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="3bebd-108">Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="3bebd-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bebd-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3bebd-109">Remarks</span></span>  
 <span data-ttu-id="3bebd-110">Die [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) und [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) -Ereignistyp implementieren diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3bebd-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bebd-111">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3bebd-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="3bebd-112">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3bebd-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bebd-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3bebd-113">Requirements</span></span>  
 <span data-ttu-id="3bebd-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bebd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bebd-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3bebd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3bebd-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bebd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bebd-117">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bebd-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bebd-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bebd-118">See Also</span></span>  
 [<span data-ttu-id="3bebd-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3bebd-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="3bebd-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="3bebd-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
