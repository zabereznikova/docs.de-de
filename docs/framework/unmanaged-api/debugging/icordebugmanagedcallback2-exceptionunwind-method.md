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
ms.openlocfilehash: 8f66369d3ac5ddcfe38fe579cac728eb3a250165
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205625"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="ab7fa-102">ICorDebugManagedCallback2::ExceptionUnwind-Methode</span><span class="sxs-lookup"><span data-stu-id="ab7fa-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="ab7fa-103">Stellt während des Entwicklungs Vorgangs der Ausnahme eine Status Benachrichtigung bereit.</span><span class="sxs-lookup"><span data-stu-id="ab7fa-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab7fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab7fa-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab7fa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ab7fa-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ab7fa-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Thread darstellt, für den die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="ab7fa-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ab7fa-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, für den die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="ab7fa-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="ab7fa-108">in Ein Wert der CorDebugExceptionUnwindCallbackType-Enumeration, der das Ereignis angibt, das während der Entladephase durch den Rückruf signalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="ab7fa-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ab7fa-109">in Ein Wert der [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) -Enumeration, der zusätzliche Informationen über die Ausnahme angibt.</span><span class="sxs-lookup"><span data-stu-id="ab7fa-109">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab7fa-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab7fa-110">Remarks</span></span>  
 <span data-ttu-id="ab7fa-111">`ExceptionUnwind`wird an verschiedenen Punkten während der Entladephase des Ausnahme Behandlungsprozesses aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ab7fa-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="ab7fa-112">`ExceptionUnwind`kann mehrmals aufgerufen werden, während eine einzelne Ausnahme entwickelt wird.</span><span class="sxs-lookup"><span data-stu-id="ab7fa-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="ab7fa-113">Wenn `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, wird der Anweisungs Zeiger im blattrahmen des Threads am Sequenz Punkt vor (möglicherweise mehrere Anweisungen vor) der Anweisung angezeigt, die zur Ausnahme geführt hat.</span><span class="sxs-lookup"><span data-stu-id="ab7fa-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab7fa-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ab7fa-114">Requirements</span></span>  
 <span data-ttu-id="ab7fa-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab7fa-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab7fa-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab7fa-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab7fa-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab7fa-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab7fa-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab7fa-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab7fa-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab7fa-119">See also</span></span>

- [<span data-ttu-id="ab7fa-120">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab7fa-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="ab7fa-121">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab7fa-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
