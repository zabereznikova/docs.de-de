---
title: ICorDebugBoxValue Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b546d65e2c3cf498c80e19cc7236a6e424515577
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405925"
---
# <a name="icordebugboxvalue-interface1"></a><span data-ttu-id="08408-102">ICorDebugBoxValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="08408-102">ICorDebugBoxValue Interface1</span></span>
<span data-ttu-id="08408-103">Eine Unterklasse von "ICorDebugHeapValue", die ein geschachteltes Wertklassenobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="08408-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08408-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="08408-104">Methods</span></span>  
  
|<span data-ttu-id="08408-105">Methode</span><span class="sxs-lookup"><span data-stu-id="08408-105">Method</span></span>|<span data-ttu-id="08408-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08408-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08408-107">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="08408-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="08408-108">Ruft einen Schnittstellenzeiger auf die geschachtelte "ICorDebugObjectValue"-Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="08408-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08408-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08408-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08408-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="08408-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08408-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08408-111">Requirements</span></span>  
 <span data-ttu-id="08408-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08408-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08408-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08408-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08408-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08408-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08408-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08408-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08408-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08408-116">See Also</span></span>  
 [<span data-ttu-id="08408-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="08408-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
