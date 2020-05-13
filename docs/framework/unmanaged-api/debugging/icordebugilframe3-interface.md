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
ms.openlocfilehash: 59221b09cc1c5d2d01c1007b649a4bb01de57f04
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213763"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="d62c1-102">ICorDebugILFrame3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d62c1-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="d62c1-103">Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="d62c1-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="d62c1-104">`ICorDebugILFrame3` ist eine logische Erweiterung der ICorDebugILFrame- und ICorDebugILFrame2-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="d62c1-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d62c1-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d62c1-105">Methods</span></span>  
  
|<span data-ttu-id="d62c1-106">Methode</span><span class="sxs-lookup"><span data-stu-id="d62c1-106">Method</span></span>|<span data-ttu-id="d62c1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d62c1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d62c1-108">GetReturnValueForILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="d62c1-108">GetReturnValueForILOffset Method</span></span>](icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="d62c1-109">Ruft ein ICorDebugValue-Objekt ab, das den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="d62c1-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d62c1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d62c1-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d62c1-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d62c1-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d62c1-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d62c1-112">Requirements</span></span>  
 <span data-ttu-id="d62c1-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d62c1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d62c1-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d62c1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d62c1-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d62c1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d62c1-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d62c1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d62c1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d62c1-117">See also</span></span>

- [<span data-ttu-id="d62c1-118">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d62c1-118">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="d62c1-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d62c1-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
