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
ms.openlocfilehash: 4f87065fc4a3d80a8363f3ae2fbb76c29f3d9b96
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138414"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="61bc2-102">ICorDebugHeapValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61bc2-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="61bc2-103">Eine Unterklasse von "ICorDebugValue", die ein Objekt darstellt, das von der Common Language Runtime-Garbage Collector (CLR) erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="61bc2-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61bc2-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="61bc2-104">Methods</span></span>  
  
|<span data-ttu-id="61bc2-105">Methode</span><span class="sxs-lookup"><span data-stu-id="61bc2-105">Method</span></span>|<span data-ttu-id="61bc2-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61bc2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61bc2-107">CreateRelocBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="61bc2-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="61bc2-108">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="61bc2-108">Not implemented.</span></span>|  
|[<span data-ttu-id="61bc2-109">IsValid-Methode</span><span class="sxs-lookup"><span data-stu-id="61bc2-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="61bc2-110">Ruft einen Wert ab, der angibt, ob das von diesem `ICorDebugHeapValue` dargestellte Objekt gültig ist oder vom Garbage Collector freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="61bc2-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="61bc2-111">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="61bc2-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61bc2-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="61bc2-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="61bc2-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="61bc2-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61bc2-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="61bc2-114">Requirements</span></span>  
 <span data-ttu-id="61bc2-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61bc2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61bc2-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61bc2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61bc2-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61bc2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61bc2-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61bc2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61bc2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61bc2-119">See also</span></span>

- [<span data-ttu-id="61bc2-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="61bc2-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
