---
title: ICorDebugVirtualUnwinder-Schnittstelle
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639cfc514d2a206f0de72db4b0bac02b53305ae3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083399"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="2f837-102">ICorDebugVirtualUnwinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f837-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="2f837-103">Stellt Methoden bereit, um die Stapelentladung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2f837-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f837-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2f837-104">Methods</span></span>  
  
|<span data-ttu-id="2f837-105">Methode</span><span class="sxs-lookup"><span data-stu-id="2f837-105">Method</span></span>|<span data-ttu-id="2f837-106">Name</span><span class="sxs-lookup"><span data-stu-id="2f837-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="2f837-107">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="2f837-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="2f837-108">Ruft den aktuellen Kontext dieses Entladers ab.</span><span class="sxs-lookup"><span data-stu-id="2f837-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="2f837-109">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="2f837-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="2f837-110">Wechselt zum Kontext eines Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="2f837-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f837-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f837-111">Remarks</span></span>  
 <span data-ttu-id="2f837-112">Die Elemente der `ICorDebugVirtualUnwinder`-Schnittstelle werden durch den Debugger implementiert, damit die Stapelentladung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="2f837-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f837-113">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2f837-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="2f837-114">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2f837-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f837-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f837-115">Requirements</span></span>  
 <span data-ttu-id="2f837-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f837-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f837-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f837-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f837-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f837-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2f837-119">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2f837-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2f837-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f837-120">See also</span></span>

- [<span data-ttu-id="2f837-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2f837-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2f837-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2f837-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
