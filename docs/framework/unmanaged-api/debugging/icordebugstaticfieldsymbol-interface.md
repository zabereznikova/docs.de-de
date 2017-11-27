---
title: ICorDebugStaticFieldSymbol-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b747d2d43fd7ff4dc901dff14277dbce9606497f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="4949a-102">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4949a-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="4949a-103">Stellt die Debugsymbolinformationen für ein statisches Feld dar.</span><span class="sxs-lookup"><span data-stu-id="4949a-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4949a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4949a-104">Methods</span></span>  
  
|<span data-ttu-id="4949a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4949a-105">Method</span></span>|<span data-ttu-id="4949a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4949a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4949a-107">GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="4949a-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="4949a-108">Ruft die Adresse des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="4949a-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="4949a-109">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="4949a-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="4949a-110">Ruft den Namen des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="4949a-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="4949a-111">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="4949a-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="4949a-112">Ruft die Größe des statischen Felds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="4949a-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4949a-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4949a-113">Remarks</span></span>  
 <span data-ttu-id="4949a-114">Die `ICorDebugStaticFieldSymbol`-Schnittstelle wird verwendet, um Debugsymbolinformationen für ein statisches Feld abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4949a-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4949a-115">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4949a-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="4949a-116">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4949a-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4949a-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4949a-117">Requirements</span></span>  
 <span data-ttu-id="4949a-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4949a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4949a-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4949a-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4949a-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4949a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4949a-121">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4949a-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4949a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4949a-122">See Also</span></span>  
 [<span data-ttu-id="4949a-123">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4949a-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="4949a-124">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4949a-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4949a-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4949a-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
