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
ms.openlocfilehash: 28b9fb5a25981e5e37a5f1bbb797baeac45e0028
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793576"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="7d992-102">ICorDebug::CanLaunchOrAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="7d992-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="7d992-103">Gibt ein HRESULT zurück, das angibt, ob das Starten eines neuen Prozesses oder das Anfügen an den angegebenen vorhandenen Prozess innerhalb des Kontexts der aktuellen Computer-und Laufzeitkonfiguration möglich ist.</span><span class="sxs-lookup"><span data-stu-id="7d992-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d992-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d992-104">Syntax</span></span>  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d992-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7d992-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="7d992-106">in Die ID eines vorhandenen Prozesses.</span><span class="sxs-lookup"><span data-stu-id="7d992-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="7d992-107">in Übergeben Sie `true`, wenn Sie mit aktiviertem Win32-Debugging starten möchten, oder wenn Sie das Win32-Debugging aktiviert haben. Andernfalls übergeben Sie `false`.</span><span class="sxs-lookup"><span data-stu-id="7d992-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d992-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7d992-108">Return Value</span></span>  
 <span data-ttu-id="7d992-109">S_OK, wenn die Debugdienste bestimmen, dass das Starten eines neuen Prozesses oder das Anfügen an den angegebenen Prozess möglich ist, wenn die Informationen über den aktuellen Computer und die Laufzeitkonfiguration angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7d992-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="7d992-110">Mögliche HRESULT-Werte sind:</span><span class="sxs-lookup"><span data-stu-id="7d992-110">Possible HRESULT values are:</span></span>  
  
- <span data-ttu-id="7d992-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d992-111">S_OK</span></span>  
  
- <span data-ttu-id="7d992-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="7d992-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
- <span data-ttu-id="7d992-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="7d992-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
- <span data-ttu-id="7d992-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="7d992-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d992-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d992-115">Remarks</span></span>  
 <span data-ttu-id="7d992-116">Diese Methode dient nur zu Informationszwecken.</span><span class="sxs-lookup"><span data-stu-id="7d992-116">This method is purely informational.</span></span> <span data-ttu-id="7d992-117">Die-Schnittstelle hindert Sie nicht daran, einen Prozess zu starten oder anzufügen, unabhängig von dem Wert, der von `CanLaunchOrAttach`zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7d992-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="7d992-118">Wenn Sie den Start mit Win32-Debugging aktivieren oder mit aktiviertem Win32-Debugging anfügen planen, übergeben Sie `true` für `win32DebuggingEnabled`.</span><span class="sxs-lookup"><span data-stu-id="7d992-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="7d992-119">Das von `CanLaunchOrAttach` zurückgegebene HRESULT unterscheidet sich möglicherweise, wenn Sie diese Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d992-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d992-120">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d992-120">Requirements</span></span>  
 <span data-ttu-id="7d992-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d992-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d992-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d992-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d992-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d992-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d992-124">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d992-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d992-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d992-125">See also</span></span>

- [<span data-ttu-id="7d992-126">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d992-126">ICorDebug Interface</span></span>](icordebug-interface.md)
