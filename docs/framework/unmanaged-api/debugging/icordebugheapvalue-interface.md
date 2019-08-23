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
ms.openlocfilehash: eb130f11975eb95db7807126d6f163425439b0c4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914903"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="0e707-102">ICorDebugHeapValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0e707-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="0e707-103">Eine Unterklasse von "ICorDebugValue", die ein Objekt darstellt, das von der Common Language Runtime-Garbage Collector (CLR) erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="0e707-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e707-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0e707-104">Methods</span></span>  
  
|<span data-ttu-id="0e707-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0e707-105">Method</span></span>|<span data-ttu-id="0e707-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e707-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e707-107">CreateRelocBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="0e707-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="0e707-108">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="0e707-108">Not implemented.</span></span>|  
|[<span data-ttu-id="0e707-109">IsValid-Methode</span><span class="sxs-lookup"><span data-stu-id="0e707-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="0e707-110">Ruft einen Wert ab, der angibt, ob das von `ICorDebugHeapValue` diesem dargestellte Objekt gültig ist oder vom Garbage Collector freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0e707-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="0e707-111">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="0e707-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e707-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e707-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e707-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0e707-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e707-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e707-114">Requirements</span></span>  
 <span data-ttu-id="0e707-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e707-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e707-116">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="0e707-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e707-117">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e707-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e707-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e707-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e707-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e707-119">See also</span></span>

- [<span data-ttu-id="0e707-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0e707-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
