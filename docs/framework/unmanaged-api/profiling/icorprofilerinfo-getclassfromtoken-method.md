---
title: ICorProfilerInfo::GetClassFromToken-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 580c554c968819ba4ef2ba52edeb5e754d33ac1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185265"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="4d1f9-102">ICorProfilerInfo::GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="4d1f9-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="4d1f9-103">Ruft die ID der Klasse, mit dem angegebenen Metadatentoken ab.</span><span class="sxs-lookup"><span data-stu-id="4d1f9-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="4d1f9-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="4d1f9-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="4d1f9-105">Verwendung [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="4d1f9-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d1f9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d1f9-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d1f9-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="4d1f9-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="4d1f9-108">[in] Die ID des Moduls, das die Klasse enthält.</span><span class="sxs-lookup"><span data-stu-id="4d1f9-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="4d1f9-109">[in] Ein `mdTypeDef` Metadatentoken, das die Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="4d1f9-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="4d1f9-110">[out] Ein Zeiger auf die Klasse-ID</span><span class="sxs-lookup"><span data-stu-id="4d1f9-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d1f9-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4d1f9-111">Remarks</span></span>  
 <span data-ttu-id="4d1f9-112">Diese Methode ist veraltet. Verwenden Sie stattdessen `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` für alle Typen.</span><span class="sxs-lookup"><span data-stu-id="4d1f9-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d1f9-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4d1f9-113">Requirements</span></span>  
 <span data-ttu-id="4d1f9-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d1f9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d1f9-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4d1f9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4d1f9-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d1f9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d1f9-117">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="4d1f9-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d1f9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d1f9-118">See also</span></span>

- [<span data-ttu-id="4d1f9-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d1f9-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
