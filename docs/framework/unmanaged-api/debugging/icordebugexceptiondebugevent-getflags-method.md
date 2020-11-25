---
title: ICorDebugExceptionDebugEvent::GetFlags-Methode
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 02a20b54b7fecc711bda010c6916fe036cf20dd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729602"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="eb652-102">ICorDebugExceptionDebugEvent::GetFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="eb652-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>

<span data-ttu-id="eb652-103">Ruft ein Flag ab, das angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="eb652-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb652-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb652-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb652-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb652-105">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="eb652-106">vorgenommen Ein Zeiger auf einen [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) -Wert, der angibt, ob die Ausnahme abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="eb652-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb652-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eb652-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb652-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eb652-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb652-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="eb652-109">Requirements</span></span>  

 <span data-ttu-id="eb652-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb652-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb652-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb652-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb652-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb652-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb652-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb652-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb652-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb652-114">See also</span></span>

- [<span data-ttu-id="eb652-115">ICorDebugExceptionDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb652-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="eb652-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="eb652-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
