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
ms.openlocfilehash: 36a485413490045ca49b99fca4fe5d43edc37114
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213009"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="486bb-102">ICorDebugHeapValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="486bb-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="486bb-103">Eine Unterklasse von "ICorDebugValue", die ein Objekt darstellt, das von der Common Language Runtime-Garbage Collector (CLR) erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="486bb-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="486bb-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="486bb-104">Methods</span></span>  
  
|<span data-ttu-id="486bb-105">Methode</span><span class="sxs-lookup"><span data-stu-id="486bb-105">Method</span></span>|<span data-ttu-id="486bb-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="486bb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="486bb-107">CreateRelocBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="486bb-107">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="486bb-108">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="486bb-108">Not implemented.</span></span>|  
|[<span data-ttu-id="486bb-109">IsValid-Methode</span><span class="sxs-lookup"><span data-stu-id="486bb-109">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="486bb-110">Ruft einen Wert ab, der angibt, ob das von diesem dargestellte Objekt `ICorDebugHeapValue` gültig ist oder vom Garbage Collector freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="486bb-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="486bb-111">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="486bb-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="486bb-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="486bb-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="486bb-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="486bb-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="486bb-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="486bb-114">Requirements</span></span>  
 <span data-ttu-id="486bb-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="486bb-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="486bb-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="486bb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="486bb-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="486bb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="486bb-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="486bb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="486bb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="486bb-119">See also</span></span>

- [<span data-ttu-id="486bb-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="486bb-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
