---
title: ICorDebugExceptionDebugEvent::GetFlags-Methode
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c38c3399c95d40acd6fafb05f51eb934647827e3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471757"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="8f7f9-102">ICorDebugExceptionDebugEvent::GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="8f7f9-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="8f7f9-103">Ruft ein Flag ab, das angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8f7f9-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f7f9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f7f9-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f7f9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f7f9-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="8f7f9-106">[out] Ein Zeiger auf eine [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) Wert, der angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8f7f9-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f7f9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f7f9-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f7f9-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8f7f9-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f7f9-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f7f9-109">Requirements</span></span>  
 <span data-ttu-id="8f7f9-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f7f9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f7f9-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f7f9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f7f9-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f7f9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f7f9-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f7f9-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f7f9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f7f9-114">See also</span></span>
- [<span data-ttu-id="8f7f9-115">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f7f9-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="8f7f9-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8f7f9-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
