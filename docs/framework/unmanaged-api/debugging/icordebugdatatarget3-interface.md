---
title: ICorDebugDataTarget3-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3b0d67d390931cc92c0b6a1320f66545517cde3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223042"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="41d93-102">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41d93-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="41d93-103">Erweitert logisch die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle, um Informationen zu geladenen Modulen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="41d93-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="41d93-104">Methode</span><span class="sxs-lookup"><span data-stu-id="41d93-104">Method</span></span>  
  
|<span data-ttu-id="41d93-105">Methode</span><span class="sxs-lookup"><span data-stu-id="41d93-105">Method</span></span>|<span data-ttu-id="41d93-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41d93-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41d93-107">GetLoadedModules-Methode</span><span class="sxs-lookup"><span data-stu-id="41d93-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="41d93-108">Ruft eine Liste der Module ab, die bisher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="41d93-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41d93-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41d93-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41d93-110">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="41d93-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="41d93-111">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="41d93-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41d93-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41d93-112">Requirements</span></span>  
 <span data-ttu-id="41d93-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41d93-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41d93-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41d93-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41d93-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41d93-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="41d93-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="41d93-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="41d93-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41d93-117">See also</span></span>

- [<span data-ttu-id="41d93-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="41d93-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="41d93-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="41d93-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
