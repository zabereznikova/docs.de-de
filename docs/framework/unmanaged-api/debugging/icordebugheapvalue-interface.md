---
title: ICorDebugHeapValue-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5fcd8c17c4006714fa9d11aece5cccc57c97087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700825"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="af7ba-102">ICorDebugHeapValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af7ba-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="af7ba-103">Eine Unterklasse von "ICorDebugValue", die ein Objekt darstellt, die von der Garbage Collector der common Language Runtime (CLR) gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="af7ba-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af7ba-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="af7ba-104">Methods</span></span>  
  
|<span data-ttu-id="af7ba-105">Methode</span><span class="sxs-lookup"><span data-stu-id="af7ba-105">Method</span></span>|<span data-ttu-id="af7ba-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af7ba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af7ba-107">CreateRelocBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="af7ba-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="af7ba-108">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="af7ba-108">Not implemented.</span></span>|  
|[<span data-ttu-id="af7ba-109">IsValid-Methode</span><span class="sxs-lookup"><span data-stu-id="af7ba-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="af7ba-110">Ruft einen Wert, der angibt, ob das Objekt von diesem dargestellt `ICorDebugHeapValue` ist ungültig, oder durch den Garbage Collector zurückgefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="af7ba-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="af7ba-111">Diese Methode wurde in .NET Framework, Version 2.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="af7ba-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af7ba-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af7ba-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af7ba-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="af7ba-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af7ba-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af7ba-114">Requirements</span></span>  
 <span data-ttu-id="af7ba-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af7ba-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af7ba-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af7ba-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af7ba-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af7ba-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af7ba-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af7ba-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af7ba-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af7ba-119">See also</span></span>

- [<span data-ttu-id="af7ba-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="af7ba-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
