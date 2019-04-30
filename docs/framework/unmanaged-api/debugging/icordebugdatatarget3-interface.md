---
title: ICorDebugDataTarget3-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3b0d67d390931cc92c0b6a1320f66545517cde3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965203"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="6430b-102">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6430b-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="6430b-103">Erweitert logisch die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle, um Informationen zu geladenen Modulen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6430b-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="6430b-104">Methode</span><span class="sxs-lookup"><span data-stu-id="6430b-104">Method</span></span>  
  
|<span data-ttu-id="6430b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6430b-105">Method</span></span>|<span data-ttu-id="6430b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6430b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6430b-107">GetLoadedModules-Methode</span><span class="sxs-lookup"><span data-stu-id="6430b-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="6430b-108">Ruft eine Liste der Module ab, die bisher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="6430b-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6430b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6430b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6430b-110">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6430b-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="6430b-111">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6430b-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6430b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6430b-112">Requirements</span></span>  
 <span data-ttu-id="6430b-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6430b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6430b-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6430b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6430b-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6430b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6430b-116">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6430b-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6430b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6430b-117">See also</span></span>

- [<span data-ttu-id="6430b-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6430b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6430b-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6430b-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
