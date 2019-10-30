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
ms.openlocfilehash: fb8cfb2d1c5902ecd0d5858ef21ba48b65b12506
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125334"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="e6d21-102">ICorDebugController::Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="e6d21-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="e6d21-103">Beendet den Prozess mit dem angegebenen Exitcode.</span><span class="sxs-lookup"><span data-stu-id="e6d21-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6d21-104">Bei dieser Methode handelt es sich um einen Wrapper für die Win32-`TerminateProcess` Funktion.</span><span class="sxs-lookup"><span data-stu-id="e6d21-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="e6d21-105">Folglich verwendet `Terminate` den Exitcode auf die gleiche Weise, wie die Win32-`TerminateProcess` Funktion Sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="e6d21-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6d21-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6d21-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6d21-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6d21-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="e6d21-108">in Ein numerischer Wert, der der Exitcode ist.</span><span class="sxs-lookup"><span data-stu-id="e6d21-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="e6d21-109">Die gültigen numerischen Werte werden in Winbase. h definiert.</span><span class="sxs-lookup"><span data-stu-id="e6d21-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6d21-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6d21-110">Remarks</span></span>  
 <span data-ttu-id="e6d21-111">Wenn der Prozess beendet wird, wenn `Terminate` aufgerufen wird, sollte der Prozess mit der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) -Methode fortgesetzt werden, damit der Debugger eine Bestätigung der Beendigung durch [ICorDebugManagedCallback erhält: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) -oder [ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) -Rückruf.</span><span class="sxs-lookup"><span data-stu-id="e6d21-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6d21-112">Diese Methode wird nicht von einer Anwendungsdomäne implementiert.</span><span class="sxs-lookup"><span data-stu-id="e6d21-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="e6d21-113">Das heißt, es ist nicht auf <xref:System.AppDomain> Ebene implementiert.</span><span class="sxs-lookup"><span data-stu-id="e6d21-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6d21-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6d21-114">Requirements</span></span>  
 <span data-ttu-id="e6d21-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6d21-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6d21-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6d21-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6d21-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6d21-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6d21-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6d21-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d21-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6d21-119">See also</span></span>
