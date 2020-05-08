---
title: ICorDebugDataTarget3-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 57ef9b567d57c77c523ca6daefcf80b1d7de66d1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976407"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="4da8f-102">ICorDebugDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4da8f-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="4da8f-103">Erweitert logisch die [ICorDebugDataTarget](icordebugdatatarget-interface.md) -Schnittstelle, um Informationen über geladene Module bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4da8f-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="4da8f-104">Methode</span><span class="sxs-lookup"><span data-stu-id="4da8f-104">Method</span></span>  
  
|<span data-ttu-id="4da8f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4da8f-105">Method</span></span>|<span data-ttu-id="4da8f-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4da8f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4da8f-107">GetLoadedModules-Methode</span><span class="sxs-lookup"><span data-stu-id="4da8f-107">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="4da8f-108">Ruft eine Liste der Module ab, die bisher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="4da8f-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4da8f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4da8f-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4da8f-110">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4da8f-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="4da8f-111">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4da8f-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4da8f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4da8f-112">Requirements</span></span>  
 <span data-ttu-id="4da8f-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4da8f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4da8f-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4da8f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4da8f-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4da8f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4da8f-116">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4da8f-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da8f-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4da8f-117">See also</span></span>

- [<span data-ttu-id="4da8f-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4da8f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4da8f-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4da8f-119">Debugging</span></span>](index.md)
