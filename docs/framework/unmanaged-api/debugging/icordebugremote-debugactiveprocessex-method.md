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
ms.openlocfilehash: c9847fd6122aa32c95aecd5643a62a6775ae38d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712117"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="082b9-102">ICorDebugRemote::DebugActiveProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="082b9-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>

<span data-ttu-id="082b9-103">Startet einen Prozess auf einem Remote Computer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="082b9-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="082b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="082b9-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="082b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="082b9-105">Parameters</span></span>  

 `pRemoteTarget`  
 <span data-ttu-id="082b9-106">in Zeiger auf eine [icordebugremotetarget-Schnittstelle](icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="082b9-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="082b9-107">Dieser Parameter wird verwendet, um den Computer zu ermitteln, auf dem der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="082b9-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="082b9-108">in Die ID des Prozesses, an den der Debugger angefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="082b9-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="082b9-109">[in] `true` , wenn sich der Debugger als Win32-Debugger für den Prozessverhalten soll und die nicht verwalteten Rückrufe versendet. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="082b9-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="082b9-110">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt, dem der Debugger angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="082b9-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="082b9-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="082b9-111">Return Value</span></span>  

 <span data-ttu-id="082b9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="082b9-112">S_OK</span></span>  
 <span data-ttu-id="082b9-113">Erfolgreich an den Prozess auf dem Remote Computer angefügt.</span><span class="sxs-lookup"><span data-stu-id="082b9-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="082b9-114">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="082b9-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="082b9-115">Das Anfügen an den Prozess auf dem Remote Computer ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="082b9-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="082b9-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="082b9-116">Remarks</span></span>  

 <span data-ttu-id="082b9-117">Das Debuggen im gemischten Modus wird in Silverlight nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="082b9-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="082b9-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="082b9-118">Requirements</span></span>  

 <span data-ttu-id="082b9-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="082b9-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="082b9-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="082b9-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="082b9-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="082b9-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="082b9-122">**.NET Framework Versionen:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="082b9-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="082b9-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="082b9-123">See also</span></span>

- [<span data-ttu-id="082b9-124">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="082b9-124">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="082b9-125">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="082b9-125">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="082b9-126">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="082b9-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
