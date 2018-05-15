---
title: ICorDebugManagedCallback2::ExceptionUnwind-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92c4f488dcdc5712dcd2632f489fb0cd65d05ee6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="b34a3-102">ICorDebugManagedCallback2::ExceptionUnwind-Methode</span><span class="sxs-lookup"><span data-stu-id="b34a3-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="b34a3-103">Stellt eine Benachrichtigung zum Status während des Entladungsprozesses Ausnahme bereit.</span><span class="sxs-lookup"><span data-stu-id="b34a3-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b34a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b34a3-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b34a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b34a3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b34a3-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Thread, der der Ausnahme darstellt.</span><span class="sxs-lookup"><span data-stu-id="b34a3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="b34a3-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="b34a3-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="b34a3-108">[in] Der Wert der CorDebugExceptionUnwindCallbackType-Enumeration, die das Ereignis angibt, das durch den Rückruf während der Entladephase signalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b34a3-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b34a3-109">[in] Der Wert der [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) Enumeration, die zusätzliche Informationen über die Ausnahme angibt.</span><span class="sxs-lookup"><span data-stu-id="b34a3-109">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b34a3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b34a3-110">Remarks</span></span>  
 <span data-ttu-id="b34a3-111">`ExceptionUnwind` an verschiedenen Punkten wird während der Entladephase des Prozesses für die Ausnahmebehandlung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b34a3-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="b34a3-112">`ExceptionUnwind` kann mehrmals aufgerufen werden, während der Entladung einer einzelnen Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="b34a3-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="b34a3-113">Wenn `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, befindet sich der Anweisungszeiger im Endframe des Threads, an dem Sequenzpunkt vor dem werden (dies möglicherweise mehrere Anweisungen vor) der Anweisung, die zu der Ausnahme geführt hat.</span><span class="sxs-lookup"><span data-stu-id="b34a3-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b34a3-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b34a3-114">Requirements</span></span>  
 <span data-ttu-id="b34a3-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b34a3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b34a3-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b34a3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b34a3-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b34a3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b34a3-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b34a3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b34a3-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b34a3-119">See Also</span></span>  
 [<span data-ttu-id="b34a3-120">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b34a3-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="b34a3-121">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b34a3-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
