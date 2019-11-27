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
ms.openlocfilehash: 6999821412b3cdd614cb30858a0616c9f27a6baa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448110"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="10156-102">ICorProfilerInfo::GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="10156-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="10156-103">Ruft die ID der Klasse ab, wenn das Metadatentoken angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="10156-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="10156-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="10156-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="10156-105">Verwenden Sie stattdessen [ICorProfilerInfo2:: getclassfromtkenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="10156-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10156-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="10156-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10156-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="10156-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="10156-108">in Die ID des Moduls, das die Klasse enthält.</span><span class="sxs-lookup"><span data-stu-id="10156-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="10156-109">in Ein `mdTypeDef` Metadatentoken, das auf die-Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="10156-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="10156-110">vorgenommen Ein Zeiger auf die Klassen-ID.</span><span class="sxs-lookup"><span data-stu-id="10156-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10156-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10156-111">Remarks</span></span>  
 <span data-ttu-id="10156-112">Diese Methode ist veraltet. Verwenden Sie stattdessen `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` für alle Typen.</span><span class="sxs-lookup"><span data-stu-id="10156-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10156-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="10156-113">Requirements</span></span>  
 <span data-ttu-id="10156-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10156-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10156-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="10156-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="10156-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10156-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10156-117">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="10156-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10156-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10156-118">See also</span></span>

- [<span data-ttu-id="10156-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10156-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
