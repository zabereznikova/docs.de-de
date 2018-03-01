---
title: ICorDebugHeapValue Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2ab132b73369526204f8fd811e1567b07b4a9b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapvalue-interface1"></a><span data-ttu-id="7828c-102">ICorDebugHeapValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="7828c-102">ICorDebugHeapValue Interface1</span></span>
<span data-ttu-id="7828c-103">Eine Unterklasse von "ICorDebugValue", die ein Objekt darstellt, die von der Garbage Collector der common Language Runtime (CLR) gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="7828c-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7828c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7828c-104">Methods</span></span>  
  
|<span data-ttu-id="7828c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7828c-105">Method</span></span>|<span data-ttu-id="7828c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7828c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7828c-107">CreateRelocBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="7828c-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="7828c-108">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="7828c-108">Not implemented.</span></span>|  
|[<span data-ttu-id="7828c-109">IsValid-Methode</span><span class="sxs-lookup"><span data-stu-id="7828c-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="7828c-110">Ruft einen Wert, der angibt, ob das Objekt von diesem dargestellt `ICorDebugHeapValue` ist ungültig oder wurde durch den Garbage Collector freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="7828c-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="7828c-111">Diese Methode ist in .NET Framework, Version 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="7828c-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7828c-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7828c-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7828c-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7828c-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7828c-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7828c-114">Requirements</span></span>  
 <span data-ttu-id="7828c-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7828c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7828c-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7828c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7828c-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7828c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7828c-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7828c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7828c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7828c-119">See Also</span></span>  
    
    
    
 [<span data-ttu-id="7828c-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7828c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
