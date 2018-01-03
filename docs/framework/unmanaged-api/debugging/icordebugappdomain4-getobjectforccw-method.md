---
title: ICorDebugAppDomain4::GetObjectForCCW-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d459c9ea807114c4f63995ba8fbbb288ea5463b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="ef9f5-102">ICorDebugAppDomain4::GetObjectForCCW-Methode</span><span class="sxs-lookup"><span data-stu-id="ef9f5-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="ef9f5-103">Ruft ein verwaltetes Objekt über einen Zeiger des COM Callable Wrapper (CCW) ab.</span><span class="sxs-lookup"><span data-stu-id="ef9f5-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef9f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef9f5-104">Syntax</span></span>  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef9f5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ef9f5-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="ef9f5-106">[in] Zeiger des COM Callable Wrapper (CCW).</span><span class="sxs-lookup"><span data-stu-id="ef9f5-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="ef9f5-107">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugValue", die das verwaltete Objekt, das entspricht dem angegebenen CCW-Zeiger darstellt.</span><span class="sxs-lookup"><span data-stu-id="ef9f5-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef9f5-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef9f5-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef9f5-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ef9f5-109">Requirements</span></span>  
 <span data-ttu-id="ef9f5-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef9f5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef9f5-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef9f5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef9f5-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef9f5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef9f5-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef9f5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef9f5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef9f5-114">See Also</span></span>  
 [<span data-ttu-id="ef9f5-115">ICorDebugAppDomain4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef9f5-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 [<span data-ttu-id="ef9f5-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ef9f5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
