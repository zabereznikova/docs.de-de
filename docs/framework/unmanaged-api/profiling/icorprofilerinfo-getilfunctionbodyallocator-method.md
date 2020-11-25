---
title: ICorProfilerInfo::GetILFunctionBodyAllocator-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
ms.openlocfilehash: b18de87cf89985e0f7ec11edf58b43d67720251c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718019"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="c103d-102">ICorProfilerInfo::GetILFunctionBodyAllocator-Methode</span><span class="sxs-lookup"><span data-stu-id="c103d-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>

<span data-ttu-id="c103d-103">Ruft eine-Schnittstelle ab, die eine Methode bereitstellt, um Speicher zuzuweisen, der zum Austauschen des Texts einer Methode im MSIL-Code (Microsoft Intermediate Language) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c103d-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c103d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c103d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c103d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c103d-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="c103d-106">in Die ID des Moduls, in dem sich die Methode befindet.</span><span class="sxs-lookup"><span data-stu-id="c103d-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="c103d-107">vorgenommen Ein Zeiger auf eine [IMethodMalloc](imethodmalloc-interface.md) -Schnittstelle, die eine Methode zum Zuordnen des Arbeitsspeichers bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c103d-107">[out] A pointer to an [IMethodMalloc](imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c103d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c103d-108">Remarks</span></span>  

 <span data-ttu-id="c103d-109">Ein Methoden Text im MSIL-Code muss sich in Relation zum geladenen Modul als relative virtuelle Adresse (RVA) befinden, was bedeutet, dass er auf das Modul innerhalb von 4 GB folgt.</span><span class="sxs-lookup"><span data-stu-id="c103d-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="c103d-110">Um einem Tool das Austauschen des Texts einer Methode zu erleichtern, stellt die- `GetILFunctionBodyAllocator` Methode sicher, dass der Arbeitsspeicher innerhalb dieses Bereichs zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="c103d-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c103d-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c103d-111">Requirements</span></span>  

 <span data-ttu-id="c103d-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c103d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c103d-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c103d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c103d-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c103d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c103d-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c103d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c103d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c103d-116">See also</span></span>

- [<span data-ttu-id="c103d-117">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c103d-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
