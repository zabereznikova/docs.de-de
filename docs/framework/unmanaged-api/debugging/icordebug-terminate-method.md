---
title: ICorDebug::Terminate-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: cf9c9d11c4725908fcf7ff4a0c91882b70a80190
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723375"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="cc4f3-102">ICorDebug::Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="cc4f3-102">ICorDebug::Terminate Method</span></span>

<span data-ttu-id="cc4f3-103">Beendet das- `ICorDebug` Objekt.</span><span class="sxs-lookup"><span data-stu-id="cc4f3-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc4f3-104">`Terminate` sollte erst aufgerufen werden, wenn ein [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) -Rückruf für alle Prozesse empfangen wurde, die gedebuggt werden.</span><span class="sxs-lookup"><span data-stu-id="cc4f3-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc4f3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc4f3-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cc4f3-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc4f3-106">Remarks</span></span>  

 <span data-ttu-id="cc4f3-107">`Terminate` muss aufgerufen werden, wenn das `ICorDebug` Objekt nicht mehr benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="cc4f3-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc4f3-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cc4f3-108">Requirements</span></span>  

 <span data-ttu-id="cc4f3-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc4f3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc4f3-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc4f3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc4f3-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc4f3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc4f3-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc4f3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc4f3-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc4f3-113">See also</span></span>

- [<span data-ttu-id="cc4f3-114">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cc4f3-114">ICorDebug Interface</span></span>](icordebug-interface.md)
