---
title: ICoreClrDebugTarget::EnumRuntimes-Methode
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
ms.openlocfilehash: 2579bed9ae432a2b9460c421c6ee5bdc40d1e149
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121839"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="b0d65-102">ICoreClrDebugTarget::EnumRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="b0d65-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="b0d65-103">Listet die CLR-Laufzeiten (Common Language Runtime) im angegebenen Prozess auf, der auf einem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b0d65-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0d65-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0d65-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0d65-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b0d65-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="b0d65-106">[in] Die interne Prozess-ID des Prozesses, für den Laufzeiten aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0d65-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="b0d65-107">Dies wird aus der entsprechenden [coreclrdebugprocinfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)`m_dwInternalID`.</span><span class="sxs-lookup"><span data-stu-id="b0d65-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="b0d65-108">[out] Die Anzahl der in `ppRuntimes` zurückgegebenen Laufzeiten.</span><span class="sxs-lookup"><span data-stu-id="b0d65-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="b0d65-109">Dieser Wert kann 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="b0d65-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="b0d65-110">vorgenommen Ein Array von [coreclrdebugruntimeingefo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) -Strukturen, die die Laufzeiten darstellen, die im Remote Ziel Prozess geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="b0d65-110">[out] An array of [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0d65-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b0d65-111">Return Value</span></span>  
 <span data-ttu-id="b0d65-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0d65-112">S_OK</span></span>  
 <span data-ttu-id="b0d65-113">Erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="b0d65-113">Success.</span></span>  
  
 <span data-ttu-id="b0d65-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b0d65-114">S_FALSE</span></span>  
 <span data-ttu-id="b0d65-115">`dwInternalProcessID` entspricht keinem auf dem Computer ausgeführten Prozess; wahrscheinlich wurde der Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="b0d65-115">`dwInternalProcessID` does not match any process that is running on the computer, probably because the process was terminated.</span></span> <span data-ttu-id="b0d65-116">`pcRuntimes` und `ppRuntimes` sind null.</span><span class="sxs-lookup"><span data-stu-id="b0d65-116">`pcRuntimes` and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="b0d65-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b0d65-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="b0d65-118">Für `ppRuntimes` kann nicht genug Arbeitsspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b0d65-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="b0d65-119">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="b0d65-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="b0d65-120">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="b0d65-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0d65-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0d65-121">Remarks</span></span>  
 <span data-ttu-id="b0d65-122">Um den von dieser Methode belegten Arbeitsspeicher freizugeben, müssen Sie die [icoreclrdebugtarget:: FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b0d65-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0d65-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b0d65-123">Requirements</span></span>  
 <span data-ttu-id="b0d65-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0d65-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0d65-125">**Header:** Coreclrremotedebugginginterfaces. h</span><span class="sxs-lookup"><span data-stu-id="b0d65-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="b0d65-126">**Bibliothek:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="b0d65-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="b0d65-127">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="b0d65-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0d65-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0d65-128">See also</span></span>

- [<span data-ttu-id="b0d65-129">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b0d65-129">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
