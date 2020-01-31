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
ms.openlocfilehash: 8412020fb98fde245b873a2f0c6a355f6436f712
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868277"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="a1825-102">ICorProfilerInfo9:: getnativecodestartadressen-Methode</span><span class="sxs-lookup"><span data-stu-id="a1825-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="a1825-103">Listet bei Angabe von FunctionID und rejitid die Startadresse des systemeigenen Codes aller JIT-Versionen dieses Codes auf, die derzeit vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a1825-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1825-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1825-104">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a><span data-ttu-id="a1825-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="a1825-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="a1825-106">\[in] die ID der Funktion, deren Start Adressen für den nativen Code zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a1825-106">\[in] The ID of the function whose native code start addresses should be returned.</span></span>

- `reJitId`

  <span data-ttu-id="a1825-107">\[in] die Identität der JIT-neu kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="a1825-107">\[in] The identity of the JIT-recompiled function.</span></span>

- `cCodeStartAddresses`

  <span data-ttu-id="a1825-108">\[in] die maximale Größe des `codeStartAddresses` Arrays.</span><span class="sxs-lookup"><span data-stu-id="a1825-108">\[in] The maximum size of the `codeStartAddresses` array.</span></span>

- `pcCodeStartAddresses`

  <span data-ttu-id="a1825-109">\[out] die Anzahl der verfügbaren Adressen.</span><span class="sxs-lookup"><span data-stu-id="a1825-109">\[out] The number of available addresses.</span></span>

- `codeStartAddresses`

  <span data-ttu-id="a1825-110">\[out] ein Array von `UINT_PTR`, von denen jedes die Startadresse für einen systemeigenen Text für die angegebene Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="a1825-110">\[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1825-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1825-111">Remarks</span></span>

<span data-ttu-id="a1825-112">Wenn die mehrstufige Kompilierung aktiviert ist, kann eine Funktion mehr als einen nativen Code Körper aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a1825-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="a1825-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1825-113">Requirements</span></span>

<span data-ttu-id="a1825-114">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="a1825-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="a1825-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1825-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="a1825-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1825-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a1825-117">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1825-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a1825-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1825-118">See also</span></span>

- [<span data-ttu-id="a1825-119">ICorProfilerInfo9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1825-119">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
