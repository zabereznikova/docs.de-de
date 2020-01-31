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
ms.openlocfilehash: 851a127c117b826c271dd021c41cfdb36045a1ff
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783752"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="6770f-102">ICorDebugController::Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="6770f-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="6770f-103">Beendet den Prozess mit dem angegebenen Exitcode.</span><span class="sxs-lookup"><span data-stu-id="6770f-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6770f-104">Bei dieser Methode handelt es sich um einen Wrapper für die Win32-`TerminateProcess` Funktion.</span><span class="sxs-lookup"><span data-stu-id="6770f-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="6770f-105">Folglich verwendet `Terminate` den Exitcode auf die gleiche Weise, wie die Win32-`TerminateProcess` Funktion Sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="6770f-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6770f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6770f-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6770f-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="6770f-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="6770f-108">in Ein numerischer Wert, der der Exitcode ist.</span><span class="sxs-lookup"><span data-stu-id="6770f-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="6770f-109">Die gültigen numerischen Werte werden in Winbase. h definiert.</span><span class="sxs-lookup"><span data-stu-id="6770f-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6770f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6770f-110">Remarks</span></span>  
 <span data-ttu-id="6770f-111">Wenn der Prozess beendet wird, wenn `Terminate` aufgerufen wird, sollte der Prozess mit der [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) -Methode fortgesetzt werden, damit der Debugger eine Bestätigung der Beendigung durch den [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) -oder [ICorDebugManagedCallback:: ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) -Rückruf erhält.</span><span class="sxs-lookup"><span data-stu-id="6770f-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6770f-112">Diese Methode wird nicht von einer Anwendungsdomäne implementiert.</span><span class="sxs-lookup"><span data-stu-id="6770f-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="6770f-113">Das heißt, es ist nicht auf <xref:System.AppDomain> Ebene implementiert.</span><span class="sxs-lookup"><span data-stu-id="6770f-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6770f-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6770f-114">Requirements</span></span>  
 <span data-ttu-id="6770f-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6770f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6770f-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6770f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6770f-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6770f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6770f-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6770f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6770f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6770f-119">See also</span></span>
