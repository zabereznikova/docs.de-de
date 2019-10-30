---
title: ICorDebugThread2::InterceptCurrentException-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
ms.openlocfilehash: 1f3cf3db5df610e57a957147f0ab79121679e00b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138699"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="aa50a-102">ICorDebugThread2::InterceptCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="aa50a-102">ICorDebugThread2::InterceptCurrentException Method</span></span>
<span data-ttu-id="aa50a-103">Ermöglicht einem Debugger das Abfangen der aktuellen Ausnahme in diesem Thread.</span><span class="sxs-lookup"><span data-stu-id="aa50a-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa50a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa50a-104">Syntax</span></span>  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa50a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa50a-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="aa50a-106">in Ein Zeiger auf ein ICorDebug Frame-Element, das den aktiven Stapel Rahmen darstellt.</span><span class="sxs-lookup"><span data-stu-id="aa50a-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa50a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa50a-107">Remarks</span></span>  
 <span data-ttu-id="aa50a-108">Die `InterceptCurrentException`-Methode kann zwischen einem Ausnahme Rückruf ([ICorDebugManagedCallback:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md) oder [ICorDebugManagedCallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) und dem zugeordneten Aufruf von [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="aa50a-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa50a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa50a-109">Requirements</span></span>  
 <span data-ttu-id="aa50a-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa50a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa50a-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa50a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa50a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa50a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa50a-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa50a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
