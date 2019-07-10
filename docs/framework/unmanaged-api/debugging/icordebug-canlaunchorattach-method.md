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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af933be9edc0d0fe7249f33800fe259ddc779aeb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738314"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="c06b8-102">ICorDebug::CanLaunchOrAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="c06b8-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="c06b8-103">Gibt ein HRESULT, der angibt, ob ein neuer Prozess gestartet oder an den angegebenen vorhandenen Prozess anfügen innerhalb des Kontexts der aktuellen Computer und -Runtime-Konfiguration möglich ist.</span><span class="sxs-lookup"><span data-stu-id="c06b8-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c06b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c06b8-104">Syntax</span></span>  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c06b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c06b8-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="c06b8-106">[in] Die ID eines vorhandenen Prozesses.</span><span class="sxs-lookup"><span data-stu-id="c06b8-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="c06b8-107">[in] Übergeben Sie `true` , wenn Sie, starten Sie mit der Win32-Debuggen aktiviert möchten ist, oder übergeben Sie eine Verbindung mit der Win32-Debuggen aktiviert ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="c06b8-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c06b8-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c06b8-108">Return Value</span></span>  
 <span data-ttu-id="c06b8-109">S_OK, wenn die Debuggen von Diensten, die ein neuer Prozess gestartet oder das Anfügen an den Prozess ermitteln kann, erhält die Informationen über die aktuelle Konfiguration für Computer und der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c06b8-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="c06b8-110">HRESULT Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="c06b8-110">Possible HRESULT values are:</span></span>  
  
- <span data-ttu-id="c06b8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c06b8-111">S_OK</span></span>  
  
- <span data-ttu-id="c06b8-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="c06b8-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
- <span data-ttu-id="c06b8-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="c06b8-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
- <span data-ttu-id="c06b8-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="c06b8-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c06b8-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c06b8-115">Remarks</span></span>  
 <span data-ttu-id="c06b8-116">Diese Methode dient ausschließlich zu Informationszwecken.</span><span class="sxs-lookup"><span data-stu-id="c06b8-116">This method is purely informational.</span></span> <span data-ttu-id="c06b8-117">Die Schnittstelle beenden Sie nicht starten oder Anfügen an einen Prozess, unabhängig vom Wert von zurückgegebenen `CanLaunchOrAttach`.</span><span class="sxs-lookup"><span data-stu-id="c06b8-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="c06b8-118">Wenn Sie planen, starten Sie mit der Win32-Debuggen aktiviert oder Verbindung mit Win32-Debuggen aktiviert, übergeben Sie `true` für `win32DebuggingEnabled`.</span><span class="sxs-lookup"><span data-stu-id="c06b8-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="c06b8-119">Das HRESULT zurückgegeben wird, indem `CanLaunchOrAttach` können abweichen, wenn Sie diese Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="c06b8-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c06b8-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c06b8-120">Requirements</span></span>  
 <span data-ttu-id="c06b8-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c06b8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c06b8-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c06b8-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c06b8-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c06b8-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c06b8-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c06b8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c06b8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c06b8-125">See also</span></span>

- [<span data-ttu-id="c06b8-126">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c06b8-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
