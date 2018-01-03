---
title: ICorDebugBoxValue Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBoxValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBoxValue
helpviewer_keywords: ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 43c4a1d0e8805fc3692aa96668a7f3ea567718f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugboxvalue-interface1"></a><span data-ttu-id="bd373-102">ICorDebugBoxValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="bd373-102">ICorDebugBoxValue Interface1</span></span>
<span data-ttu-id="bd373-103">Eine Unterklasse von "ICorDebugHeapValue", die ein geschachteltes Wertklassenobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="bd373-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bd373-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bd373-104">Methods</span></span>  
  
|<span data-ttu-id="bd373-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bd373-105">Method</span></span>|<span data-ttu-id="bd373-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd373-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bd373-107">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="bd373-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="bd373-108">Ruft einen Schnittstellenzeiger auf die geschachtelte "ICorDebugObjectValue"-Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="bd373-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd373-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd373-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd373-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bd373-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd373-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd373-111">Requirements</span></span>  
 <span data-ttu-id="bd373-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd373-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd373-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd373-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd373-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd373-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd373-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd373-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd373-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd373-116">See Also</span></span>  
 [<span data-ttu-id="bd373-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bd373-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
