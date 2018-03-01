---
title: ICorDebug::CanLaunchOrAttach-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 62ebdb178ef7aaa16bcc163e42662e1d69f1f6f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="cbcf8-102">ICorDebug::CanLaunchOrAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="cbcf8-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="cbcf8-103">Gibt ein HRESULT, das angibt, ob ein neuer Prozess gestartet oder Anhängen an den angegebenen vorhandenen Prozess innerhalb des Kontexts der aktuellen Konfiguration für Computer und die Common Language Runtime möglich ist.</span><span class="sxs-lookup"><span data-stu-id="cbcf8-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbcf8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbcf8-104">Syntax</span></span>  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbcf8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cbcf8-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="cbcf8-106">[in] Die ID der eine vorhandene Prozessressource.</span><span class="sxs-lookup"><span data-stu-id="cbcf8-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="cbcf8-107">[in] Übergeben Sie `true` , wenn Sie planen, mit aktiviertem Win32-Debuggen zu starten, oder übergeben Sie eine Verbindung mit der Win32-Debuggen aktiviert ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="cbcf8-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbcf8-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cbcf8-108">Return Value</span></span>  
 <span data-ttu-id="cbcf8-109">S_OK, wenn der Debugdienste bestimmen, die einen neuen Prozess starten oder Anhängen an den angegebenen Prozess ist möglich, die Informationen zur aktuellen Computer und zur Laufzeit angegeben.</span><span class="sxs-lookup"><span data-stu-id="cbcf8-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="cbcf8-110">HRESULT Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="cbcf8-110">Possible HRESULT values are:</span></span>  
  
-   <span data-ttu-id="cbcf8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cbcf8-111">S_OK</span></span>  
  
-   <span data-ttu-id="cbcf8-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="cbcf8-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
-   <span data-ttu-id="cbcf8-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="cbcf8-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
-   <span data-ttu-id="cbcf8-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="cbcf8-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbcf8-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cbcf8-115">Remarks</span></span>  
 <span data-ttu-id="cbcf8-116">Diese Methode ist ausschließlich zu Informationszwecken.</span><span class="sxs-lookup"><span data-stu-id="cbcf8-116">This method is purely informational.</span></span> <span data-ttu-id="cbcf8-117">Die Schnittstelle beenden Sie nicht starten oder Anfügen an einen Prozess, unabhängig vom Wert von zurückgegebenen `CanLaunchOrAttach`.</span><span class="sxs-lookup"><span data-stu-id="cbcf8-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="cbcf8-118">Wenn Sie beabsichtigen, mit aktiviertem Win32-Debuggen starten oder Anhängen, mit der Win32-Debuggen aktiviert, übergeben Sie `true` für `win32DebuggingEnabled`.</span><span class="sxs-lookup"><span data-stu-id="cbcf8-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="cbcf8-119">Zurückgegebenes HRESULT `CanLaunchOrAttach` unterscheiden, wenn Sie diese Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="cbcf8-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbcf8-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cbcf8-120">Requirements</span></span>  
 <span data-ttu-id="cbcf8-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbcf8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbcf8-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbcf8-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbcf8-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbcf8-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbcf8-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbcf8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbcf8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbcf8-125">See Also</span></span>  
 [<span data-ttu-id="cbcf8-126">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cbcf8-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
