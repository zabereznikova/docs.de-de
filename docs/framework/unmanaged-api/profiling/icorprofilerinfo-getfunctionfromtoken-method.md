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
ms.openlocfilehash: 2b2d619c5940376806e9873a528b4f08886593e9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863555"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="20b9a-102">ICorProfilerInfo::GetFunctionFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="20b9a-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="20b9a-103">Ruft die ID einer Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="20b9a-103">Gets the ID of a function.</span></span> <span data-ttu-id="20b9a-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="20b9a-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="20b9a-105">Verwenden Sie stattdessen die [ICorProfilerInfo2:: getfunctionfromdekenandtypeargs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="20b9a-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20b9a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="20b9a-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="20b9a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20b9a-107">Remarks</span></span>  
 <span data-ttu-id="20b9a-108">Die `GetFunctionFromToken`-Methode funktioniert nicht für generische Funktionen oder Funktionen in generischen Typen. Es ist mittlerweile veraltet.</span><span class="sxs-lookup"><span data-stu-id="20b9a-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="20b9a-109">Verwenden Sie `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` für alle Funktionen.</span><span class="sxs-lookup"><span data-stu-id="20b9a-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20b9a-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20b9a-110">Requirements</span></span>  
 <span data-ttu-id="20b9a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20b9a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20b9a-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20b9a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20b9a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20b9a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20b9a-114">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="20b9a-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b9a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20b9a-115">See also</span></span>

- [<span data-ttu-id="20b9a-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20b9a-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
