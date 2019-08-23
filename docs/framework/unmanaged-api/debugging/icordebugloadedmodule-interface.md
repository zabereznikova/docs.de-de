---
title: ICorDebugLoadedModule-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9da6aba61382381fc25fe70615976cd0e744ee1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910005"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="cffd5-102">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cffd5-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="cffd5-103">Stellt Informationen zu einem geladenen Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="cffd5-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cffd5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="cffd5-104">Methods</span></span>  
  
|<span data-ttu-id="cffd5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="cffd5-105">Method</span></span>|<span data-ttu-id="cffd5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cffd5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cffd5-107">GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="cffd5-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="cffd5-108">Ruft die Basisadresse für das geladene Modul ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="cffd5-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="cffd5-109">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="cffd5-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="cffd5-110">Ruft den Namen des geladenen Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="cffd5-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="cffd5-111">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="cffd5-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="cffd5-112">Ruft die Größe des geladenen Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="cffd5-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cffd5-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cffd5-113">Remarks</span></span>  
 <span data-ttu-id="cffd5-114">Die `ICorDebugLoadedModule`-Schnittstelle wird von einem Debugger implementiert und von den CLR-Debugschnittstellen verwendet, um Informationen vom Debugger zum geladenen Modul zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cffd5-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cffd5-115">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cffd5-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="cffd5-116">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="cffd5-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cffd5-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cffd5-117">Requirements</span></span>  
 <span data-ttu-id="cffd5-118">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cffd5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cffd5-119">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="cffd5-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cffd5-120">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cffd5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cffd5-121">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cffd5-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cffd5-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cffd5-122">See also</span></span>

- [<span data-ttu-id="cffd5-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cffd5-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="cffd5-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="cffd5-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
