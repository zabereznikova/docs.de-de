---
title: ICorDebugStaticFieldSymbol-Schnittstelle
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0415e622ebba76d0af7d58fc3b59c4bdb47e0043
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619888"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="d607f-102">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d607f-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="d607f-103">Stellt die Debugsymbolinformationen für ein statisches Feld dar.</span><span class="sxs-lookup"><span data-stu-id="d607f-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d607f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d607f-104">Methods</span></span>  
  
|<span data-ttu-id="d607f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d607f-105">Method</span></span>|<span data-ttu-id="d607f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d607f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d607f-107">GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="d607f-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="d607f-108">Ruft die Adresse des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="d607f-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="d607f-109">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="d607f-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="d607f-110">Ruft den Namen des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="d607f-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="d607f-111">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="d607f-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="d607f-112">Ruft die Größe des statischen Felds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="d607f-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d607f-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d607f-113">Remarks</span></span>  
 <span data-ttu-id="d607f-114">Die `ICorDebugStaticFieldSymbol`-Schnittstelle wird verwendet, um Debugsymbolinformationen für ein statisches Feld abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d607f-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d607f-115">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d607f-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="d607f-116">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d607f-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d607f-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d607f-117">Requirements</span></span>  
 <span data-ttu-id="d607f-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d607f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d607f-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d607f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d607f-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d607f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d607f-121">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d607f-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d607f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d607f-122">See also</span></span>
- [<span data-ttu-id="d607f-123">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d607f-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="d607f-124">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d607f-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d607f-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d607f-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
