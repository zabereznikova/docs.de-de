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
ms.openlocfilehash: cf83124af5ced7bb6458564430ceb319ce7d680a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099156"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="51ebb-102">ICorDebugManagedCallback::LogMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="51ebb-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="51ebb-103">Benachrichtigt den Debugger, dass ein common Language Runtime (CLR) verwalteter Thread eine Methode, in aufgerufen hat der <xref:System.Diagnostics.EventLog> Klasse, um ein Ereignis protokolliert.</span><span class="sxs-lookup"><span data-stu-id="51ebb-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51ebb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51ebb-104">Syntax</span></span>  
  
```  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51ebb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="51ebb-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="51ebb-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne, die mit dem Thread, der das Ereignis protokolliert darstellt.</span><span class="sxs-lookup"><span data-stu-id="51ebb-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="51ebb-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="51ebb-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="51ebb-108">[in] Der Wert der [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) -Enumeration, der den Schweregrad der beschreibenden Meldung gibt an, die in das Ereignisprotokoll geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="51ebb-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="51ebb-109">[in] Ein Zeiger auf den Namen des Schalters Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="51ebb-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="51ebb-110">[in] Ein Zeiger auf die Meldung, die in das Ereignisprotokoll geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="51ebb-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51ebb-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51ebb-111">Requirements</span></span>  
 <span data-ttu-id="51ebb-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51ebb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51ebb-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51ebb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51ebb-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51ebb-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="51ebb-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="51ebb-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="51ebb-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51ebb-116">See also</span></span>

- [<span data-ttu-id="51ebb-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51ebb-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
