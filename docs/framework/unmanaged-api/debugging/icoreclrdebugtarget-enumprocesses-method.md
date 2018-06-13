---
title: ICoreClrDebugTarget::EnumProcesses-Methode
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c09b70b5afb0561d32e55dd89df6cac083abc068
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422015"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="d2c0e-102">ICoreClrDebugTarget::EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="d2c0e-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="d2c0e-103">Listet die Prozesse auf, die auf einem Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d2c0e-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c0e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2c0e-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2c0e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2c0e-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="d2c0e-106">[out] Die Anzahl der in `ppProcs` zurückgegebenen Prozesse.</span><span class="sxs-lookup"><span data-stu-id="d2c0e-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="d2c0e-107">Dieser Wert kann 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="d2c0e-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="d2c0e-108">[out] Ein Array von [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) Strukturen, die auf dem Remotecomputer ausgeführten Prozesse darstellen.</span><span class="sxs-lookup"><span data-stu-id="d2c0e-108">[out] An array of [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2c0e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d2c0e-109">Return Value</span></span>  
 <span data-ttu-id="d2c0e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2c0e-110">S_OK</span></span>  
 <span data-ttu-id="d2c0e-111">Erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d2c0e-111">Success.</span></span>  
  
 <span data-ttu-id="d2c0e-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d2c0e-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="d2c0e-113">Für `ppProcs` kann nicht genug Arbeitsspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d2c0e-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="d2c0e-114">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="d2c0e-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="d2c0e-115">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="d2c0e-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2c0e-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2c0e-116">Remarks</span></span>  
 <span data-ttu-id="d2c0e-117">Um den Arbeitsspeicher freizugeben, der von dieser Methode belegt wurde, rufen Sie die [ICoreClrDebugTarget:: FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="d2c0e-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2c0e-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2c0e-118">Requirements</span></span>  
 <span data-ttu-id="d2c0e-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2c0e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2c0e-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="d2c0e-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="d2c0e-121">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="d2c0e-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="d2c0e-122">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d2c0e-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c0e-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2c0e-123">See Also</span></span>  
 [<span data-ttu-id="d2c0e-124">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2c0e-124">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
