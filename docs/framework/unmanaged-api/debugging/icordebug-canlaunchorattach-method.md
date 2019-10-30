---
title: ICorDebug::CanLaunchOrAttach-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
ms.openlocfilehash: 805f9a5d1f2590a06bfa929c152bdfd13900531a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134280"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="84e81-102">ICorDebug::CanLaunchOrAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="84e81-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="84e81-103">Gibt ein HRESULT zurück, das angibt, ob das Starten eines neuen Prozesses oder das Anfügen an den angegebenen vorhandenen Prozess innerhalb des Kontexts der aktuellen Computer-und Laufzeitkonfiguration möglich ist.</span><span class="sxs-lookup"><span data-stu-id="84e81-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84e81-104">Syntax</span></span>  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84e81-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84e81-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="84e81-106">in Die ID eines vorhandenen Prozesses.</span><span class="sxs-lookup"><span data-stu-id="84e81-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="84e81-107">in Übergeben Sie `true`, wenn Sie mit aktiviertem Win32-Debugging starten möchten, oder wenn Sie das Win32-Debugging aktiviert haben. Andernfalls übergeben Sie `false`.</span><span class="sxs-lookup"><span data-stu-id="84e81-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84e81-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="84e81-108">Return Value</span></span>  
 <span data-ttu-id="84e81-109">S_OK, wenn die Debugdienste bestimmen, dass das Starten eines neuen Prozesses oder das Anfügen an den angegebenen Prozess möglich ist, wenn die Informationen über den aktuellen Computer und die Laufzeitkonfiguration angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="84e81-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="84e81-110">Mögliche HRESULT-Werte sind:</span><span class="sxs-lookup"><span data-stu-id="84e81-110">Possible HRESULT values are:</span></span>  
  
- <span data-ttu-id="84e81-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="84e81-111">S_OK</span></span>  
  
- <span data-ttu-id="84e81-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="84e81-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
- <span data-ttu-id="84e81-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="84e81-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
- <span data-ttu-id="84e81-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="84e81-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84e81-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84e81-115">Remarks</span></span>  
 <span data-ttu-id="84e81-116">Diese Methode dient nur zu Informationszwecken.</span><span class="sxs-lookup"><span data-stu-id="84e81-116">This method is purely informational.</span></span> <span data-ttu-id="84e81-117">Die-Schnittstelle hindert Sie nicht daran, einen Prozess zu starten oder anzufügen, unabhängig von dem Wert, der von `CanLaunchOrAttach`zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="84e81-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="84e81-118">Wenn Sie den Start mit Win32-Debugging aktivieren oder mit aktiviertem Win32-Debugging anfügen planen, übergeben Sie `true` für `win32DebuggingEnabled`.</span><span class="sxs-lookup"><span data-stu-id="84e81-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="84e81-119">Das von `CanLaunchOrAttach` zurückgegebene HRESULT unterscheidet sich möglicherweise, wenn Sie diese Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="84e81-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84e81-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84e81-120">Requirements</span></span>  
 <span data-ttu-id="84e81-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84e81-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84e81-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84e81-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84e81-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84e81-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84e81-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84e81-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e81-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84e81-125">See also</span></span>

- [<span data-ttu-id="84e81-126">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84e81-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
