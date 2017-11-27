---
title: ICorDebugLoadedModule-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5cdc89ec81d76a3ce7d39a53e097745d6c9822f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="4ddee-102">ICorDebugLoadedModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4ddee-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="4ddee-103">Stellt Informationen zu einem geladenen Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="4ddee-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ddee-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4ddee-104">Methods</span></span>  
  
|<span data-ttu-id="4ddee-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4ddee-105">Method</span></span>|<span data-ttu-id="4ddee-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ddee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ddee-107">GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="4ddee-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="4ddee-108">Ruft die Basisadresse für das geladene Modul ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="4ddee-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="4ddee-109">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="4ddee-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="4ddee-110">Ruft den Namen des geladenen Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="4ddee-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="4ddee-111">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="4ddee-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="4ddee-112">Ruft die Größe des geladenen Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="4ddee-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ddee-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4ddee-113">Remarks</span></span>  
 <span data-ttu-id="4ddee-114">Die `ICorDebugLoadedModule`-Schnittstelle wird von einem Debugger implementiert und von den CLR-Debugschnittstellen verwendet, um Informationen vom Debugger zum geladenen Modul zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4ddee-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ddee-115">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4ddee-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="4ddee-116">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4ddee-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ddee-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4ddee-117">Requirements</span></span>  
 <span data-ttu-id="4ddee-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ddee-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ddee-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ddee-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ddee-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ddee-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ddee-121">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ddee-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ddee-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ddee-122">See Also</span></span>  
 [<span data-ttu-id="4ddee-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4ddee-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4ddee-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4ddee-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
