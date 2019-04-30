---
title: ICorDebugLoadedModule-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e91dda9cbc5957768e98db2b2a9e1026d94c03e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946286"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="a6490-102">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a6490-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="a6490-103">Stellt Informationen zu einem geladenen Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="a6490-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6490-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a6490-104">Methods</span></span>  
  
|<span data-ttu-id="a6490-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a6490-105">Method</span></span>|<span data-ttu-id="a6490-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6490-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6490-107">GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="a6490-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="a6490-108">Ruft die Basisadresse für das geladene Modul ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="a6490-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="a6490-109">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="a6490-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="a6490-110">Ruft den Namen des geladenen Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="a6490-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="a6490-111">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="a6490-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="a6490-112">Ruft die Größe des geladenen Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="a6490-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6490-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6490-113">Remarks</span></span>  
 <span data-ttu-id="a6490-114">Die `ICorDebugLoadedModule`-Schnittstelle wird von einem Debugger implementiert und von den CLR-Debugschnittstellen verwendet, um Informationen vom Debugger zum geladenen Modul zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a6490-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6490-115">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a6490-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="a6490-116">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a6490-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6490-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a6490-117">Requirements</span></span>  
 <span data-ttu-id="a6490-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6490-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6490-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6490-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6490-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6490-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6490-121">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6490-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6490-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6490-122">See also</span></span>

- [<span data-ttu-id="a6490-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a6490-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a6490-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a6490-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
