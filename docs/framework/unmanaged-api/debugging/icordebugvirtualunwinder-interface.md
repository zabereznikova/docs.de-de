---
title: ICorDebugVirtualUnwinder-Schnittstelle
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 065f71e45c2a56dbaa16a45f70958ca3dea80c48
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790822"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="01a76-102">ICorDebugVirtualUnwinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01a76-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="01a76-103">Stellt Methoden bereit, um die Stapelentladung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="01a76-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01a76-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="01a76-104">Methods</span></span>  
  
|<span data-ttu-id="01a76-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="01a76-105">Method</span></span>|<span data-ttu-id="01a76-106">-Name</span><span class="sxs-lookup"><span data-stu-id="01a76-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="01a76-107">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="01a76-107">GetContext Method</span></span>](icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="01a76-108">Ruft den aktuellen Kontext dieses Entladers ab.</span><span class="sxs-lookup"><span data-stu-id="01a76-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="01a76-109">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="01a76-109">Next Method</span></span>](icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="01a76-110">Wechselt zum Kontext eines Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="01a76-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01a76-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01a76-111">Remarks</span></span>  
 <span data-ttu-id="01a76-112">Die Elemente der `ICorDebugVirtualUnwinder`-Schnittstelle werden durch den Debugger implementiert, damit die Stapelentladung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="01a76-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01a76-113">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="01a76-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="01a76-114">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="01a76-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01a76-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01a76-115">Requirements</span></span>  
 <span data-ttu-id="01a76-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01a76-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01a76-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01a76-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01a76-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01a76-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01a76-119">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01a76-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01a76-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01a76-120">See also</span></span>

- [<span data-ttu-id="01a76-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="01a76-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="01a76-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="01a76-122">Debugging</span></span>](index.md)
