---
title: ICorDebugMemoryBuffer-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 60f3b0c3230c524ca7d308d3cb80e50b0693715d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212333"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="f22e1-102">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f22e1-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="f22e1-103">Stellt einen In-Memory-Puffer dar.</span><span class="sxs-lookup"><span data-stu-id="f22e1-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f22e1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f22e1-104">Methods</span></span>  
  
|<span data-ttu-id="f22e1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f22e1-105">Method</span></span>|<span data-ttu-id="f22e1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f22e1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f22e1-107">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="f22e1-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="f22e1-108">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="f22e1-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="f22e1-109">GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="f22e1-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="f22e1-110">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="f22e1-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f22e1-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f22e1-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f22e1-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f22e1-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f22e1-113">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f22e1-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f22e1-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f22e1-114">Requirements</span></span>  
 <span data-ttu-id="f22e1-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f22e1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f22e1-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f22e1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f22e1-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f22e1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f22e1-118">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f22e1-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22e1-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f22e1-119">See also</span></span>

- [<span data-ttu-id="f22e1-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f22e1-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f22e1-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f22e1-121">Debugging</span></span>](index.md)
