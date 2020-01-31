---
title: ICorDebugAppDomain4::GetObjectForCCW-Methode
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 50f46394c809321f0bd256e4c8d75b76fc7c2c70
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784849"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="4c077-102">ICorDebugAppDomain4::GetObjectForCCW-Methode</span><span class="sxs-lookup"><span data-stu-id="4c077-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="4c077-103">Ruft ein verwaltetes Objekt über einen Zeiger des COM Callable Wrapper (CCW) ab.</span><span class="sxs-lookup"><span data-stu-id="4c077-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c077-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c077-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c077-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4c077-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="4c077-106">[in] Zeiger des COM Callable Wrapper (CCW).</span><span class="sxs-lookup"><span data-stu-id="4c077-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="4c077-107">vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das das verwaltete Objekt darstellt, das dem angegebenen CCW-Zeiger entspricht.</span><span class="sxs-lookup"><span data-stu-id="4c077-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c077-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c077-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c077-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c077-109">Requirements</span></span>  
 <span data-ttu-id="4c077-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c077-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c077-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c077-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c077-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c077-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c077-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c077-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c077-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c077-114">See also</span></span>

- [<span data-ttu-id="4c077-115">ICorDebugAppDomain4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c077-115">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="4c077-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4c077-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
