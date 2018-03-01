---
title: ICorProfilerInfo::GetClassFromToken-Methode
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9972a9d97f94a6286adc0906416349f92e6bf7ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="6dabb-102">ICorProfilerInfo::GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="6dabb-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="6dabb-103">Ruft die ID der Klasse, mit dem angegebenen Metadatentoken ab.</span><span class="sxs-lookup"><span data-stu-id="6dabb-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="6dabb-104">Diese Methode ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="6dabb-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="6dabb-105">Verwendung [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="6dabb-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dabb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6dabb-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6dabb-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="6dabb-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="6dabb-108">[in] Die ID des Moduls, das die Klasse enthält.</span><span class="sxs-lookup"><span data-stu-id="6dabb-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="6dabb-109">[in] Ein `mdTypeDef` Metadatentoken, das die Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="6dabb-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="6dabb-110">[out] Ein Zeiger auf die Klassen-ID.</span><span class="sxs-lookup"><span data-stu-id="6dabb-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dabb-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6dabb-111">Remarks</span></span>  
 <span data-ttu-id="6dabb-112">Diese Methode ist veraltet. Verwenden Sie stattdessen `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` für alle Typen.</span><span class="sxs-lookup"><span data-stu-id="6dabb-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dabb-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6dabb-113">Requirements</span></span>  
 <span data-ttu-id="6dabb-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dabb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dabb-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6dabb-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6dabb-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6dabb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6dabb-117">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6dabb-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dabb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6dabb-118">See Also</span></span>  
 [<span data-ttu-id="6dabb-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6dabb-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
