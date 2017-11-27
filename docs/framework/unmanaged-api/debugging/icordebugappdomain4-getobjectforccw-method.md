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
ms.openlocfilehash: abce5563e8cd7eb0c599e835d0217157cf073485
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="3765e-102">ICorDebugAppDomain4::GetObjectForCCW-Methode</span><span class="sxs-lookup"><span data-stu-id="3765e-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="3765e-103">Ruft ein verwaltetes Objekt über einen Zeiger des COM Callable Wrapper (CCW) ab.</span><span class="sxs-lookup"><span data-stu-id="3765e-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3765e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3765e-104">Syntax</span></span>  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3765e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3765e-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="3765e-106">[in] Zeiger des COM Callable Wrapper (CCW).</span><span class="sxs-lookup"><span data-stu-id="3765e-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="3765e-107">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugValue", die das verwaltete Objekt, das entspricht dem angegebenen CCW-Zeiger darstellt.</span><span class="sxs-lookup"><span data-stu-id="3765e-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3765e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3765e-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3765e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3765e-109">Requirements</span></span>  
 <span data-ttu-id="3765e-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3765e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3765e-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3765e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3765e-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3765e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3765e-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3765e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3765e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3765e-114">See Also</span></span>  
 [<span data-ttu-id="3765e-115">ICorDebugAppDomain4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3765e-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 [<span data-ttu-id="3765e-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3765e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
