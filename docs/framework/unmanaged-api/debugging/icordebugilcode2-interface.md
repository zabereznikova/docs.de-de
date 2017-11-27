---
title: ICorDebugILCode2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILCode2
api_location: mscordbi.dll
api_type: COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2fd6b7b6b097010a307abbc260cda7c4b73e0f00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="c8679-102">ICorDebugILCode2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8679-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="c8679-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="c8679-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c8679-104">Erweitert logisch die [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) -Schnittstelle um Methoden, die das Token für die lokale Variablensignatur einer Funktion zurückgeben und, Zuordnen eines Profilers den instrumentierte intermediate Language (IL) an die ursprüngliche Methode IL-offsets UTC-Offsets.</span><span class="sxs-lookup"><span data-stu-id="c8679-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8679-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="c8679-105">Methods</span></span>  
  
|<span data-ttu-id="c8679-106">Methode</span><span class="sxs-lookup"><span data-stu-id="c8679-106">Method</span></span>|<span data-ttu-id="c8679-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8679-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8679-108">GetInstrumentedILMap-Methode</span><span class="sxs-lookup"><span data-stu-id="c8679-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="c8679-109">Gibt eine Zuordnung von Profiler-instrumentierten IL-Offsets zu ILs der ursprünglichen Methode für diese Instanz aus.</span><span class="sxs-lookup"><span data-stu-id="c8679-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="c8679-110">GetLocalVarSigToken-Methode</span><span class="sxs-lookup"><span data-stu-id="c8679-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="c8679-111">Ruft den Metadatentoken für die lokale Variablensignatur für die Funktion auf, die in dieser Instanz repräsentiert wird.</span><span class="sxs-lookup"><span data-stu-id="c8679-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8679-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8679-112">Requirements</span></span>  
 <span data-ttu-id="c8679-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8679-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8679-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8679-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8679-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8679-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8679-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8679-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8679-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8679-117">See Also</span></span>  
 [<span data-ttu-id="c8679-118">ICorDebugILCode-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8679-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 [<span data-ttu-id="c8679-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c8679-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c8679-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c8679-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
