---
title: ICorDebugStaticFieldSymbol-Schnittstelle
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 382f3fc9377c25379809badac0bc580c3593cbde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103895"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="5af4e-102">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5af4e-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="5af4e-103">Stellt die Debugsymbolinformationen für ein statisches Feld dar.</span><span class="sxs-lookup"><span data-stu-id="5af4e-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5af4e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5af4e-104">Methods</span></span>  
  
|<span data-ttu-id="5af4e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5af4e-105">Method</span></span>|<span data-ttu-id="5af4e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5af4e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5af4e-107">GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="5af4e-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="5af4e-108">Ruft die Adresse des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="5af4e-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="5af4e-109">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="5af4e-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="5af4e-110">Ruft den Namen des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="5af4e-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="5af4e-111">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="5af4e-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="5af4e-112">Ruft die Größe des statischen Felds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="5af4e-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5af4e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5af4e-113">Remarks</span></span>  
 <span data-ttu-id="5af4e-114">Die `ICorDebugStaticFieldSymbol`-Schnittstelle wird verwendet, um Debugsymbolinformationen für ein statisches Feld abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5af4e-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5af4e-115">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5af4e-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="5af4e-116">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5af4e-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5af4e-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5af4e-117">Requirements</span></span>  
 <span data-ttu-id="5af4e-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5af4e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5af4e-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5af4e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5af4e-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5af4e-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5af4e-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5af4e-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5af4e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5af4e-122">See also</span></span>

- [<span data-ttu-id="5af4e-123">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5af4e-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="5af4e-124">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5af4e-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5af4e-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5af4e-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
