---
title: ICorDebugMemoryBuffer-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80002d064c48a90236a64a3d0a56fab5877cf411
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="07df9-102">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07df9-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="07df9-103">Stellt einen In-Memory-Puffer dar.</span><span class="sxs-lookup"><span data-stu-id="07df9-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07df9-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="07df9-104">Methods</span></span>  
  
|<span data-ttu-id="07df9-105">Methode</span><span class="sxs-lookup"><span data-stu-id="07df9-105">Method</span></span>|<span data-ttu-id="07df9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07df9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07df9-107">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="07df9-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="07df9-108">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="07df9-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="07df9-109">GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="07df9-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="07df9-110">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="07df9-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07df9-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07df9-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07df9-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="07df9-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="07df9-113">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="07df9-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07df9-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="07df9-114">Requirements</span></span>  
 <span data-ttu-id="07df9-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07df9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07df9-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07df9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07df9-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07df9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07df9-118">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07df9-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07df9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07df9-119">See Also</span></span>  
 [<span data-ttu-id="07df9-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="07df9-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="07df9-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="07df9-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
