---
title: ICorDebugVirtualUnwinder-Schnittstelle
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 532052aa4f869861fbdb40ba0126bfd800eba942
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121874"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="0f7ac-102">ICorDebugVirtualUnwinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f7ac-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="0f7ac-103">Stellt Methoden bereit, um die Stapelentladung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0f7ac-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0f7ac-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0f7ac-104">Methods</span></span>  
  
|<span data-ttu-id="0f7ac-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0f7ac-105">Method</span></span>|<span data-ttu-id="0f7ac-106">-Name</span><span class="sxs-lookup"><span data-stu-id="0f7ac-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="0f7ac-107">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="0f7ac-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="0f7ac-108">Ruft den aktuellen Kontext dieses Entladers ab.</span><span class="sxs-lookup"><span data-stu-id="0f7ac-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="0f7ac-109">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="0f7ac-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="0f7ac-110">Wechselt zum Kontext eines Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="0f7ac-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f7ac-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f7ac-111">Remarks</span></span>  
 <span data-ttu-id="0f7ac-112">Die Elemente der `ICorDebugVirtualUnwinder`-Schnittstelle werden durch den Debugger implementiert, damit die Stapelentladung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0f7ac-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f7ac-113">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0f7ac-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="0f7ac-114">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0f7ac-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f7ac-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f7ac-115">Requirements</span></span>  
 <span data-ttu-id="0f7ac-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f7ac-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f7ac-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f7ac-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f7ac-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f7ac-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f7ac-119">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f7ac-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f7ac-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f7ac-120">See also</span></span>

- [<span data-ttu-id="0f7ac-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0f7ac-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0f7ac-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="0f7ac-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
