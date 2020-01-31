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
ms.openlocfilehash: 46c8b3fb2c9e7c353f74ef589e21f2a61df618fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777313"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="ad7a6-102">ICorDebugManagedCallback::LogSwitch-Methode</span><span class="sxs-lookup"><span data-stu-id="ad7a6-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="ad7a6-103">Benachrichtigt den Debugger, dass ein von Common Language Runtime (CLR) verwalteter Thread eine Methode in der <xref:System.Diagnostics.Switch>-Klasse aufgerufen hat, um einen Debug/Tracing-Switch zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ad7a6-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad7a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad7a6-104">Syntax</span></span>  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad7a6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ad7a6-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="ad7a6-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem verwalteten Thread darstellt, der einen Debug/Tracing-Switch erstellt, geändert oder gelöscht hat.</span><span class="sxs-lookup"><span data-stu-id="ad7a6-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ad7a6-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="ad7a6-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="ad7a6-108">in Ein-Wert, der den Schweregrad der beschreibenden Meldung angibt, die in das Ereignisprotokoll geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="ad7a6-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="ad7a6-109">in Ein Wert der [LogSwitchCallReason](logswitchcallreason-enumeration.md) -Enumeration, der den Vorgang angibt, der für den Debugger-oder Ablauf Verfolgungs Schalter ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ad7a6-109">[in] A value of the [LogSwitchCallReason](logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="ad7a6-110">in Ein Zeiger auf den Namen des Schalters für Debugging/Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="ad7a6-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="ad7a6-111">in Ein Zeiger auf den Namen des übergeordneten Elements des Schalters für Debuggen/Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="ad7a6-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad7a6-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ad7a6-112">Requirements</span></span>  
 <span data-ttu-id="ad7a6-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad7a6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad7a6-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad7a6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad7a6-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad7a6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad7a6-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad7a6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad7a6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad7a6-117">See also</span></span>

- [<span data-ttu-id="ad7a6-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad7a6-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
