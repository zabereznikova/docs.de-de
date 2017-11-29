---
title: ICorProfilerInfo::GetClassFromToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetClassFromToken
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 761c537f0b3aba529a8a3a862a1a975ddd1c6303
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="fa791-102">ICorProfilerInfo::GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="fa791-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="fa791-103">Ruft die ID der Klasse, mit dem angegebenen Metadatentoken ab.</span><span class="sxs-lookup"><span data-stu-id="fa791-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="fa791-104">Diese Methode ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="fa791-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="fa791-105">Verwendung [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="fa791-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa791-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa791-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa791-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa791-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="fa791-108">[in] Die ID des Moduls, das die Klasse enthält.</span><span class="sxs-lookup"><span data-stu-id="fa791-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="fa791-109">[in] Ein `mdTypeDef` Metadatentoken, das die Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="fa791-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="fa791-110">[out] Ein Zeiger auf die Klassen-ID.</span><span class="sxs-lookup"><span data-stu-id="fa791-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa791-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa791-111">Remarks</span></span>  
 <span data-ttu-id="fa791-112">Diese Methode ist veraltet. Verwenden Sie stattdessen `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` für alle Typen.</span><span class="sxs-lookup"><span data-stu-id="fa791-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa791-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa791-113">Requirements</span></span>  
 <span data-ttu-id="fa791-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa791-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa791-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa791-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa791-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa791-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa791-117">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="fa791-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa791-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa791-118">See Also</span></span>  
 [<span data-ttu-id="fa791-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa791-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
