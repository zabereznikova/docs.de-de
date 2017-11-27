---
title: ICorDebugVirtualUnwinder-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d22fa926b300384b7f790468b1b3d0becafdb942
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="a01f6-102">ICorDebugVirtualUnwinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a01f6-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="a01f6-103">Stellt Methoden bereit, um die Stapelentladung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a01f6-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a01f6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a01f6-104">Methods</span></span>  
  
|<span data-ttu-id="a01f6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a01f6-105">Method</span></span>|<span data-ttu-id="a01f6-106">Name</span><span class="sxs-lookup"><span data-stu-id="a01f6-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="a01f6-107">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="a01f6-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="a01f6-108">Ruft den aktuellen Kontext dieses Entladers ab.</span><span class="sxs-lookup"><span data-stu-id="a01f6-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="a01f6-109">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="a01f6-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="a01f6-110">Wechselt zum Kontext eines Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="a01f6-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a01f6-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a01f6-111">Remarks</span></span>  
 <span data-ttu-id="a01f6-112">Die Elemente der `ICorDebugVirtualUnwinder`-Schnittstelle werden durch den Debugger implementiert, damit die Stapelentladung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a01f6-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a01f6-113">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a01f6-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="a01f6-114">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a01f6-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a01f6-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a01f6-115">Requirements</span></span>  
 <span data-ttu-id="a01f6-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a01f6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a01f6-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a01f6-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a01f6-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a01f6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a01f6-119">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a01f6-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a01f6-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a01f6-120">See Also</span></span>  
 [<span data-ttu-id="a01f6-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a01f6-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a01f6-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a01f6-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
