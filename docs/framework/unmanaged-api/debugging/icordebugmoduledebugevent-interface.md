---
title: ICorDebugModuleDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: a2c7eaa8a2c811c1696024d9af4b715cc49e7caa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792898"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="02556-102">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02556-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="02556-103">Erweitert die [icordebugdebugevent](icordebugdebugevent-interface.md) -Schnittstelle, um Ereignisse auf Modulebene zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="02556-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02556-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="02556-104">Methods</span></span>  
  
|<span data-ttu-id="02556-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="02556-105">Method</span></span>|<span data-ttu-id="02556-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02556-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02556-107">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="02556-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="02556-108">Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="02556-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02556-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02556-109">Remarks</span></span>  
 <span data-ttu-id="02556-110">Diese Schnittstelle wird von den Ereignis Typen [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) und [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) implementiert.</span><span class="sxs-lookup"><span data-stu-id="02556-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02556-111">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="02556-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="02556-112">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="02556-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02556-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02556-113">Requirements</span></span>  
 <span data-ttu-id="02556-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02556-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02556-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02556-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02556-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02556-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02556-117">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02556-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02556-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02556-118">See also</span></span>

- [<span data-ttu-id="02556-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="02556-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="02556-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="02556-120">Debugging</span></span>](index.md)
