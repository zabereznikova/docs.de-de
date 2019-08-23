---
title: ICorDebugDataTarget3-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee94e25201dee4999fd5acb2be44a80454e9efbf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911417"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="28bf8-102">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28bf8-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="28bf8-103">Erweitert logisch die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) -Schnittstelle, um Informationen über geladene Module bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="28bf8-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="28bf8-104">Methode</span><span class="sxs-lookup"><span data-stu-id="28bf8-104">Method</span></span>  
  
|<span data-ttu-id="28bf8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="28bf8-105">Method</span></span>|<span data-ttu-id="28bf8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28bf8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28bf8-107">GetLoadedModules-Methode</span><span class="sxs-lookup"><span data-stu-id="28bf8-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="28bf8-108">Ruft eine Liste der Module ab, die bisher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="28bf8-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28bf8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28bf8-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="28bf8-110">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="28bf8-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="28bf8-111">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="28bf8-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28bf8-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28bf8-112">Requirements</span></span>  
 <span data-ttu-id="28bf8-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28bf8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28bf8-114">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="28bf8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28bf8-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28bf8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28bf8-116">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28bf8-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28bf8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28bf8-117">See also</span></span>

- [<span data-ttu-id="28bf8-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="28bf8-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="28bf8-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="28bf8-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
