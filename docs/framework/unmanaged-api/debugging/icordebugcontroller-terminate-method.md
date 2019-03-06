---
title: ICorDebugController::Terminate-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65a374f942697ee670507987c4a97a7977970b69
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481092"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="28ab0-102">ICorDebugController::Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="28ab0-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="28ab0-103">Beendet den Prozess mit den angegebenen Exitcode.</span><span class="sxs-lookup"><span data-stu-id="28ab0-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28ab0-104">Diese Methode ist ein Wrapper für die Win32- `TerminateProcess` Funktion.</span><span class="sxs-lookup"><span data-stu-id="28ab0-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="28ab0-105">Daher `Terminate` verwendet den Exitcode in der gleichen Weise wie die Win32 `TerminateProcess` Funktion wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="28ab0-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ab0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="28ab0-106">Syntax</span></span>  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28ab0-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="28ab0-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="28ab0-108">[in] Ein numerischer Wert, der den Exitcode.</span><span class="sxs-lookup"><span data-stu-id="28ab0-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="28ab0-109">Die gültigen numerischen Werte sind in Winbase.h definiert.</span><span class="sxs-lookup"><span data-stu-id="28ab0-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28ab0-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28ab0-110">Remarks</span></span>  
 <span data-ttu-id="28ab0-111">Wenn der Prozess, wenn beendet wird `Terminate` ist aufgerufen wird, der Prozess weiter mithilfe der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) Methode, damit der Debugger die Bestätigung für die Beendigung über empfängt die [ ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) oder [ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="28ab0-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28ab0-112">Diese Methode wird von einer Anwendungsdomäne nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="28ab0-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="28ab0-113">D. h. es ist nicht auf implementiert die <xref:System.AppDomain> Ebene.</span><span class="sxs-lookup"><span data-stu-id="28ab0-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28ab0-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28ab0-114">Requirements</span></span>  
 <span data-ttu-id="28ab0-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28ab0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28ab0-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28ab0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28ab0-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28ab0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28ab0-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28ab0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ab0-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28ab0-119">See also</span></span>

