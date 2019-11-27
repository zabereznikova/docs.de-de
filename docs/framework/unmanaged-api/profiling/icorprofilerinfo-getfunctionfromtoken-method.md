---
title: ICorProfilerInfo::GetFunctionFromToken-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
ms.openlocfilehash: 72531dc4fa7a8afc3bd719d73389fac94e3363bb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439144"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="eba73-102">ICorProfilerInfo::GetFunctionFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="eba73-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="eba73-103">Ruft die ID einer Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="eba73-103">Gets the ID of a function.</span></span> <span data-ttu-id="eba73-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="eba73-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="eba73-105">Verwenden Sie stattdessen die [ICorProfilerInfo2:: getfunctionfromdekenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="eba73-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eba73-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="eba73-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="eba73-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eba73-107">Remarks</span></span>  
 <span data-ttu-id="eba73-108">Die `GetFunctionFromToken`-Methode funktioniert nicht für generische Funktionen oder Funktionen in generischen Typen. Es ist mittlerweile veraltet.</span><span class="sxs-lookup"><span data-stu-id="eba73-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="eba73-109">Verwenden Sie `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` für alle Funktionen.</span><span class="sxs-lookup"><span data-stu-id="eba73-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eba73-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="eba73-110">Requirements</span></span>  
 <span data-ttu-id="eba73-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eba73-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eba73-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eba73-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eba73-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eba73-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eba73-114">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="eba73-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba73-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eba73-115">See also</span></span>

- [<span data-ttu-id="eba73-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eba73-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
