---
title: ICorDebugMemoryBuffer-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 2765852309401d2aa30f91b506ba55156cd8a3e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710735"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="070f0-102">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="070f0-102">ICorDebugMemoryBuffer Interface</span></span>

<span data-ttu-id="070f0-103">Stellt einen In-Memory-Puffer dar.</span><span class="sxs-lookup"><span data-stu-id="070f0-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="070f0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="070f0-104">Methods</span></span>  
  
|<span data-ttu-id="070f0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="070f0-105">Method</span></span>|<span data-ttu-id="070f0-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="070f0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="070f0-107">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="070f0-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="070f0-108">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="070f0-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="070f0-109">GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="070f0-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="070f0-110">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="070f0-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="070f0-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="070f0-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="070f0-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="070f0-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="070f0-113">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="070f0-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="070f0-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="070f0-114">Requirements</span></span>  

 <span data-ttu-id="070f0-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="070f0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="070f0-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="070f0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="070f0-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="070f0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="070f0-118">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="070f0-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="070f0-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="070f0-119">See also</span></span>

- [<span data-ttu-id="070f0-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="070f0-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="070f0-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="070f0-121">Debugging</span></span>](index.md)
