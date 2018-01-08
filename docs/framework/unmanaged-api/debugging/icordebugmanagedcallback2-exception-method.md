---
title: ICorDebugManagedCallback2::Exception-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.Exception
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79a8fa4709aeb04164bd1c2da07607435b76fff5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="bd846-102">ICorDebugManagedCallback2::Exception-Methode</span><span class="sxs-lookup"><span data-stu-id="bd846-102">ICorDebugManagedCallback2::Exception Method</span></span>
<span data-ttu-id="bd846-103">Benachrichtigt den Debugger, dass eine Suche nach einem Ausnahmehandler gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="bd846-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd846-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd846-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd846-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd846-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="bd846-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Thread, der der Ausnahme darstellt.</span><span class="sxs-lookup"><span data-stu-id="bd846-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="bd846-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="bd846-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="bd846-108">[in] Ein Zeiger auf ein ICorDebugFrame-Objekt, das einen Frame darstellt, durch die `dwEventType` Parameter.</span><span class="sxs-lookup"><span data-stu-id="bd846-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="bd846-109">Weitere Informationen finden Sie in der Tabelle im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="bd846-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="bd846-110">[in] Eine ganze Zahl, die einen Offset angibt, durch die `dwEventType` Parameter.</span><span class="sxs-lookup"><span data-stu-id="bd846-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="bd846-111">Weitere Informationen finden Sie in der Tabelle im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="bd846-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="bd846-112">[in] Der Wert CorDebugExceptionCallbackType-Enumeration, die der den von diesem Ausnahmerückruf angibt.</span><span class="sxs-lookup"><span data-stu-id="bd846-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="bd846-113">[in] Der Wert der [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) Enumeration, die zusätzliche Informationen über die Ausnahme angibt.</span><span class="sxs-lookup"><span data-stu-id="bd846-113">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd846-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd846-114">Remarks</span></span>  
 <span data-ttu-id="bd846-115">Die `Exception` aufgerufener Rückruf an verschiedenen Punkten während der Suche Phase des Prozesses für die Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="bd846-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="bd846-116">D. h. es kann aufgerufen werden, mehr als einmal während Entladen einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="bd846-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="bd846-117">Die Ausnahme, die verarbeitet werden kann abgerufen werden, aus dem ICorDebugThread-Objekt verweist die `pThread` Parameter.</span><span class="sxs-lookup"><span data-stu-id="bd846-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="bd846-118">Der jeweilige Frame und Offset hängen von der `dwEventType` Parameter wie folgt:</span><span class="sxs-lookup"><span data-stu-id="bd846-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="bd846-119">Wert von `dwEventType`</span><span class="sxs-lookup"><span data-stu-id="bd846-119">Value of `dwEventType`</span></span>|<span data-ttu-id="bd846-120">Wert von `pFrame`</span><span class="sxs-lookup"><span data-stu-id="bd846-120">Value of `pFrame`</span></span>|<span data-ttu-id="bd846-121">Wert von `nOffset`</span><span class="sxs-lookup"><span data-stu-id="bd846-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="bd846-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="bd846-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="bd846-123">Der Frame, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="bd846-123">The frame that threw the exception.</span></span>|<span data-ttu-id="bd846-124">Der Anweisungszeiger im Frame.</span><span class="sxs-lookup"><span data-stu-id="bd846-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="bd846-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="bd846-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="bd846-126">Der Benutzercode-Frames, die den Punkt der ausgelösten Ausnahme am nächsten.</span><span class="sxs-lookup"><span data-stu-id="bd846-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="bd846-127">Der Anweisungszeiger im Frame.</span><span class="sxs-lookup"><span data-stu-id="bd846-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="bd846-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="bd846-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="bd846-129">Der Frame, der den Catch-Handler enthält.</span><span class="sxs-lookup"><span data-stu-id="bd846-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="bd846-130">Der Microsoft intermediate Language (MSIL)-Offset des Anfangs des Catch-Handler.</span><span class="sxs-lookup"><span data-stu-id="bd846-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="bd846-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="bd846-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="bd846-132">NULL</span><span class="sxs-lookup"><span data-stu-id="bd846-132">NULL</span></span>|<span data-ttu-id="bd846-133">Nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="bd846-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd846-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd846-134">Requirements</span></span>  
 <span data-ttu-id="bd846-135">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd846-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd846-136">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd846-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd846-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd846-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd846-138">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd846-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd846-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd846-139">See Also</span></span>  
 [<span data-ttu-id="bd846-140">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd846-140">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="bd846-141">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd846-141">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
