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
ms.openlocfilehash: 9a676989bdc6866f85fabe3e15b1e6b7b8b5a9a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000713"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="2d18c-102">IMethodMalloc::Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="2d18c-102">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="2d18c-103">Versucht, eine angegebene Menge an Arbeitsspeicher für einen neuen Microsoft intermediate Language (MSIL)-Funktionsrumpf zu reservieren.</span><span class="sxs-lookup"><span data-stu-id="2d18c-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="2d18c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d18c-104">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="2d18c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d18c-105">Parameters</span></span>

`cb`\
<span data-ttu-id="2d18c-106">[in] Die Anzahl der Bytes, die für den Methodentext zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2d18c-106">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d18c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d18c-107">Remarks</span></span>

 <span data-ttu-id="2d18c-108">Der zugeordnete Arbeitsspeicher beginnt an einer Adresse, die größer als die Basisadresse des Moduls, das mit dieser Zuordnung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="2d18c-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="2d18c-109">Das heißt, jede Zuweisung für ein bestimmtes Modul erstellt wird, und versucht, aus der Basisadresse mit einem positiven Offset speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="2d18c-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="2d18c-110">Wenn `Alloc` nicht die angeforderte Anzahl von Bytes an einer Adresse, die größer als die Basisadresse des Moduls kann unabhängig von der tatsächlichen Menge des freien Speichers E_OUTOFMEMORY zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d18c-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="2d18c-111">Die `Alloc` Methode sollte verwendet werden, in Verbindung mit der [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="2d18c-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2d18c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d18c-112">Requirements</span></span>
 <span data-ttu-id="2d18c-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d18c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="2d18c-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d18c-114">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="2d18c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d18c-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="2d18c-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d18c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2d18c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d18c-117">See also</span></span>

- [<span data-ttu-id="2d18c-118">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d18c-118">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)