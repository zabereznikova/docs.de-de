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
ms.openlocfilehash: 30008d6cc98f7d0d0501d67e18703ed5a344d43a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794364"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="b4acf-102">ICorDebugILCode2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4acf-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="b4acf-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="b4acf-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b4acf-104">Erweitert logisch die [icordebugilcode](icordebugilcode-interface.md) -Schnittstelle so, dass Methoden bereitgestellt werden, die das Token für die Signatur der lokalen Variablen einer Funktion zurückgeben und die instrumentierten Intermediate Language (IL)-Offsets eines Profilers den ursprünglichen Methoden-IL-Offsets zuordnen.</span><span class="sxs-lookup"><span data-stu-id="b4acf-104">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b4acf-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b4acf-105">Methods</span></span>  
  
|<span data-ttu-id="b4acf-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="b4acf-106">Method</span></span>|<span data-ttu-id="b4acf-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4acf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b4acf-108">GetInstrumentedILMap-Methode</span><span class="sxs-lookup"><span data-stu-id="b4acf-108">GetInstrumentedILMap Method</span></span>](icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="b4acf-109">Gibt eine Zuordnung von Profiler-instrumentierten IL-Offsets zu ILs der ursprünglichen Methode für diese Instanz aus.</span><span class="sxs-lookup"><span data-stu-id="b4acf-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="b4acf-110">GetLocalVarSigToken-Methode</span><span class="sxs-lookup"><span data-stu-id="b4acf-110">GetLocalVarSigToken Method</span></span>](icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="b4acf-111">Ruft den Metadatentoken für die lokale Variablensignatur für die Funktion auf, die in dieser Instanz repräsentiert wird.</span><span class="sxs-lookup"><span data-stu-id="b4acf-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4acf-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4acf-112">Requirements</span></span>  
 <span data-ttu-id="b4acf-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4acf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4acf-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4acf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4acf-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4acf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4acf-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4acf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4acf-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4acf-117">See also</span></span>

- [<span data-ttu-id="b4acf-118">ICorDebugILCode-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4acf-118">ICorDebugILCode Interface</span></span>](icordebugilcode-interface.md)
- [<span data-ttu-id="b4acf-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b4acf-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b4acf-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b4acf-120">Debugging</span></span>](index.md)
