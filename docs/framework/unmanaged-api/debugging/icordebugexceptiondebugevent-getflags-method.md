---
title: ICorDebugExceptionDebugEvent::GetFlags-Methode
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: aaf137b1d851d0de86bde697c9e3a512f34d2aa9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782920"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="30eca-102">ICorDebugExceptionDebugEvent::GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="30eca-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="30eca-103">Ruft ein Flag ab, das angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="30eca-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30eca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30eca-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30eca-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="30eca-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="30eca-106">vorgenommen Ein Zeiger auf einen [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) -Wert, der angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="30eca-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30eca-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30eca-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30eca-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="30eca-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30eca-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30eca-109">Requirements</span></span>  
 <span data-ttu-id="30eca-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30eca-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30eca-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30eca-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30eca-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30eca-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30eca-113">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30eca-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30eca-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30eca-114">See also</span></span>

- [<span data-ttu-id="30eca-115">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30eca-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="30eca-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="30eca-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
