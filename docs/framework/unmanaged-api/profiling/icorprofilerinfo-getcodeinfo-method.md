---
title: ICorProfilerInfo::GetCodeInfo-Methode
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
- ICorProfilerInfo.GetCodeInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCodeInfo
helpviewer_keywords:
- GetCodeInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetCodeInfo method [.NET Framework profiling]
ms.assetid: 90140b0f-a926-4a7e-b6fa-23e05f703cce
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cd05f1ed64e32c4b451f3e60d856be0e99e302b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetcodeinfo-method"></a><span data-ttu-id="47691-102">ICorProfilerInfo::GetCodeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="47691-102">ICorProfilerInfo::GetCodeInfo Method</span></span>
<span data-ttu-id="47691-103">Ruft den Wertebereich des nativen Codes ab, der der angegebenen Funktions-ID zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="47691-103">Gets the extent of native code associated with the specified function ID.</span></span>  
  
 <span data-ttu-id="47691-104">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="47691-104">This method is obsolete.</span></span> <span data-ttu-id="47691-105">Verwenden der [ICorProfilerInfo2:: Getcodeinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="47691-105">Use the [ICorProfilerInfo2::GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47691-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="47691-106">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47691-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="47691-107">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="47691-108">[in] Die ID der Funktion, der der native Code zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="47691-108">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `pStart`  
 <span data-ttu-id="47691-109">[out] Ein Zeiger auf ein Array von Bytes, aus denen sich der native Code der Funktion zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="47691-109">[out] A pointer to an array of bytes that compose the native code of the function.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="47691-110">[out] Ein Zeiger auf eine ganze Zahl, die die Größe des nativen Codes in Bytes angibt.</span><span class="sxs-lookup"><span data-stu-id="47691-110">[out] A pointer to an integer that specifies the size, in bytes, of the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47691-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="47691-111">Remarks</span></span>  
 <span data-ttu-id="47691-112">Zur Leistungsoptimierung teilt die Laufzeit in .NET Framework, Version 2.0, den vorkompilierten nativen Code einer Funktion in mehrere Bereiche auf.</span><span class="sxs-lookup"><span data-stu-id="47691-112">To optimize performance, the runtime in the .NET Framework version 2.0 splits the precompiled, native code of a function into multiple regions.</span></span> <span data-ttu-id="47691-113">Daher ist die `GetCodeInfo`-Methode in .NET Framework 2.0 veraltet, weil sie den Wertebereich des systemeigenen Codes einer Funktion nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="47691-113">Consequently, the `GetCodeInfo` method is obsolete in the .NET Framework 2.0 because it is unable to handle the extent of a function's native code.</span></span> <span data-ttu-id="47691-114">Profiler sollten stattdessen die allgemeinere `ICorProfilerInfo2::GetCodeInfo2`-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="47691-114">Profilers should switch to using the more general `ICorProfilerInfo2::GetCodeInfo2` method instead.</span></span>  
  
 <span data-ttu-id="47691-115">Diese Funktion verwendet vom Aufrufer reservierte Puffer.</span><span class="sxs-lookup"><span data-stu-id="47691-115">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47691-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47691-116">Requirements</span></span>  
 <span data-ttu-id="47691-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47691-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47691-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="47691-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="47691-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47691-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47691-120">**.NET Framework-Versionen:** 1.0</span><span class="sxs-lookup"><span data-stu-id="47691-120">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47691-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47691-121">See Also</span></span>  
 [<span data-ttu-id="47691-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47691-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="47691-123">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="47691-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="47691-124">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="47691-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
