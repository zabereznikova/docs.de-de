---
title: 'Icordebugexceptiondebugevent:: GetFlags-Methode'
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 6c330ce5b375daacdf257eda16fd5e34012f5d69
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084751"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="21dab-102">Icordebugexceptiondebugevent:: GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="21dab-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="21dab-103">Ruft ein Flag ab, das angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="21dab-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21dab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21dab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21dab-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="21dab-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="21dab-106">vorgenommen Ein Zeiger auf einen [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) -Wert, der angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="21dab-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21dab-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21dab-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21dab-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="21dab-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21dab-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="21dab-109">Requirements</span></span>  
 <span data-ttu-id="21dab-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21dab-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21dab-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21dab-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21dab-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21dab-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21dab-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21dab-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21dab-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21dab-114">See also</span></span>

- [<span data-ttu-id="21dab-115">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21dab-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="21dab-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="21dab-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
