---
title: ICorDebugStepper2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2
helpviewer_keywords:
- ICorDebugStepper2 interface [.NET Framework debugging]
ms.assetid: 7a191c2a-95ea-4d47-83b0-44de2b632d63
topic_type:
- apiref
ms.openlocfilehash: ef7aa164c43751fa39e49d0ab6486a9f29e23c20
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379476"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="58cb9-102">ICorDebugStepper2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58cb9-102">ICorDebugStepper2 Interface</span></span>
<span data-ttu-id="58cb9-103">Bietet Unterstützung für das Debuggen von nur eigenen Code (JMC).</span><span class="sxs-lookup"><span data-stu-id="58cb9-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="58cb9-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="58cb9-104">Methods</span></span>  
  
|<span data-ttu-id="58cb9-105">Methode</span><span class="sxs-lookup"><span data-stu-id="58cb9-105">Method</span></span>|<span data-ttu-id="58cb9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58cb9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="58cb9-107">SetJMC-Methode</span><span class="sxs-lookup"><span data-stu-id="58cb9-107">SetJMC Method</span></span>](icordebugstepper2-setjmc-method.md)|<span data-ttu-id="58cb9-108">Legt einen Wert fest, der angibt, ob dieser ICorDebugStepper nur durch Code ausgeführt wird, der vom Entwickler einer Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="58cb9-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58cb9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58cb9-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58cb9-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="58cb9-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58cb9-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="58cb9-111">Requirements</span></span>  
 <span data-ttu-id="58cb9-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58cb9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58cb9-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58cb9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58cb9-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58cb9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58cb9-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58cb9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58cb9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58cb9-116">See also</span></span>

- [<span data-ttu-id="58cb9-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="58cb9-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
