---
title: ICorDebugILCode2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
ms.openlocfilehash: 9c1a5cde5a39a334d655d865c5e44a5eb0c1766a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131041"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="83978-102">ICorDebugILCode2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83978-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="83978-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="83978-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="83978-104">Erweitert logisch die [icordebugilcode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) -Schnittstelle so, dass Methoden bereitgestellt werden, die das Token für die Signatur der lokalen Variablen einer Funktion zurückgeben und die instrumentierten Intermediate Language (IL)-Offsets eines Profilers den ursprünglichen Methoden-IL-Offsets zuordnen.</span><span class="sxs-lookup"><span data-stu-id="83978-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83978-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="83978-105">Methods</span></span>  
  
|<span data-ttu-id="83978-106">Methode</span><span class="sxs-lookup"><span data-stu-id="83978-106">Method</span></span>|<span data-ttu-id="83978-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83978-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83978-108">GetInstrumentedILMap-Methode</span><span class="sxs-lookup"><span data-stu-id="83978-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="83978-109">Gibt eine Zuordnung von Profiler-instrumentierten IL-Offsets zu ILs der ursprünglichen Methode für diese Instanz aus.</span><span class="sxs-lookup"><span data-stu-id="83978-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="83978-110">GetLocalVarSigToken-Methode</span><span class="sxs-lookup"><span data-stu-id="83978-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="83978-111">Ruft den Metadatentoken für die lokale Variablensignatur für die Funktion auf, die in dieser Instanz repräsentiert wird.</span><span class="sxs-lookup"><span data-stu-id="83978-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83978-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83978-112">Requirements</span></span>  
 <span data-ttu-id="83978-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83978-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83978-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83978-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83978-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83978-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83978-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83978-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83978-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83978-117">See also</span></span>

- [<span data-ttu-id="83978-118">ICorDebugILCode-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83978-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)
- [<span data-ttu-id="83978-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="83978-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="83978-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="83978-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
