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
ms.openlocfilehash: b95e9f3a0d584511a2bcf156ed2c50a98f96d071
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379066"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="f873d-102">ICorDebugRemote::DebugActiveProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="f873d-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="f873d-103">Startet einen Prozess auf einem Remote Computer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="f873d-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f873d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f873d-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f873d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f873d-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="f873d-106">in Zeiger auf eine [icordebugremotetarget-Schnittstelle](icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f873d-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="f873d-107">Dieser Parameter wird verwendet, um den Computer zu ermitteln, auf dem der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f873d-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="f873d-108">in Die ID des Prozesses, an den der Debugger angefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f873d-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="f873d-109">[in] `true` , wenn sich der Debugger als Win32-Debugger für den Prozessverhalten soll und die nicht verwalteten Rückrufe versendet. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="f873d-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="f873d-110">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt, dem der Debugger angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="f873d-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f873d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f873d-111">Return Value</span></span>  
 <span data-ttu-id="f873d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f873d-112">S_OK</span></span>  
 <span data-ttu-id="f873d-113">Erfolgreich an den Prozess auf dem Remote Computer angefügt.</span><span class="sxs-lookup"><span data-stu-id="f873d-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="f873d-114">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="f873d-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="f873d-115">Das Anfügen an den Prozess auf dem Remote Computer ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="f873d-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f873d-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f873d-116">Remarks</span></span>  
 <span data-ttu-id="f873d-117">Das Debuggen im gemischten Modus wird in Silverlight nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f873d-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f873d-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f873d-118">Requirements</span></span>  
 <span data-ttu-id="f873d-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f873d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f873d-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f873d-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f873d-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f873d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f873d-122">**.NET Framework Versionen:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="f873d-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f873d-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f873d-123">See also</span></span>

- [<span data-ttu-id="f873d-124">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f873d-124">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="f873d-125">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f873d-125">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="f873d-126">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f873d-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
