---
title: ICorDebugMemoryBuffer-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a1bc8e1206b8a82127645362cfe0a124074271c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414402"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="b2543-102">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b2543-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="b2543-103">Stellt einen In-Memory-Puffer dar.</span><span class="sxs-lookup"><span data-stu-id="b2543-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2543-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b2543-104">Methods</span></span>  
  
|<span data-ttu-id="b2543-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b2543-105">Method</span></span>|<span data-ttu-id="b2543-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2543-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2543-107">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="b2543-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="b2543-108">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="b2543-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="b2543-109">GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="b2543-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="b2543-110">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="b2543-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2543-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2543-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2543-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b2543-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="b2543-113">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b2543-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2543-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b2543-114">Requirements</span></span>  
 <span data-ttu-id="b2543-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2543-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2543-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2543-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2543-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2543-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2543-118">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2543-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2543-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2543-119">See Also</span></span>  
 [<span data-ttu-id="b2543-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b2543-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b2543-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b2543-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
