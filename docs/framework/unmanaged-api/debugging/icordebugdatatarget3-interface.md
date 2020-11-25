---
title: ICorDebugDataTarget3-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: e219c703ce2d8bb42f824a8892991f6803e6ef9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713729"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="aa436-102">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa436-102">ICorDebugDataTarget3 Interface</span></span>

<span data-ttu-id="aa436-103">Erweitert logisch die [ICorDebugDataTarget](icordebugdatatarget-interface.md) -Schnittstelle, um Informationen über geladene Module bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="aa436-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="aa436-104">Methode</span><span class="sxs-lookup"><span data-stu-id="aa436-104">Method</span></span>  
  
|<span data-ttu-id="aa436-105">Methode</span><span class="sxs-lookup"><span data-stu-id="aa436-105">Method</span></span>|<span data-ttu-id="aa436-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="aa436-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa436-107">GetLoadedModules-Methode</span><span class="sxs-lookup"><span data-stu-id="aa436-107">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="aa436-108">Ruft eine Liste der Module ab, die bisher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="aa436-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa436-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa436-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa436-110">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="aa436-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="aa436-111">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="aa436-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa436-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="aa436-112">Requirements</span></span>  

 <span data-ttu-id="aa436-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa436-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa436-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa436-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa436-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa436-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa436-116">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa436-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa436-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa436-117">See also</span></span>

- [<span data-ttu-id="aa436-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="aa436-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="aa436-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="aa436-119">Debugging</span></span>](index.md)
