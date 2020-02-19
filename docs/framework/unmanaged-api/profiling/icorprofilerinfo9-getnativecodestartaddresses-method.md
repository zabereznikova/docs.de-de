---
title: 'ICorProfilerInfo9:: getnativecodestartadressen'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 99706fdc3d60a5e1a7f85400c1184d5acc808e42
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449728"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="d510e-102">ICorProfilerInfo9:: getnativecodestartadressen-Methode</span><span class="sxs-lookup"><span data-stu-id="d510e-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="d510e-103">Listet bei Angabe von FunctionID und rejitid die Startadresse des systemeigenen Codes aller JIT-Versionen dieses Codes auf, die derzeit vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d510e-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="d510e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d510e-104">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a><span data-ttu-id="d510e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d510e-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="d510e-106">\[in] die ID der Funktion, deren Start Adressen für den nativen Code zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d510e-106">\[in] The ID of the function whose native code start addresses should be returned.</span></span>

- `reJitId`

  <span data-ttu-id="d510e-107">\[in] die Identität der JIT-neu kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="d510e-107">\[in] The identity of the JIT-recompiled function.</span></span>

- `cCodeStartAddresses`

  <span data-ttu-id="d510e-108">\[in] die maximale Größe des `codeStartAddresses` Arrays.</span><span class="sxs-lookup"><span data-stu-id="d510e-108">\[in] The maximum size of the `codeStartAddresses` array.</span></span>

- `pcCodeStartAddresses`

  <span data-ttu-id="d510e-109">\[out] die Anzahl der verfügbaren Adressen.</span><span class="sxs-lookup"><span data-stu-id="d510e-109">\[out] The number of available addresses.</span></span>

- `codeStartAddresses`

  <span data-ttu-id="d510e-110">\[out] ein Array von `UINT_PTR`, von denen jedes die Startadresse für einen systemeigenen Text für die angegebene Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="d510e-110">\[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="d510e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d510e-111">Remarks</span></span>

<span data-ttu-id="d510e-112">Wenn die mehrstufige Kompilierung aktiviert ist, kann eine Funktion mehr als einen nativen Code Körper aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d510e-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="d510e-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d510e-113">Requirements</span></span>

<span data-ttu-id="d510e-114">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="d510e-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="d510e-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d510e-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="d510e-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d510e-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d510e-117">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d510e-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d510e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d510e-118">See also</span></span>

- [<span data-ttu-id="d510e-119">ICorProfilerInfo9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d510e-119">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
