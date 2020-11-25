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
ms.openlocfilehash: ee3ea319360bba1a113c15daf8cf143ea512e5cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733320"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="421b5-102">ICorDebugHeapValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="421b5-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="421b5-103">Eine Unterklasse von "ICorDebugValue", die ein Objekt darstellt, das von der Common Language Runtime-Garbage Collector (CLR) erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="421b5-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="421b5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="421b5-104">Methods</span></span>  
  
|<span data-ttu-id="421b5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="421b5-105">Method</span></span>|<span data-ttu-id="421b5-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="421b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="421b5-107">CreateRelocBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="421b5-107">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="421b5-108">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="421b5-108">Not implemented.</span></span>|  
|[<span data-ttu-id="421b5-109">IsValid-Methode</span><span class="sxs-lookup"><span data-stu-id="421b5-109">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="421b5-110">Ruft einen Wert ab, der angibt, ob das von diesem dargestellte Objekt `ICorDebugHeapValue` gültig ist oder vom Garbage Collector freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="421b5-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="421b5-111">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="421b5-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="421b5-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="421b5-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="421b5-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="421b5-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="421b5-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="421b5-114">Requirements</span></span>  

 <span data-ttu-id="421b5-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="421b5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="421b5-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="421b5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="421b5-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="421b5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="421b5-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="421b5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="421b5-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="421b5-119">See also</span></span>

- [<span data-ttu-id="421b5-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="421b5-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
