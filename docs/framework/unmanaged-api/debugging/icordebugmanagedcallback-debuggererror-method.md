---
title: ICorDebugManagedCallback::DebuggerError-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
ms.openlocfilehash: 8f3697f8b193319ebb7b155ad79b8ec25a0a2266
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205276"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="262e6-102">ICorDebugManagedCallback::DebuggerError-Methode</span><span class="sxs-lookup"><span data-stu-id="262e6-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="262e6-103">Benachrichtigt den Debugger, dass beim Verarbeiten eines Ereignisses aus dem Common Language Runtime (CLR) ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="262e6-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="262e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="262e6-104">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="262e6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="262e6-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="262e6-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, in dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="262e6-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="262e6-107">in Der HRESULT-Wert, der vom Ereignishandler zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="262e6-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="262e6-108">in Eine ganze Zahl, die den CLR-Fehler angibt.</span><span class="sxs-lookup"><span data-stu-id="262e6-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="262e6-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="262e6-109">Remarks</span></span>  
 <span data-ttu-id="262e6-110">Der Prozess kann je nach Art des Fehlers in den Pass-Through-Modus versetzt werden.</span><span class="sxs-lookup"><span data-stu-id="262e6-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="262e6-111">Der `DebugError` Rückruf gibt an, dass debuggingdienste aufgrund eines Fehlers deaktiviert wurden. Daher sollten Debugger dem Benutzer die Fehlermeldung zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="262e6-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="262e6-112">[ICorDebugProcess:: GetId](icordebugprocess-getid-method.md) kann sicher aufgerufen werden, aber alle anderen Methoden, einschließlich [ICorDebug::](icordebug-terminate-method.md)End, dürfen nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="262e6-112">[ICorDebugProcess::GetID](icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="262e6-113">Der Debugger sollte Betriebssystemfunktionen zum Beenden von Prozessen verwenden.</span><span class="sxs-lookup"><span data-stu-id="262e6-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="262e6-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="262e6-114">Requirements</span></span>  
 <span data-ttu-id="262e6-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="262e6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="262e6-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="262e6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="262e6-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="262e6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="262e6-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="262e6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="262e6-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="262e6-119">See also</span></span>

- [<span data-ttu-id="262e6-120">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="262e6-120">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
