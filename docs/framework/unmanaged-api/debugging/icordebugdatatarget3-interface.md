---
title: ICorDebugDataTarget3-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 04e7b9a064d4a06a06b8a1518f06092ba79a3561
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783488"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="d8c5c-102">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c5c-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="d8c5c-103">Erweitert logisch die [ICorDebugDataTarget](icordebugdatatarget-interface.md) -Schnittstelle, um Informationen über geladene Module bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="d8c5c-104">-Methode</span><span class="sxs-lookup"><span data-stu-id="d8c5c-104">Method</span></span>  
  
|<span data-ttu-id="d8c5c-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="d8c5c-105">Method</span></span>|<span data-ttu-id="d8c5c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8c5c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8c5c-107">GetLoadedModules-Methode</span><span class="sxs-lookup"><span data-stu-id="d8c5c-107">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="d8c5c-108">Ruft eine Liste der Module ab, die bisher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8c5c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8c5c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8c5c-110">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="d8c5c-111">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d8c5c-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8c5c-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d8c5c-112">Requirements</span></span>  
 <span data-ttu-id="d8c5c-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8c5c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8c5c-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8c5c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8c5c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8c5c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8c5c-116">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8c5c-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8c5c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8c5c-117">See also</span></span>

- [<span data-ttu-id="d8c5c-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d8c5c-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d8c5c-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d8c5c-119">Debugging</span></span>](index.md)
