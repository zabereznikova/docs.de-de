---
title: ICorDebugModuleDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 706f392652c5cb868e09d4ee9fcb69c6d3d92d2a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965100"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="29201-102">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29201-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="29201-103">Erweitert die [icordebugdebugevent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) -Schnittstelle, um Ereignisse auf Modulebene zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="29201-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29201-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="29201-104">Methods</span></span>  
  
|<span data-ttu-id="29201-105">Methode</span><span class="sxs-lookup"><span data-stu-id="29201-105">Method</span></span>|<span data-ttu-id="29201-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29201-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29201-107">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="29201-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="29201-108">Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="29201-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29201-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29201-109">Remarks</span></span>  
 <span data-ttu-id="29201-110">Diese Schnittstelle wird von den Ereignis Typen [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) und [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) implementiert.</span><span class="sxs-lookup"><span data-stu-id="29201-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29201-111">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="29201-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="29201-112">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="29201-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29201-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="29201-113">Requirements</span></span>  
 <span data-ttu-id="29201-114">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29201-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29201-115">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="29201-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29201-116">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29201-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29201-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29201-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29201-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29201-118">See also</span></span>

- [<span data-ttu-id="29201-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="29201-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="29201-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="29201-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
