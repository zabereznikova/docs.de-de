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
ms.openlocfilehash: ecbedfbca37a3630fc6d40c173f8a6cd05b4d3fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727639"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="f6db3-102">ICorDebugStepper2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6db3-102">ICorDebugStepper2 Interface</span></span>

<span data-ttu-id="f6db3-103">Bietet Unterstützung für das Debuggen von nur eigenen Code (JMC).</span><span class="sxs-lookup"><span data-stu-id="f6db3-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6db3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f6db3-104">Methods</span></span>  
  
|<span data-ttu-id="f6db3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f6db3-105">Method</span></span>|<span data-ttu-id="f6db3-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f6db3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6db3-107">SetJMC-Methode</span><span class="sxs-lookup"><span data-stu-id="f6db3-107">SetJMC Method</span></span>](icordebugstepper2-setjmc-method.md)|<span data-ttu-id="f6db3-108">Legt einen Wert fest, der angibt, ob dieser ICorDebugStepper nur durch Code ausgeführt wird, der vom Entwickler einer Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f6db3-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6db3-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6db3-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6db3-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f6db3-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6db3-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f6db3-111">Requirements</span></span>  

 <span data-ttu-id="f6db3-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6db3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6db3-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6db3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6db3-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6db3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6db3-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6db3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6db3-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6db3-116">See also</span></span>

- [<span data-ttu-id="f6db3-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f6db3-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
