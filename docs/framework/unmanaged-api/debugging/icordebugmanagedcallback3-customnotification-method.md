---
title: ICorDebugManagedCallback3::CustomNotification-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9c42443b0d1e355d4233909357c341763298160e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="1b111-102">ICorDebugManagedCallback3::CustomNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="1b111-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="1b111-103">Gibt an, dass eine benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="1b111-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b111-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b111-104">Syntax</span></span>  
  
```  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b111-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b111-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="1b111-106">[in] Ein Zeiger auf den Thread, der die Benachrichtigung ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b111-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="1b111-107">[in] Ein Zeiger auf die Anwendungsdomäne, die den Thread enthält, der die Benachrichtigung ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b111-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b111-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1b111-108">Return Value</span></span>  
 <span data-ttu-id="1b111-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1b111-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1b111-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b111-110">HRESULT</span></span>|<span data-ttu-id="1b111-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b111-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b111-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b111-112">S_OK</span></span>|<span data-ttu-id="1b111-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1b111-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="1b111-114">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="1b111-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b111-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b111-115">Remarks</span></span>  
 <span data-ttu-id="1b111-116">Ein nachfolgender Aufruf von der [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) Methode ruft die Threadobjekt, das übergeben wurde die <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="1b111-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1b111-117">Typ des Threadobjekts muss zuvor aktiviert werden durch Aufrufen der [ICorDebugProcess3:: SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="1b111-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="1b111-118">Der Debugger kann typspezifische Parameter aus den Feldern des Threadobjekts lesen und Antworten in Feldern speichern kann.</span><span class="sxs-lookup"><span data-stu-id="1b111-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="1b111-119">Die [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Schnittstelle erzwingt keine Richtlinie für die Typen von Benachrichtigungen oder dessen Inhalt und die Semantik der Benachrichtigungen dienen ausschließlich der einen Vertrag zwischen dem Debugger, Anwendungen und .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1b111-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b111-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b111-120">Requirements</span></span>  
 <span data-ttu-id="1b111-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b111-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b111-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b111-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b111-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b111-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b111-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b111-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b111-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b111-125">See Also</span></span>  
 [<span data-ttu-id="1b111-126">ICorDebugManagedCallback3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b111-126">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 [<span data-ttu-id="1b111-127">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1b111-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1b111-128">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1b111-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
