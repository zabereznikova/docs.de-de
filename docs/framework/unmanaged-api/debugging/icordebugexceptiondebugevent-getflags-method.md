---
title: ICorDebugExceptionDebugEvent::GetFlags-Methode
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 5793d939c8497ef842f614048707f69faa8ac568
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976043"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="20094-102">ICorDebugExceptionDebugEvent::GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="20094-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="20094-103">Ruft ein Flag ab, das angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="20094-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20094-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20094-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20094-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20094-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="20094-106">vorgenommen Ein Zeiger auf einen [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) -Wert, der angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="20094-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20094-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20094-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20094-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="20094-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20094-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20094-109">Requirements</span></span>  
 <span data-ttu-id="20094-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20094-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20094-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20094-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20094-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20094-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20094-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20094-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20094-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20094-114">See also</span></span>

- [<span data-ttu-id="20094-115">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20094-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="20094-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="20094-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
