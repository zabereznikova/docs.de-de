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
ms.openlocfilehash: 739c648173d45a9c147ea2a4e469a3a4b518e893
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794334"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="a7310-102">ICorDebugILFrame3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7310-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="a7310-103">Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="a7310-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="a7310-104">`ICorDebugILFrame3` ist eine logische Erweiterung der ICorDebugILFrame-Schnittstelle und der ICorDebugILFrame2-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a7310-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7310-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a7310-105">Methods</span></span>  
  
|<span data-ttu-id="a7310-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="a7310-106">Method</span></span>|<span data-ttu-id="a7310-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7310-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7310-108">GetReturnValueForILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="a7310-108">GetReturnValueForILOffset Method</span></span>](icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="a7310-109">Ruft ein ICorDebugValue-Objekt ab, das den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="a7310-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7310-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7310-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a7310-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a7310-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7310-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7310-112">Requirements</span></span>  
 <span data-ttu-id="a7310-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7310-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7310-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7310-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7310-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7310-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7310-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7310-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7310-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7310-117">See also</span></span>

- [<span data-ttu-id="a7310-118">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7310-118">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="a7310-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a7310-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
