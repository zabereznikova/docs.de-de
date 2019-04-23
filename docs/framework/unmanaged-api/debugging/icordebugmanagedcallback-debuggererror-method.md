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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd7909b94343b1fb83836f5c369ddc1993f049d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191168"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="53eae-102">ICorDebugManagedCallback::DebuggerError-Methode</span><span class="sxs-lookup"><span data-stu-id="53eae-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="53eae-103">Benachrichtigt den Debugger, dass ein Fehler aufgetreten ist, bei dem Versuch, ein Ereignis von der common Language Runtime (CLR) zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="53eae-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53eae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53eae-104">Syntax</span></span>  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53eae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="53eae-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="53eae-106">[in] Ein Zeiger auf ein "ICorDebugProcess"-Objekt, das den Prozess darstellt, in dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="53eae-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="53eae-107">[in] Der HRESULT-Wert, der aus dem Ereignishandler zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="53eae-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="53eae-108">[in] Eine ganze Zahl, die den CLR-Fehler angibt.</span><span class="sxs-lookup"><span data-stu-id="53eae-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53eae-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53eae-109">Remarks</span></span>  
 <span data-ttu-id="53eae-110">Der Prozess kann in den Pass-Through-Modus, je nach Art des Fehlers platziert werden.</span><span class="sxs-lookup"><span data-stu-id="53eae-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="53eae-111">Die `DebugError` -Rückruf gibt an, dass das Debuggen von Diensten aufgrund eines Fehlers deaktiviert wurden, sodass der Debugger die Fehlermeldung dem Benutzer verfügbar machen soll.</span><span class="sxs-lookup"><span data-stu-id="53eae-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="53eae-112">[ICorDebugProcess:: GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) kann sicher aufrufen, aber alle anderen Methoden, einschließlich [ICorDebug:: Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), sollte nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="53eae-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="53eae-113">Der Debugger sollte Betriebssystemfunktionen zum Beenden von Prozessen verwenden.</span><span class="sxs-lookup"><span data-stu-id="53eae-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53eae-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="53eae-114">Requirements</span></span>  
 <span data-ttu-id="53eae-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53eae-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53eae-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53eae-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53eae-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53eae-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53eae-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53eae-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53eae-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53eae-119">See also</span></span>

- [<span data-ttu-id="53eae-120">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53eae-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
