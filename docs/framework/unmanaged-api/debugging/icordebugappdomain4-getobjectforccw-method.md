---
title: ICorDebugAppDomain4::GetObjectForCCW-Methode
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 8b046eb5926bb9aa4738e8fff8e61b0b7c23a3aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088830"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="3e548-102">ICorDebugAppDomain4::GetObjectForCCW-Methode</span><span class="sxs-lookup"><span data-stu-id="3e548-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="3e548-103">Ruft ein verwaltetes Objekt über einen Zeiger des COM Callable Wrapper (CCW) ab.</span><span class="sxs-lookup"><span data-stu-id="3e548-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e548-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e548-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e548-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3e548-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="3e548-106">[in] Zeiger des COM Callable Wrapper (CCW).</span><span class="sxs-lookup"><span data-stu-id="3e548-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="3e548-107">vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das das verwaltete Objekt darstellt, das dem angegebenen CCW-Zeiger entspricht.</span><span class="sxs-lookup"><span data-stu-id="3e548-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e548-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3e548-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e548-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3e548-109">Requirements</span></span>  
 <span data-ttu-id="3e548-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e548-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e548-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e548-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e548-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e548-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e548-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e548-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e548-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e548-114">See also</span></span>

- [<span data-ttu-id="3e548-115">ICorDebugAppDomain4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3e548-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [<span data-ttu-id="3e548-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3e548-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
