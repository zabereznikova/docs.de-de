---
title: ICorDebugVirtualUnwinder-Schnittstelle
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9db6b83e2feedd761b95dec455213051e37366e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684144"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="97fdc-102">ICorDebugVirtualUnwinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97fdc-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="97fdc-103">Stellt Methoden bereit, um die Stapelentladung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="97fdc-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97fdc-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="97fdc-104">Methods</span></span>  
  
|<span data-ttu-id="97fdc-105">Methode</span><span class="sxs-lookup"><span data-stu-id="97fdc-105">Method</span></span>|<span data-ttu-id="97fdc-106">name</span><span class="sxs-lookup"><span data-stu-id="97fdc-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="97fdc-107">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="97fdc-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="97fdc-108">Ruft den aktuellen Kontext dieses Entladers ab.</span><span class="sxs-lookup"><span data-stu-id="97fdc-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="97fdc-109">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="97fdc-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="97fdc-110">Wechselt zum Kontext eines Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="97fdc-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97fdc-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97fdc-111">Remarks</span></span>  
 <span data-ttu-id="97fdc-112">Die Elemente der `ICorDebugVirtualUnwinder`-Schnittstelle werden durch den Debugger implementiert, damit die Stapelentladung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="97fdc-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97fdc-113">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="97fdc-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="97fdc-114">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="97fdc-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97fdc-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97fdc-115">Requirements</span></span>  
 <span data-ttu-id="97fdc-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97fdc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97fdc-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97fdc-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97fdc-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97fdc-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97fdc-119">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97fdc-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97fdc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97fdc-120">See also</span></span>
- [<span data-ttu-id="97fdc-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="97fdc-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="97fdc-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="97fdc-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
