---
title: ICorDebugInstanceFieldSymbol-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fbf3f07f5669c4fcafa4d3cc4119fc715539651d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="71a4c-102">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71a4c-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="71a4c-103">Stellt die Debugsymbolinformationen für ein Instanzfeld dar.</span><span class="sxs-lookup"><span data-stu-id="71a4c-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71a4c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="71a4c-104">Methods</span></span>  
  
|<span data-ttu-id="71a4c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="71a4c-105">Method</span></span>|<span data-ttu-id="71a4c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71a4c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71a4c-107">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="71a4c-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="71a4c-108">Ruft den Namen des Instanzfelds ab.</span><span class="sxs-lookup"><span data-stu-id="71a4c-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="71a4c-109">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="71a4c-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="71a4c-110">Ruft den Offset dieses Instanzenfelds in der übergeordneten Klasse in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="71a4c-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="71a4c-111">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="71a4c-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="71a4c-112">Ruft die Größe des Instanzfelds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="71a4c-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71a4c-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71a4c-113">Remarks</span></span>  
 <span data-ttu-id="71a4c-114">Die `ICorDebugInstanceFieldSymbol`-Schnittstelle wird verwendet, um Debugsymbolinformationen für ein Instanzfeld abzurufen.</span><span class="sxs-lookup"><span data-stu-id="71a4c-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71a4c-115">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="71a4c-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="71a4c-116">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="71a4c-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71a4c-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71a4c-117">Requirements</span></span>  
 <span data-ttu-id="71a4c-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71a4c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71a4c-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71a4c-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71a4c-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71a4c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71a4c-121">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71a4c-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a4c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71a4c-122">See Also</span></span>  
 [<span data-ttu-id="71a4c-123">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71a4c-123">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="71a4c-124">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="71a4c-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="71a4c-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="71a4c-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
