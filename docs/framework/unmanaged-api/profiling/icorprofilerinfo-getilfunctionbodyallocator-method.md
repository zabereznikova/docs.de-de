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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c5651da4c0065a4ac479fe31e54225ee5df51b32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780619"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="31d90-102">ICorProfilerInfo::GetILFunctionBodyAllocator-Methode</span><span class="sxs-lookup"><span data-stu-id="31d90-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="31d90-103">Ruft eine Schnittstelle, die eine Methode zum Belegen von Arbeitsspeicher bietet für die Auslagerung des Texts einer Methode in der Microsoft intermediate Language (MSIL)-Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="31d90-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31d90-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31d90-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31d90-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="31d90-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="31d90-106">[in] Die ID des Moduls, in dem die Methode befindet.</span><span class="sxs-lookup"><span data-stu-id="31d90-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="31d90-107">[out] Ein Zeiger auf ein [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) Schnittstelle, die eine Methode, um die speicherbelegung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="31d90-107">[out] A pointer to an [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31d90-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31d90-108">Remarks</span></span>  
 <span data-ttu-id="31d90-109">Methodenkörper in MSIL-Code muss als eine relative virtuelle Adresse (RVA), relativ zu das geladene Modul gefunden werden, was bedeutet, dass sie das Modul innerhalb von 4 GB folgt.</span><span class="sxs-lookup"><span data-stu-id="31d90-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="31d90-110">Um ein Tool zum Auslagern des Texts einer Methode, erleichtern die `GetILFunctionBodyAllocator` Methode stellt sicher, dass der Speicher wird in diesem Bereich zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="31d90-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31d90-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31d90-111">Requirements</span></span>  
 <span data-ttu-id="31d90-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31d90-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31d90-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="31d90-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="31d90-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31d90-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31d90-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31d90-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d90-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31d90-116">See also</span></span>

- [<span data-ttu-id="31d90-117">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31d90-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
