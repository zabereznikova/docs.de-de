---
title: ICorDebugExceptionDebugEvent::GetFlags-Methode
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b9c07b010447b4a437febb4b60565111a85c8d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415453"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="c250b-102">ICorDebugExceptionDebugEvent::GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="c250b-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="c250b-103">Ruft ein Flag ab, das angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c250b-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c250b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c250b-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c250b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c250b-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="c250b-106">[out] Ein Zeiger auf eine [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) Wert, der angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c250b-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c250b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c250b-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c250b-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c250b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c250b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c250b-109">Requirements</span></span>  
 <span data-ttu-id="c250b-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c250b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c250b-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c250b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c250b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c250b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c250b-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c250b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c250b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c250b-114">See Also</span></span>  
 [<span data-ttu-id="c250b-115">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c250b-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="c250b-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c250b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
