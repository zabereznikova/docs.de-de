---
title: ICorDebugRemote::DebugActiveProcessEx-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45b919d90454c9424cadb1d4dfc3b0dfb09e5053
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782771"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="b5ac8-102">ICorDebugRemote::DebugActiveProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="b5ac8-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="b5ac8-103">Startet einen Prozess auf einem Remotecomputer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="b5ac8-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5ac8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5ac8-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5ac8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5ac8-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="b5ac8-106">[in] Zeiger auf eine [ICorDebugRemoteTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b5ac8-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="b5ac8-107">Dieser Parameter wird verwendet, um den Computer zu ermitteln, auf dem der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b5ac8-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="b5ac8-108">[in] Die ID des Prozesses, für die der Debugger wird angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b5ac8-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="b5ac8-109">[in] `true` Wenn der Debugger sollte sich so wie Win32-Debugger für den Prozess Verhalten und die nicht verwalteten Rückrufe; anderenfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="b5ac8-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="b5ac8-110">[out] Ein Zeiger auf die Adresse ein "ICorDebugProcess"-Objekt, das den Prozess darstellt, an dem der Debugger angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="b5ac8-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5ac8-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b5ac8-111">Return Value</span></span>  
 <span data-ttu-id="b5ac8-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b5ac8-112">S_OK</span></span>  
 <span data-ttu-id="b5ac8-113">Erfolgreich an den Prozess auf dem Remotecomputer angefügt.</span><span class="sxs-lookup"><span data-stu-id="b5ac8-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="b5ac8-114">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="b5ac8-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="b5ac8-115">Anfügen an den Prozess auf dem Remotecomputer nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b5ac8-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5ac8-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5ac8-116">Remarks</span></span>  
 <span data-ttu-id="b5ac8-117">Debuggen im gemischten Modus wird in Silverlight nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b5ac8-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5ac8-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b5ac8-118">Requirements</span></span>  
 <span data-ttu-id="b5ac8-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5ac8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5ac8-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5ac8-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5ac8-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5ac8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5ac8-122">**.NET Framework-Versionen:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="b5ac8-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5ac8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5ac8-123">See also</span></span>

- [<span data-ttu-id="b5ac8-124">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b5ac8-124">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="b5ac8-125">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b5ac8-125">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="b5ac8-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b5ac8-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
