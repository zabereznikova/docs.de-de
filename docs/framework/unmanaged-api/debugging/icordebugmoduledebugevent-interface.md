---
title: ICorDebugModuleDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: 62d419a193cff000e1dd748d0cbb6b61775a81aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695815"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="ed85d-102">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed85d-102">ICorDebugModuleDebugEvent Interface</span></span>

<span data-ttu-id="ed85d-103">Erweitert die [icordebugdebugevent](icordebugdebugevent-interface.md) -Schnittstelle, um Ereignisse auf Modulebene zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ed85d-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed85d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ed85d-104">Methods</span></span>  
  
|<span data-ttu-id="ed85d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ed85d-105">Method</span></span>|<span data-ttu-id="ed85d-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ed85d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed85d-107">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="ed85d-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="ed85d-108">Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ed85d-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed85d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed85d-109">Remarks</span></span>  

 <span data-ttu-id="ed85d-110">Diese Schnittstelle wird von den Ereignis Typen [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) und [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) implementiert.</span><span class="sxs-lookup"><span data-stu-id="ed85d-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed85d-111">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ed85d-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="ed85d-112">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ed85d-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed85d-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ed85d-113">Requirements</span></span>  

 <span data-ttu-id="ed85d-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed85d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed85d-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed85d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed85d-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed85d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed85d-117">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed85d-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed85d-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed85d-118">See also</span></span>

- [<span data-ttu-id="ed85d-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ed85d-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ed85d-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ed85d-120">Debugging</span></span>](index.md)
