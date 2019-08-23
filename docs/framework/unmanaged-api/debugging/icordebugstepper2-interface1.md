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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d86f4bbec8971d164966298734388f0744a2d41c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69953037"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="c02fa-102">ICorDebugStepper2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c02fa-102">ICorDebugStepper2 Interface</span></span>
<span data-ttu-id="c02fa-103">Bietet Unterstützung für das Debuggen von nur eigenen Code (JMC).</span><span class="sxs-lookup"><span data-stu-id="c02fa-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c02fa-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c02fa-104">Methods</span></span>  
  
|<span data-ttu-id="c02fa-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c02fa-105">Method</span></span>|<span data-ttu-id="c02fa-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c02fa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c02fa-107">SetJMC-Methode</span><span class="sxs-lookup"><span data-stu-id="c02fa-107">SetJMC Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-setjmc-method.md)|<span data-ttu-id="c02fa-108">Legt einen Wert fest, der angibt, ob dieser ICorDebugStepper nur durch Code ausgeführt wird, der vom Entwickler einer Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c02fa-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c02fa-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c02fa-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c02fa-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c02fa-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c02fa-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c02fa-111">Requirements</span></span>  
 <span data-ttu-id="c02fa-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c02fa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c02fa-113">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="c02fa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c02fa-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c02fa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c02fa-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c02fa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c02fa-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c02fa-116">See also</span></span>

- [<span data-ttu-id="c02fa-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c02fa-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
