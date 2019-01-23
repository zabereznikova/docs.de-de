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
ms.openlocfilehash: 54c38f9a9abc9a02ba4d84c9a41b2ef6b1f7cb69
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528562"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="23287-102">IMethodMalloc::Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="23287-102">IMethodMalloc::Alloc Method</span></span>
<span data-ttu-id="23287-103">Versucht, eine angegebene Menge an Arbeitsspeicher für einen neuen Microsoft intermediate Language (MSIL)-Funktionsrumpf zu reservieren.</span><span class="sxs-lookup"><span data-stu-id="23287-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23287-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23287-104">Syntax</span></span>  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23287-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23287-105">Parameters</span></span>  
 `cb`  
 <span data-ttu-id="23287-106">[in] Die Anzahl der Bytes, die für den Methodentext zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="23287-106">[in] The number of bytes to allocate for the method body.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23287-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23287-107">Remarks</span></span>  
 <span data-ttu-id="23287-108">Der zugeordnete Arbeitsspeicher beginnt an einer Adresse, die größer als die Basisadresse des Moduls, das mit dieser Zuordnung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="23287-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="23287-109">Das heißt, jede Zuweisung für ein bestimmtes Modul erstellt wird, und versucht, aus der Basisadresse mit einem positiven Offset speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="23287-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="23287-110">Wenn `Alloc` nicht die angeforderte Anzahl von Bytes an einer Adresse, die größer als die Basisadresse des Moduls kann unabhängig von der tatsächlichen Menge des freien Speichers E_OUTOFMEMORY zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23287-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>  
  
 <span data-ttu-id="23287-111">Die `Alloc` Methode sollte verwendet werden, in Verbindung mit der [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="23287-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23287-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23287-112">Requirements</span></span>  
 <span data-ttu-id="23287-113">**Plattformen:** WindSee [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23287-113">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23287-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="23287-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="23287-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23287-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23287-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23287-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23287-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23287-117">See also</span></span>
- [<span data-ttu-id="23287-118">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23287-118">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
