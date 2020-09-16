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
ms.openlocfilehash: ecaff179378eb417393c0a0d17d0a00d3b99e5a4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541297"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="451a5-102">ICorProfilerInfo9:: GetCodeInfo4-Methode</span><span class="sxs-lookup"><span data-stu-id="451a5-102">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>

<span data-ttu-id="451a5-103">Gibt bei der Startadresse des systemeigenen Codes die Blöcke des virtuellen Speichers zurück, in denen dieser Code gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="451a5-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>

## <a name="syntax"></a><span data-ttu-id="451a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="451a5-104">Syntax</span></span>

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

## <a name="parameters"></a><span data-ttu-id="451a5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="451a5-105">Parameters</span></span>

- `pNativeCodeStartAddress`

  <span data-ttu-id="451a5-106">\[in] ein Zeiger auf den Anfang einer nativen Funktion.</span><span class="sxs-lookup"><span data-stu-id="451a5-106">\[in] A pointer to the start of a native function.</span></span>

- `cCodeInfos`

  <span data-ttu-id="451a5-107">\[in] die Größe des `codeInfos` Arrays.</span><span class="sxs-lookup"><span data-stu-id="451a5-107">\[in] The size of the `codeInfos` array.</span></span>

- `pcCodeInfos`

  <span data-ttu-id="451a5-108">\[out] ein Zeiger auf die Gesamtzahl der verfügbaren [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="451a5-108">\[out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>

- `codeInfos`

  <span data-ttu-id="451a5-109">\[out] ein vom Aufrufer bereitgestellter Puffer.</span><span class="sxs-lookup"><span data-stu-id="451a5-109">\[out] A caller-provided buffer.</span></span> <span data-ttu-id="451a5-110">Nach dem Ausführen enthält die Methode ein Array aus `COR_PRF_CODE_INFO`-Strukturen, von denen jede einen Block des systemeigenen Codes beschreibt.</span><span class="sxs-lookup"><span data-stu-id="451a5-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>

## <a name="remarks"></a><span data-ttu-id="451a5-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="451a5-111">Remarks</span></span>

<span data-ttu-id="451a5-112">Die- `GetCodeInfo4` Methode ähnelt [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md), mit der Ausnahme, dass Sie Code Informationen für verschiedene Native Versionen einer Methode suchen kann.</span><span class="sxs-lookup"><span data-stu-id="451a5-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>

> [!NOTE]
> <span data-ttu-id="451a5-113">`GetCodeInfo4` kann eine Garbage Collection auslöst.</span><span class="sxs-lookup"><span data-stu-id="451a5-113">`GetCodeInfo4` can trigger a garbage collection.</span></span>

<span data-ttu-id="451a5-114">Die Wertebereiche sind in aufsteigender Reihenfolge des CIL-Offsets (Common Intermediate Language) sortiert.</span><span class="sxs-lookup"><span data-stu-id="451a5-114">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>

<span data-ttu-id="451a5-115">Nachdem `GetCodeInfo4` zurückgegeben wurde, müssen Sie überprüfen, ob der `codeInfos` Puffer groß genug war, um alle [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) Strukturen zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="451a5-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="451a5-116">Vergleichen Sie hierzu den Wert von `cCodeInfos` mit dem Wert des `cchName`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="451a5-116">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="451a5-117">Wenn `cCodeInfos` dividiert durch die Größe einer [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) -Struktur kleiner als ist, weisen Sie `pcCodeInfos` einen größeren- `codeInfos` Puffer zu, aktualisieren Sie `cCodeInfos` mit der neuen Größe, und wiederholen Sie den Vorgang `GetCodeInfo4` .</span><span class="sxs-lookup"><span data-stu-id="451a5-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>

<span data-ttu-id="451a5-118">Alternativ können Sie zuerst `GetCodeInfo4` mit einem `codeInfos`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="451a5-118">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="451a5-119">Anschließend können Sie die `codeInfos` Puffergröße auf den in zurückgegebenen Wert `pcCodeInfos` , multipliziert mit der Größe einer [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) Struktur, und erneut aufzurufen `GetCodeInfo4` .</span><span class="sxs-lookup"><span data-stu-id="451a5-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>

## <a name="requirements"></a><span data-ttu-id="451a5-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="451a5-120">Requirements</span></span>

<span data-ttu-id="451a5-121">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="451a5-121">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="451a5-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="451a5-122">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="451a5-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="451a5-123">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="451a5-124">**.NET-Versionen:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="451a5-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="451a5-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="451a5-125">See also</span></span>

- [<span data-ttu-id="451a5-126">ICorProfilerInfo9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="451a5-126">ICorProfilerInfo9 Interface</span></span>](ICorProfilerInfo9-interface.md)
