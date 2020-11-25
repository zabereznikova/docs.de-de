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
ms.openlocfilehash: 195c7e1e7c61fd6ac8a21226b52e3782d2f7e421
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723492"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="a41f2-102">ICorDebug::CanLaunchOrAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="a41f2-102">ICorDebug::CanLaunchOrAttach Method</span></span>

<span data-ttu-id="a41f2-103">Gibt ein HRESULT zurück, das angibt, ob das Starten eines neuen Prozesses oder das Anfügen an den angegebenen vorhandenen Prozess innerhalb des Kontexts der aktuellen Computer-und Laufzeitkonfiguration möglich ist.</span><span class="sxs-lookup"><span data-stu-id="a41f2-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a41f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a41f2-104">Syntax</span></span>  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a41f2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a41f2-105">Parameters</span></span>  

 `dwProcessId`  
 <span data-ttu-id="a41f2-106">in Die ID eines vorhandenen Prozesses.</span><span class="sxs-lookup"><span data-stu-id="a41f2-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="a41f2-107">in Übergeben `true` Sie, wenn Sie planen, mit aktiviertem Win32-Debugging zu starten oder mit aktiviertem Win32-Debugging anzufügen. Andernfalls übergeben Sie `false` .</span><span class="sxs-lookup"><span data-stu-id="a41f2-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a41f2-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a41f2-108">Return Value</span></span>  

 <span data-ttu-id="a41f2-109">S_OK, wenn die Debugdienste bestimmen, dass das Starten eines neuen Prozesses oder das Anfügen an den angegebenen Prozess möglich ist, wenn die Informationen über den aktuellen Computer und die Laufzeitkonfiguration angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a41f2-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="a41f2-110">Mögliche HRESULT-Werte sind:</span><span class="sxs-lookup"><span data-stu-id="a41f2-110">Possible HRESULT values are:</span></span>  
  
- <span data-ttu-id="a41f2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a41f2-111">S_OK</span></span>  
  
- <span data-ttu-id="a41f2-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="a41f2-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
- <span data-ttu-id="a41f2-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="a41f2-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
- <span data-ttu-id="a41f2-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="a41f2-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a41f2-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a41f2-115">Remarks</span></span>  

 <span data-ttu-id="a41f2-116">Diese Methode dient nur zu Informationszwecken.</span><span class="sxs-lookup"><span data-stu-id="a41f2-116">This method is purely informational.</span></span> <span data-ttu-id="a41f2-117">Die-Schnittstelle hindert Sie nicht daran, einen Prozess zu starten oder anzufügen, unabhängig von dem Wert, der von zurückgegeben wird `CanLaunchOrAttach` .</span><span class="sxs-lookup"><span data-stu-id="a41f2-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="a41f2-118">Wenn Sie planen, mit aktiviertem Win32-Debugging oder Attach mit aktiviertem Win32-Debugging zu starten, geben Sie `true` für an `win32DebuggingEnabled` .</span><span class="sxs-lookup"><span data-stu-id="a41f2-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="a41f2-119">Das von zurückgegebene HRESULT `CanLaunchOrAttach` unterscheidet sich möglicherweise, wenn Sie diese Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="a41f2-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a41f2-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a41f2-120">Requirements</span></span>  

 <span data-ttu-id="a41f2-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a41f2-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a41f2-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a41f2-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a41f2-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a41f2-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a41f2-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a41f2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a41f2-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a41f2-125">See also</span></span>

- [<span data-ttu-id="a41f2-126">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a41f2-126">ICorDebug Interface</span></span>](icordebug-interface.md)
