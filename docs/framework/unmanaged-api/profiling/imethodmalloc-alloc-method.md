---
title: IMethodMalloc::Alloc-Methode
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d73fe16720248d541bac64a432bb6f35d6873b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454980"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="40907-102">IMethodMalloc::Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="40907-102">IMethodMalloc::Alloc Method</span></span>
<span data-ttu-id="40907-103">Versucht, eine bestimmte Arbeitsspeichermenge für einen neuen Microsoft intermediate Language (MSIL)-Funktionsrumpf belegt werden.</span><span class="sxs-lookup"><span data-stu-id="40907-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40907-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40907-104">Syntax</span></span>  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40907-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="40907-105">Parameters</span></span>  
 `cb`  
 <span data-ttu-id="40907-106">[in] Die Anzahl der Bytes, die für den Methodentext zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="40907-106">[in] The number of bytes to allocate for the method body.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40907-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40907-107">Remarks</span></span>  
 <span data-ttu-id="40907-108">Der belegte Arbeitsspeicher beginnt an einer Adresse, die größer als die Basisadresse des Moduls, das diese Zuweisung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="40907-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="40907-109">In anderen Worten, jede Zuweisung wird für ein bestimmtes Modul erstellt und versucht, mit einem positiven Offset von seiner Basisadresse belegt werden.</span><span class="sxs-lookup"><span data-stu-id="40907-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="40907-110">Wenn `Alloc` nicht belegen kann die angeforderte Anzahl von Bytes an einer Adresse, die größer als die Basisadresse des Moduls, unabhängig von der tatsächlichen Menge des freien Speichers E_OUTOFMEMORY zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="40907-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>  
  
 <span data-ttu-id="40907-111">Die `Alloc` -Methode sollte verwendet werden, zusammen mit den [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="40907-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40907-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40907-112">Requirements</span></span>  
 <span data-ttu-id="40907-113">**Plattformen:** WindSee [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40907-113">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40907-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40907-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40907-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40907-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40907-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40907-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40907-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40907-117">See Also</span></span>  
 [<span data-ttu-id="40907-118">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40907-118">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
