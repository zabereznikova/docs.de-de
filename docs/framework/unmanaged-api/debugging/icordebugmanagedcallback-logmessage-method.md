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
ms.openlocfilehash: 2f89119c5c02c50dbecb0a17694bfc3eda8c732c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474331"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="fc897-102">ICorDebugManagedCallback::LogMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="fc897-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="fc897-103">Benachrichtigt den Debugger, dass ein common Language Runtime (CLR) verwalteter Thread eine Methode, in aufgerufen hat der <xref:System.Diagnostics.EventLog> Klasse, um ein Ereignis protokolliert.</span><span class="sxs-lookup"><span data-stu-id="fc897-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc897-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc897-104">Syntax</span></span>  
  
```  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc897-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fc897-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fc897-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne, die mit dem Thread, der das Ereignis protokolliert darstellt.</span><span class="sxs-lookup"><span data-stu-id="fc897-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="fc897-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="fc897-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="fc897-108">[in] Der Wert der [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) -Enumeration, der den Schweregrad der beschreibenden Meldung gibt an, die in das Ereignisprotokoll geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="fc897-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="fc897-109">[in] Ein Zeiger auf den Namen des Schalters Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="fc897-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="fc897-110">[in] Ein Zeiger auf die Meldung, die in das Ereignisprotokoll geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="fc897-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc897-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fc897-111">Requirements</span></span>  
 <span data-ttu-id="fc897-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc897-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc897-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc897-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc897-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc897-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc897-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc897-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc897-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc897-116">See also</span></span>
- [<span data-ttu-id="fc897-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fc897-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
