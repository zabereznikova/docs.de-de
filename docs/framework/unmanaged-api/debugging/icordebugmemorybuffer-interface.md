---
title: ICorDebugMemoryBuffer-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 019fc3db0f09dc9e5cb22ba3cf012605bf865d6b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574858"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="6651f-102">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6651f-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="6651f-103">Stellt einen In-Memory-Puffer dar.</span><span class="sxs-lookup"><span data-stu-id="6651f-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6651f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6651f-104">Methods</span></span>  
  
|<span data-ttu-id="6651f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6651f-105">Method</span></span>|<span data-ttu-id="6651f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6651f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6651f-107">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="6651f-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="6651f-108">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="6651f-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="6651f-109">GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="6651f-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="6651f-110">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="6651f-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6651f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6651f-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6651f-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6651f-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="6651f-113">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6651f-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6651f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6651f-114">Requirements</span></span>  
 <span data-ttu-id="6651f-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6651f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6651f-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6651f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6651f-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6651f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6651f-118">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6651f-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6651f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6651f-119">See also</span></span>
- [<span data-ttu-id="6651f-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6651f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6651f-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6651f-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
