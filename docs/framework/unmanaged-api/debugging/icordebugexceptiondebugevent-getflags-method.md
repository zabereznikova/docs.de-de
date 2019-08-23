---
title: ICorDebugExceptionDebugEvent::GetFlags-Methode
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbe6f6a2953c3f815606e881b86a693b7a0e6ec7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951899"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="fd4a8-102">ICorDebugExceptionDebugEvent::GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="fd4a8-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="fd4a8-103">Ruft ein Flag ab, das angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fd4a8-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd4a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd4a8-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd4a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd4a8-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="fd4a8-106">vorgenommen Ein Zeiger auf einen [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) -Wert, der angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fd4a8-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd4a8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd4a8-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd4a8-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fd4a8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd4a8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd4a8-109">Requirements</span></span>  
 <span data-ttu-id="fd4a8-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd4a8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd4a8-111">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="fd4a8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd4a8-112">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd4a8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd4a8-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd4a8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4a8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd4a8-114">See also</span></span>

- [<span data-ttu-id="fd4a8-115">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd4a8-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="fd4a8-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fd4a8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
