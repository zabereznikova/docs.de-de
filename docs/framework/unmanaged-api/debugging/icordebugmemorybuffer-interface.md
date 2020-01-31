---
title: ICorDebugMemoryBuffer-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: fa1bbca1e771cbc2b3475891862875b97b9e7f90
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793140"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="9cabb-102">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9cabb-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="9cabb-103">Stellt einen In-Memory-Puffer dar.</span><span class="sxs-lookup"><span data-stu-id="9cabb-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9cabb-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9cabb-104">Methods</span></span>  
  
|<span data-ttu-id="9cabb-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="9cabb-105">Method</span></span>|<span data-ttu-id="9cabb-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9cabb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9cabb-107">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="9cabb-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="9cabb-108">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="9cabb-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="9cabb-109">GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="9cabb-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="9cabb-110">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="9cabb-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cabb-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9cabb-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9cabb-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9cabb-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="9cabb-113">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9cabb-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cabb-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9cabb-114">Requirements</span></span>  
 <span data-ttu-id="9cabb-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cabb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cabb-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cabb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cabb-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cabb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cabb-118">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cabb-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cabb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cabb-119">See also</span></span>

- [<span data-ttu-id="9cabb-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9cabb-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9cabb-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="9cabb-121">Debugging</span></span>](index.md)
