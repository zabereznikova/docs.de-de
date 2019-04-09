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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f4fb2292154a2660a2db3f0b3962fcf2114e385
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099975"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="a3827-102">ICorProfilerInfo::GetFunctionFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="a3827-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="a3827-103">Ruft die ID einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="a3827-103">Gets the ID of a function.</span></span> <span data-ttu-id="a3827-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="a3827-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a3827-105">Verwenden der [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="a3827-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3827-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3827-106">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a3827-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3827-107">Remarks</span></span>  
 <span data-ttu-id="a3827-108">Die `GetFunctionFromToken` -Methode funktioniert nicht für generische Funktionen oder Funktionen in generischen Typen; ist jetzt veraltet.</span><span class="sxs-lookup"><span data-stu-id="a3827-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="a3827-109">Verwendung `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` für alle Funktionen.</span><span class="sxs-lookup"><span data-stu-id="a3827-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3827-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3827-110">Requirements</span></span>  
 <span data-ttu-id="a3827-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3827-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3827-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3827-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3827-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3827-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3827-114">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="a3827-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3827-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3827-115">See also</span></span>

- [<span data-ttu-id="a3827-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3827-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
