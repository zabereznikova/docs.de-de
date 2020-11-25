---
title: ICorDebugILFrame3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
ms.openlocfilehash: dab5329086971b9349deaf84535fa251744f3cf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724987"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="7fd78-102">ICorDebugILFrame3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fd78-102">ICorDebugILFrame3 Interface</span></span>

<span data-ttu-id="7fd78-103">Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="7fd78-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="7fd78-104">`ICorDebugILFrame3` ist eine logische Erweiterung der ICorDebugILFrame- und ICorDebugILFrame2-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="7fd78-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7fd78-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7fd78-105">Methods</span></span>  
  
|<span data-ttu-id="7fd78-106">Methode</span><span class="sxs-lookup"><span data-stu-id="7fd78-106">Method</span></span>|<span data-ttu-id="7fd78-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7fd78-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7fd78-108">GetReturnValueForILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="7fd78-108">GetReturnValueForILOffset Method</span></span>](icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="7fd78-109">Ruft ein ICorDebugValue-Objekt ab, das den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="7fd78-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fd78-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7fd78-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7fd78-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7fd78-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fd78-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7fd78-112">Requirements</span></span>  

 <span data-ttu-id="7fd78-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fd78-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fd78-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7fd78-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7fd78-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fd78-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fd78-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fd78-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd78-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7fd78-117">See also</span></span>

- [<span data-ttu-id="7fd78-118">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fd78-118">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="7fd78-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7fd78-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
