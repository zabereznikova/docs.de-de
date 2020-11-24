---
title: ICorDebugManagedCallback2::Exception-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
ms.openlocfilehash: c5be9231bcd5aaddfa0cf1b0051f8e1184faef04
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687631"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="bad8b-102">ICorDebugManagedCallback2::Exception-Methode</span><span class="sxs-lookup"><span data-stu-id="bad8b-102">ICorDebugManagedCallback2::Exception Method</span></span>

<span data-ttu-id="bad8b-103">Benachrichtigt den Debugger, dass eine Suche nach einem Ausnahmehandler gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="bad8b-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bad8b-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bad8b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bad8b-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="bad8b-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Thread darstellt, für den die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="bad8b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="bad8b-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, für den die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="bad8b-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="bad8b-108">in Ein Zeiger auf ein ICorDebug Frame-Objekt, das einen Frame darstellt, wie vom- `dwEventType` Parameter festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bad8b-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="bad8b-109">Weitere Informationen finden Sie in der Tabelle im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="bad8b-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="bad8b-110">in Eine ganze Zahl, die einen Offset angibt, der durch den-Parameter bestimmt wird `dwEventType` .</span><span class="sxs-lookup"><span data-stu-id="bad8b-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="bad8b-111">Weitere Informationen finden Sie in der Tabelle im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="bad8b-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="bad8b-112">in Ein Wert der CorDebugExceptionCallbackType-Enumeration, der den Typ dieses Ausnahme Rückrufs angibt.</span><span class="sxs-lookup"><span data-stu-id="bad8b-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="bad8b-113">in Ein Wert der [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) -Enumeration, der zusätzliche Informationen über die Ausnahme angibt.</span><span class="sxs-lookup"><span data-stu-id="bad8b-113">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bad8b-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bad8b-114">Remarks</span></span>  

 <span data-ttu-id="bad8b-115">Der `Exception` Rückruf wird an verschiedenen Punkten während der Suchphase des Ausnahme Behandlungsprozesses aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bad8b-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="bad8b-116">Das heißt, dass Sie mehrmals aufgerufen werden kann, während Sie eine Ausnahme entwickeln.</span><span class="sxs-lookup"><span data-stu-id="bad8b-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="bad8b-117">Die verarbeitete Ausnahme kann aus dem ICorDebugThread-Objekt abgerufen werden, auf das durch den-Parameter verwiesen wird `pThread` .</span><span class="sxs-lookup"><span data-stu-id="bad8b-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="bad8b-118">Der jeweilige Frame und der Offset werden vom- `dwEventType` Parameter wie folgt bestimmt:</span><span class="sxs-lookup"><span data-stu-id="bad8b-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="bad8b-119">Wert von `dwEventType`</span><span class="sxs-lookup"><span data-stu-id="bad8b-119">Value of `dwEventType`</span></span>|<span data-ttu-id="bad8b-120">Wert von `pFrame`</span><span class="sxs-lookup"><span data-stu-id="bad8b-120">Value of `pFrame`</span></span>|<span data-ttu-id="bad8b-121">Wert von `nOffset`</span><span class="sxs-lookup"><span data-stu-id="bad8b-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="bad8b-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="bad8b-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="bad8b-123">Der Frame, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="bad8b-123">The frame that threw the exception.</span></span>|<span data-ttu-id="bad8b-124">Der Anweisungs Zeiger im Frame.</span><span class="sxs-lookup"><span data-stu-id="bad8b-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="bad8b-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="bad8b-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="bad8b-126">Der Benutzercode Rahmen, der dem Punkt der ausgelösten Ausnahme am nächsten ist.</span><span class="sxs-lookup"><span data-stu-id="bad8b-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="bad8b-127">Der Anweisungs Zeiger im Frame.</span><span class="sxs-lookup"><span data-stu-id="bad8b-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="bad8b-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="bad8b-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="bad8b-129">Der Frame, der den catch-Handler enthält.</span><span class="sxs-lookup"><span data-stu-id="bad8b-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="bad8b-130">Der MSIL-Offset (Microsoft Intermediate Language) am Anfang des catch-Handlers.</span><span class="sxs-lookup"><span data-stu-id="bad8b-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="bad8b-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="bad8b-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="bad8b-132">NULL</span><span class="sxs-lookup"><span data-stu-id="bad8b-132">NULL</span></span>|<span data-ttu-id="bad8b-133">Nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="bad8b-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bad8b-134">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bad8b-134">Requirements</span></span>  

 <span data-ttu-id="bad8b-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bad8b-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bad8b-136">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bad8b-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bad8b-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bad8b-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bad8b-138">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bad8b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad8b-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bad8b-139">See also</span></span>

- [<span data-ttu-id="bad8b-140">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bad8b-140">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="bad8b-141">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bad8b-141">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
