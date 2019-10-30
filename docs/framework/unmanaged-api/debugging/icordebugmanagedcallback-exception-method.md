---
title: ICorDebugManagedCallback::Exception-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
ms.openlocfilehash: af2dab65629093401219f1016538b912bee4d067
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130827"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="cb6fb-102">ICorDebugManagedCallback::Exception-Methode</span><span class="sxs-lookup"><span data-stu-id="cb6fb-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="cb6fb-103">Benachrichtigt den Debugger, dass eine Ausnahme von verwaltetem Code ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cb6fb-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb6fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb6fb-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb6fb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cb6fb-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="cb6fb-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cb6fb-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="cb6fb-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cb6fb-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="cb6fb-108">in Wenn dieser Wert `false`ist, wurde die Ausnahme noch nicht von der Anwendung verarbeitet. Andernfalls wird die Ausnahme nicht behandelt, und der Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="cb6fb-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb6fb-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cb6fb-109">Remarks</span></span>  
 <span data-ttu-id="cb6fb-110">Die spezifische Ausnahme kann aus dem Thread Objekt abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cb6fb-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb6fb-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cb6fb-111">Requirements</span></span>  
 <span data-ttu-id="cb6fb-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb6fb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb6fb-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb6fb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb6fb-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb6fb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb6fb-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb6fb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb6fb-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb6fb-116">See also</span></span>

- [<span data-ttu-id="cb6fb-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb6fb-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
