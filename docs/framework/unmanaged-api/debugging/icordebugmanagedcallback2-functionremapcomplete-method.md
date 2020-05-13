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
ms.openlocfilehash: d49992b1f4b25586f6171a51b351a25d453560f2
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212151"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="9d99a-102">ICorDebugManagedCallback2::FunctionRemapComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="9d99a-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="9d99a-103">Benachrichtigt den Debugger, dass die Codeausführung zu einer neuen Version einer bearbeiteten Funktion gewechselt hat.</span><span class="sxs-lookup"><span data-stu-id="9d99a-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d99a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d99a-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d99a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9d99a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9d99a-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die die bearbeitete Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="9d99a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="9d99a-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem der Umwandlungs-Breakpoint gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="9d99a-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="9d99a-108">in Ein Zeiger auf ein ICorDebugFunction-Objekt, das die Version der Funktion darstellt, die derzeit auf dem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9d99a-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d99a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d99a-109">Remarks</span></span>  
 <span data-ttu-id="9d99a-110">Mit diesem Rückruf hat der Debugger die Möglichkeit, alle zuvor vorhandenen Steppers neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9d99a-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d99a-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9d99a-111">Requirements</span></span>  
 <span data-ttu-id="9d99a-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d99a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d99a-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d99a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d99a-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d99a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d99a-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d99a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d99a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d99a-116">See also</span></span>

- [<span data-ttu-id="9d99a-117">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d99a-117">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="9d99a-118">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d99a-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
