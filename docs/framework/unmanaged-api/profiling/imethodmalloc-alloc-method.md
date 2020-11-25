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
ms.openlocfilehash: 58809f12e4dd4419b754caafc3f8b883b8bc5089
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721165"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="43829-102">IMethodMalloc::Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="43829-102">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="43829-103">Versucht, eine angegebene Arbeitsspeicher Menge für einen neuen MSIL-Funktions Text (Microsoft Intermediate Language) zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="43829-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="43829-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43829-104">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="43829-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="43829-105">Parameters</span></span>

`cb`\
<span data-ttu-id="43829-106">in Die Anzahl der Bytes, die für den Methoden Text zuzuordnen sind.</span><span class="sxs-lookup"><span data-stu-id="43829-106">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="43829-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43829-107">Remarks</span></span>

 <span data-ttu-id="43829-108">Der zugewiesene Arbeitsspeicher beginnt bei einer Adresse, die größer ist als die Basisadresse des Moduls, das mit dieser Zuweisung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="43829-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="43829-109">Anders ausgedrückt, wird jede Zuweisung für ein bestimmtes Modul erstellt, und es wird versucht, Arbeitsspeicher in einem positiven Offset von der Basisadresse zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="43829-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="43829-110">Wenn `Alloc` die angeforderte Anzahl von Bytes bei einer Adresse, die größer als die Basisadresse des Moduls ist, nicht zuordnen kann, wird unabhängig von der tatsächlichen Menge an verfügbarem Speicherplatz E_OUTOFMEMORY zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="43829-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="43829-111">Die- `Alloc` Methode sollte in Verbindung mit der [ICorProfilerInfo:: abtilfunctionbody](icorprofilerinfo-setilfunctionbody-method.md) -Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43829-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="43829-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="43829-112">Requirements</span></span>

 <span data-ttu-id="43829-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43829-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="43829-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43829-114">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="43829-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43829-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="43829-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43829-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="43829-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43829-117">See also</span></span>

- [<span data-ttu-id="43829-118">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43829-118">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)
