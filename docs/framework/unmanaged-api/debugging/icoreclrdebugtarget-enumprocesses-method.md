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
ms.openlocfilehash: 6484832e8e737b9a0d0b3eaf3ede4078729f7a4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178443"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="deb39-102">ICoreClrDebugTarget::EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="deb39-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="deb39-103">Listet die Prozesse auf, die auf einem Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="deb39-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deb39-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="deb39-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="deb39-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="deb39-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="deb39-106">[out] Die Anzahl der in `ppProcs` zurückgegebenen Prozesse.</span><span class="sxs-lookup"><span data-stu-id="deb39-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="deb39-107">Dieser Wert kann 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="deb39-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="deb39-108">[out] Ein Array von [CoreClrDebugProcInfo-Strukturen,](coreclrdebugprocinfo-structure.md) die die auf dem Remotecomputer ausgeführten Prozesse darstellen.</span><span class="sxs-lookup"><span data-stu-id="deb39-108">[out] An array of [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="deb39-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="deb39-109">Return Value</span></span>  
 <span data-ttu-id="deb39-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="deb39-110">S_OK</span></span>  
 <span data-ttu-id="deb39-111">Erfolg.</span><span class="sxs-lookup"><span data-stu-id="deb39-111">Success.</span></span>  
  
 <span data-ttu-id="deb39-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="deb39-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="deb39-113">Für `ppProcs` kann nicht genug Arbeitsspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="deb39-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="deb39-114">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="deb39-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="deb39-115">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="deb39-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="deb39-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="deb39-116">Remarks</span></span>  
 <span data-ttu-id="deb39-117">Um den Speicher freizugeben, der von dieser Methode zugewiesen wurde, rufen Sie die [ICoreClrDebugTarget::FreeMemory-Methode](icoreclrdebugtarget-freememory-method.md) auf.</span><span class="sxs-lookup"><span data-stu-id="deb39-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deb39-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="deb39-118">Requirements</span></span>  
 <span data-ttu-id="deb39-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="deb39-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deb39-120">**Kopfzeile:** CoreClrRemoteDebuggingSchnittstellen.h</span><span class="sxs-lookup"><span data-stu-id="deb39-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="deb39-121">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="deb39-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="deb39-122">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="deb39-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb39-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="deb39-123">See also</span></span>

- [<span data-ttu-id="deb39-124">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="deb39-124">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
