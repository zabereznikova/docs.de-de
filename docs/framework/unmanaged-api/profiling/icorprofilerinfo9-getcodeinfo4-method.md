---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f65cebff912adeb7afc34434467cf7be72f9be32
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449763"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="af26d-102">ICorProfilerInfo9:: GetCodeInfo4-Methode</span><span class="sxs-lookup"><span data-stu-id="af26d-102">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>

<span data-ttu-id="af26d-103">Gibt bei der Startadresse des systemeigenen Codes die Blöcke des virtuellen Speichers zurück, in denen dieser Code gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="af26d-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>

## <a name="syntax"></a><span data-ttu-id="af26d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af26d-104">Syntax</span></span>

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

## <a name="parameters"></a><span data-ttu-id="af26d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="af26d-105">Parameters</span></span>

- `pNativeCodeStartAddress`

  <span data-ttu-id="af26d-106">\[in] ein Zeiger auf den Anfang einer nativen Funktion.</span><span class="sxs-lookup"><span data-stu-id="af26d-106">\[in] A pointer to the start of a native function.</span></span>

- `cCodeInfos`

  <span data-ttu-id="af26d-107">\[in] die Größe des `codeInfos` Arrays.</span><span class="sxs-lookup"><span data-stu-id="af26d-107">\[in] The size of the `codeInfos` array.</span></span>

- `pcCodeInfos`

  <span data-ttu-id="af26d-108">\[out] ein Zeiger auf die Gesamtzahl der verfügbaren [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="af26d-108">\[out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>

- `codeInfos`

  <span data-ttu-id="af26d-109">\[out] ein vom Aufrufer bereitgestellter Puffer.</span><span class="sxs-lookup"><span data-stu-id="af26d-109">\[out] A caller-provided buffer.</span></span> <span data-ttu-id="af26d-110">Nach dem Ausführen enthält die Methode ein Array aus `COR_PRF_CODE_INFO`-Strukturen, von denen jede einen Block des systemeigenen Codes beschreibt.</span><span class="sxs-lookup"><span data-stu-id="af26d-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>

## <a name="remarks"></a><span data-ttu-id="af26d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af26d-111">Remarks</span></span>

<span data-ttu-id="af26d-112">Die `GetCodeInfo4`-Methode ähnelt [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md), mit der Ausnahme, dass Sie Code Informationen für verschiedene Native Versionen einer Methode suchen kann.</span><span class="sxs-lookup"><span data-stu-id="af26d-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>

> [!NOTE]
> <span data-ttu-id="af26d-113">`GetCodeInfo4` können eine Garbage Collection auslöst.</span><span class="sxs-lookup"><span data-stu-id="af26d-113">`GetCodeInfo4` can trigger a garbage collection.</span></span>

<span data-ttu-id="af26d-114">Die Wertebereiche sind in aufsteigender Reihenfolge des CIL-Offsets (Common Intermediate Language) sortiert.</span><span class="sxs-lookup"><span data-stu-id="af26d-114">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>

<span data-ttu-id="af26d-115">Nachdem `GetCodeInfo4` zurückgegeben hat, müssen Sie überprüfen, ob der `codeInfos` Puffer groß genug war, um alle [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) Strukturen zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="af26d-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="af26d-116">Vergleichen Sie hierzu den Wert von `cCodeInfos` mit dem Wert des `cchName`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="af26d-116">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="af26d-117">Wenn `cCodeInfos` dividiert durch die Größe einer [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) Struktur kleiner als `pcCodeInfos`ist, weisen Sie einen größeren `codeInfos` Puffer zu, aktualisieren Sie `cCodeInfos` mit der neuen, größeren Größe, und wenden Sie `GetCodeInfo4` erneut an.</span><span class="sxs-lookup"><span data-stu-id="af26d-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>

<span data-ttu-id="af26d-118">Alternativ können Sie zuerst `GetCodeInfo4` mit einem `codeInfos`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="af26d-118">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="af26d-119">Sie können dann die `codeInfos` Puffergröße auf den Wert festlegen, der in `pcCodeInfos`zurückgegeben wurde, multipliziert mit der Größe einer [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) Struktur, und `GetCodeInfo4` erneut aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="af26d-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>

## <a name="requirements"></a><span data-ttu-id="af26d-120">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="af26d-120">Requirements</span></span>

<span data-ttu-id="af26d-121">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="af26d-121">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="af26d-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="af26d-122">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="af26d-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af26d-123">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="af26d-124">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af26d-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="af26d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af26d-125">See also</span></span>

- [<span data-ttu-id="af26d-126">ICorProfilerInfo9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af26d-126">ICorProfilerInfo9 Interface</span></span>](ICorProfilerInfo9-interface.md)
