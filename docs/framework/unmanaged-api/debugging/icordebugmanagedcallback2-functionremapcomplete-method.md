---
title: ICorDebugManagedCallback2::FunctionRemapComplete-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1909b7123bde23058e42394db86af83d08e2354
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685385"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="75af6-102">ICorDebugManagedCallback2::FunctionRemapComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="75af6-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="75af6-103">Benachrichtigt den Debugger, dass die Ausführung von Code auf eine neue Version einer bearbeiteten Funktion gewechselt hat.</span><span class="sxs-lookup"><span data-stu-id="75af6-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75af6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="75af6-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75af6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="75af6-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="75af6-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne, die mit der bearbeiteten Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="75af6-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="75af6-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem die neuzuordnung Breakpoint erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="75af6-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="75af6-108">[in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das die Version der Funktion, die derzeit ausgeführt wird, auf dem Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="75af6-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75af6-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75af6-109">Remarks</span></span>  
 <span data-ttu-id="75af6-110">Dieser Rückruf ermöglicht dem Debugger die Möglichkeit, vorhandenen Stepper neu zu erstellen, die zuvor vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="75af6-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75af6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="75af6-111">Requirements</span></span>  
 <span data-ttu-id="75af6-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75af6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75af6-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75af6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75af6-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75af6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75af6-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75af6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75af6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75af6-116">See also</span></span>
- [<span data-ttu-id="75af6-117">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75af6-117">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="75af6-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75af6-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
