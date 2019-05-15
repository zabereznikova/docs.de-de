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
ms.openlocfilehash: 66bd56a332dc34fd35f3129256cc0e3d6c5d4508
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636703"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="7c0f5-102">IMethodMalloc::Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="7c0f5-102">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="7c0f5-103">Versucht, eine angegebene Menge an Arbeitsspeicher für einen neuen Microsoft intermediate Language (MSIL)-Funktionsrumpf zu reservieren.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c0f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c0f5-104">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="7c0f5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c0f5-105">Parameters</span></span>

`cb`\
<span data-ttu-id="7c0f5-106">[in] Die Anzahl der Bytes, die für den Methodentext zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-106">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c0f5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c0f5-107">Remarks</span></span>

 <span data-ttu-id="7c0f5-108">Der zugeordnete Arbeitsspeicher beginnt an einer Adresse, die größer als die Basisadresse des Moduls, das mit dieser Zuordnung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="7c0f5-109">Das heißt, jede Zuweisung für ein bestimmtes Modul erstellt wird, und versucht, aus der Basisadresse mit einem positiven Offset speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="7c0f5-110">Wenn `Alloc` nicht die angeforderte Anzahl von Bytes an einer Adresse, die größer als die Basisadresse des Moduls kann unabhängig von der tatsächlichen Menge des freien Speichers E_OUTOFMEMORY zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="7c0f5-111">Die `Alloc` Methode sollte verwendet werden, in Verbindung mit der [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="7c0f5-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7c0f5-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c0f5-112">Requirements</span></span>
 <span data-ttu-id="7c0f5-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c0f5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="7c0f5-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c0f5-114">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="7c0f5-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c0f5-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="7c0f5-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c0f5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7c0f5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c0f5-117">See also</span></span>

- [<span data-ttu-id="7c0f5-118">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c0f5-118">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)
