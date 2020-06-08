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
ms.openlocfilehash: 12b4b897f9dc51175037d39c0368b6ce59fefefb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498478"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="645ed-102">ICorProfilerInfo::GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="645ed-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="645ed-103">Ruft die ID der Klasse ab, wenn das Metadatentoken angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="645ed-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="645ed-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="645ed-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="645ed-105">Verwenden Sie stattdessen [ICorProfilerInfo2:: getclassfromtkenandtypeargs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="645ed-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="645ed-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="645ed-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="645ed-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="645ed-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="645ed-108">in Die ID des Moduls, das die Klasse enthält.</span><span class="sxs-lookup"><span data-stu-id="645ed-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="645ed-109">in Ein `mdTypeDef` Metadatentoken, das auf die-Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="645ed-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="645ed-110">vorgenommen Ein Zeiger auf die Klassen-ID.</span><span class="sxs-lookup"><span data-stu-id="645ed-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="645ed-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="645ed-111">Remarks</span></span>  
 <span data-ttu-id="645ed-112">Diese Methode ist veraltet. Verwenden Sie stattdessen `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` für alle Typen.</span><span class="sxs-lookup"><span data-stu-id="645ed-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="645ed-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="645ed-113">Requirements</span></span>  
 <span data-ttu-id="645ed-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="645ed-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="645ed-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="645ed-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="645ed-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="645ed-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="645ed-117">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="645ed-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="645ed-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="645ed-118">See also</span></span>

- [<span data-ttu-id="645ed-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="645ed-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
