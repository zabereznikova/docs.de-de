---
title: ICorDebugManagedCallback::LogSwitch-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d7432771a7d8eee9cea10f883dd3bd91f5ffb74
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761388"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="6fa0f-102">ICorDebugManagedCallback::LogSwitch-Methode</span><span class="sxs-lookup"><span data-stu-id="6fa0f-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="6fa0f-103">Benachrichtigt den Debugger, dass ein common Language Runtime (CLR) verwalteter Thread eine Methode, in aufgerufen hat der <xref:System.Diagnostics.Switch> Klasse zu erstellen, ändern oder Löschen einen Debug-/Ablaufverfolgungsschalter.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa0f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fa0f-104">Syntax</span></span>  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fa0f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6fa0f-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="6fa0f-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne, die mit dem Thread, der erstellt, geändert oder gelöscht einen Debug-/Ablaufverfolgungsschalter darstellt.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="6fa0f-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="6fa0f-108">[in] Ein Wert, der den Schweregrad der beschreibenden Meldung gibt an, die in das Ereignisprotokoll geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="6fa0f-109">[in] Der Wert der [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) -Enumeration, der den Vorgang angibt, die für die Debug-/Ablaufverfolgungsschalter ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="6fa0f-110">[in] Ein Zeiger auf den Namen der Debug-/Ablaufverfolgungsschalter.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="6fa0f-111">[in] Ein Zeiger auf den Namen des übergeordneten Elements der Debug-/Ablaufverfolgungsschalter.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fa0f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6fa0f-112">Requirements</span></span>  
 <span data-ttu-id="6fa0f-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fa0f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fa0f-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fa0f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fa0f-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fa0f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fa0f-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fa0f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fa0f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fa0f-117">See also</span></span>

- [<span data-ttu-id="6fa0f-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fa0f-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
