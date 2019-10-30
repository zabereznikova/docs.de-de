---
title: ICorDebugModuleDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: cca181c6af6db9f35ff7913e045a30e37e07a5e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110247"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="fd15d-102">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd15d-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="fd15d-103">Erweitert die [icordebugdebugevent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) -Schnittstelle, um Ereignisse auf Modulebene zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fd15d-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd15d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fd15d-104">Methods</span></span>  
  
|<span data-ttu-id="fd15d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fd15d-105">Method</span></span>|<span data-ttu-id="fd15d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd15d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd15d-107">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="fd15d-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="fd15d-108">Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="fd15d-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd15d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd15d-109">Remarks</span></span>  
 <span data-ttu-id="fd15d-110">Diese Schnittstelle wird von den Ereignis Typen [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) und [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) implementiert.</span><span class="sxs-lookup"><span data-stu-id="fd15d-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd15d-111">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fd15d-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="fd15d-112">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fd15d-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd15d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd15d-113">Requirements</span></span>  
 <span data-ttu-id="fd15d-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd15d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd15d-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd15d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd15d-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd15d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd15d-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd15d-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd15d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd15d-118">See also</span></span>

- [<span data-ttu-id="fd15d-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fd15d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fd15d-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fd15d-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
