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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075495"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="943c1-102">ICorDebugHeapValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="943c1-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="943c1-103">Eine Unterklasse von "ICorDebugValue", die ein Objekt darstellt, die von der Garbage Collector der common Language Runtime (CLR) gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="943c1-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="943c1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="943c1-104">Methods</span></span>  
  
|<span data-ttu-id="943c1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="943c1-105">Method</span></span>|<span data-ttu-id="943c1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="943c1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="943c1-107">CreateRelocBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="943c1-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="943c1-108">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="943c1-108">Not implemented.</span></span>|  
|[<span data-ttu-id="943c1-109">IsValid-Methode</span><span class="sxs-lookup"><span data-stu-id="943c1-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="943c1-110">Ruft einen Wert, der angibt, ob das Objekt von diesem dargestellt `ICorDebugHeapValue` ist ungültig, oder durch den Garbage Collector zurückgefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="943c1-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="943c1-111">Diese Methode wurde in .NET Framework, Version 2.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="943c1-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="943c1-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="943c1-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="943c1-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="943c1-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="943c1-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="943c1-114">Requirements</span></span>  
 <span data-ttu-id="943c1-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="943c1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="943c1-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="943c1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="943c1-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="943c1-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="943c1-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="943c1-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="943c1-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="943c1-119">See also</span></span>

- [<span data-ttu-id="943c1-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="943c1-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
