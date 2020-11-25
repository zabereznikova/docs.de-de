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
ms.openlocfilehash: db6ccd63bbeadd7dcff1c7f8491b59017d431d12
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720697"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="71a63-102">ICorDebugManagedCallback::LogSwitch-Methode</span><span class="sxs-lookup"><span data-stu-id="71a63-102">ICorDebugManagedCallback::LogSwitch Method</span></span>

<span data-ttu-id="71a63-103">Benachrichtigt den Debugger, dass ein von Common Language Runtime (CLR) verwalteter Thread eine Methode in der-Klasse aufgerufen hat, <xref:System.Diagnostics.Switch> um einen Debug/Tracing-Switch zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="71a63-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71a63-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71a63-104">Syntax</span></span>  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71a63-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71a63-105">Parameters</span></span>  

 `PAppDomain`  
 <span data-ttu-id="71a63-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem verwalteten Thread darstellt, der einen Debug/Tracing-Switch erstellt, geändert oder gelöscht hat.</span><span class="sxs-lookup"><span data-stu-id="71a63-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="71a63-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="71a63-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="71a63-108">in Ein-Wert, der den Schweregrad der beschreibenden Meldung angibt, die in das Ereignisprotokoll geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="71a63-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="71a63-109">in Ein Wert der [LogSwitchCallReason](logswitchcallreason-enumeration.md) -Enumeration, der den Vorgang angibt, der für den Debugger-oder Ablauf Verfolgungs Schalter ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="71a63-109">[in] A value of the [LogSwitchCallReason](logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="71a63-110">in Ein Zeiger auf den Namen des Schalters für Debugging/Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="71a63-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="71a63-111">in Ein Zeiger auf den Namen des übergeordneten Elements des Schalters für Debuggen/Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="71a63-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71a63-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="71a63-112">Requirements</span></span>  

 <span data-ttu-id="71a63-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71a63-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71a63-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71a63-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71a63-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71a63-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71a63-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71a63-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a63-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71a63-117">See also</span></span>

- [<span data-ttu-id="71a63-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71a63-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
