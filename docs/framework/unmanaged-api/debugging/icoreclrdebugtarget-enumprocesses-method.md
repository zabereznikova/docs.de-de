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
ms.openlocfilehash: 11b1072b3467f7d0a3f223fbc2151ec9ccf461ad
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790800"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="60345-102">ICoreClrDebugTarget::EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="60345-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="60345-103">Listet die Prozesse auf, die auf einem Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="60345-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60345-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60345-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60345-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="60345-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="60345-106">[out] Die Anzahl der in `ppProcs` zurückgegebenen Prozesse.</span><span class="sxs-lookup"><span data-stu-id="60345-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="60345-107">Dieser Wert kann 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="60345-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="60345-108">vorgenommen Ein Array von [coreclrdebugprocinfo](coreclrdebugprocinfo-structure.md) -Strukturen, die die Prozesse darstellen, die auf dem Remote Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="60345-108">[out] An array of [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60345-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="60345-109">Return Value</span></span>  
 <span data-ttu-id="60345-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="60345-110">S_OK</span></span>  
 <span data-ttu-id="60345-111">Erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="60345-111">Success.</span></span>  
  
 <span data-ttu-id="60345-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="60345-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="60345-113">Für `ppProcs` kann nicht genug Arbeitsspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="60345-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="60345-114">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="60345-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="60345-115">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="60345-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60345-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60345-116">Remarks</span></span>  
 <span data-ttu-id="60345-117">Um den von dieser Methode belegten Arbeitsspeicher freizugeben, müssen Sie die [icoreclrdebugtarget:: FreeMemory](icoreclrdebugtarget-freememory-method.md) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="60345-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60345-118">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60345-118">Requirements</span></span>  
 <span data-ttu-id="60345-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60345-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60345-120">**Header:** Coreclrremotedebugginginterfaces. h</span><span class="sxs-lookup"><span data-stu-id="60345-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="60345-121">**Bibliothek:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="60345-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="60345-122">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="60345-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60345-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60345-123">See also</span></span>

- [<span data-ttu-id="60345-124">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60345-124">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
