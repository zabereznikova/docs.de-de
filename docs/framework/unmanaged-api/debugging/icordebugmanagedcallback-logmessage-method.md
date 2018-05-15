---
title: ICorDebugManagedCallback::LogMessage-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4c8494b1ffc80fc49acce01c5de0b3fd18c0f5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="7262b-102">ICorDebugManagedCallback::LogMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="7262b-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="7262b-103">Benachrichtigt den Debugger, dass ein common Language Runtime (CLR) verwaltet Thread eine Methode, in aufgerufen hat der <xref:System.Diagnostics.EventLog> Klasse ein Ereignis protokolliert.</span><span class="sxs-lookup"><span data-stu-id="7262b-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7262b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7262b-104">Syntax</span></span>  
  
```  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7262b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7262b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7262b-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Thread, der das Ereignis protokolliert darstellt.</span><span class="sxs-lookup"><span data-stu-id="7262b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="7262b-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="7262b-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="7262b-108">[in] Der Wert der [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) -Enumeration, der den Schweregrad der beschreibenden Meldung angibt, die in das Ereignisprotokoll geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="7262b-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="7262b-109">[in] Ein Zeiger auf den Namen des Switches Tracing.</span><span class="sxs-lookup"><span data-stu-id="7262b-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="7262b-110">[in] Ein Zeiger auf die Meldung, die in das Ereignisprotokoll geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="7262b-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7262b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7262b-111">Requirements</span></span>  
 <span data-ttu-id="7262b-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7262b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7262b-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7262b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7262b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7262b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7262b-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7262b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7262b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7262b-116">See Also</span></span>  
 [<span data-ttu-id="7262b-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7262b-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
