---
title: ICorDebugExceptionDebugEvent::GetFlags-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c6e7767ca5467f69dc7f53728bda9daf5f08331c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="d21aa-102">ICorDebugExceptionDebugEvent::GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="d21aa-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="d21aa-103">Ruft ein Flag ab, das angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d21aa-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d21aa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d21aa-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d21aa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d21aa-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="d21aa-106">[out] Ein Zeiger auf eine [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) Wert, der angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d21aa-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d21aa-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d21aa-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d21aa-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d21aa-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d21aa-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d21aa-109">Requirements</span></span>  
 <span data-ttu-id="d21aa-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d21aa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d21aa-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d21aa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d21aa-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d21aa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d21aa-113">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d21aa-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d21aa-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d21aa-114">See Also</span></span>  
 [<span data-ttu-id="d21aa-115">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d21aa-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="d21aa-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d21aa-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
