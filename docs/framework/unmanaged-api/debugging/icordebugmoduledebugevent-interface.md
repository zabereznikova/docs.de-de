---
title: ICorDebugModuleDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: ec6bad730d807b9a36ce5bba1c6f5d80da375f6d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213332"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="f2622-102">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2622-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="f2622-103">Erweitert die [icordebugdebugevent](icordebugdebugevent-interface.md) -Schnittstelle, um Ereignisse auf Modulebene zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f2622-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2622-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f2622-104">Methods</span></span>  
  
|<span data-ttu-id="f2622-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f2622-105">Method</span></span>|<span data-ttu-id="f2622-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2622-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2622-107">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="f2622-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="f2622-108">Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="f2622-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2622-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2622-109">Remarks</span></span>  
 <span data-ttu-id="f2622-110">Diese Schnittstelle wird von den Ereignis Typen [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) und [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) implementiert.</span><span class="sxs-lookup"><span data-stu-id="f2622-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2622-111">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f2622-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="f2622-112">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f2622-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2622-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f2622-113">Requirements</span></span>  
 <span data-ttu-id="f2622-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2622-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2622-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2622-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2622-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2622-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2622-117">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2622-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2622-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2622-118">See also</span></span>

- [<span data-ttu-id="f2622-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f2622-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f2622-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f2622-120">Debugging</span></span>](index.md)
