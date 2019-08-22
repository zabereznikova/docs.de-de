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
ms.openlocfilehash: 80571933bc8d91c074dbee62aad50cece6277d51
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665504"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="b68d7-102">ICorProfilerInfo9:: getnativecodestartadressen-Methode</span><span class="sxs-lookup"><span data-stu-id="b68d7-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="b68d7-103">Listet bei Angabe von FunctionID und rejitid die Startadresse des systemeigenen Codes aller JIT-Versionen dieses Codes auf, die derzeit vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b68d7-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="b68d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b68d7-104">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

#### <a name="parameters"></a><span data-ttu-id="b68d7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b68d7-105">Parameters</span></span>

`functionId` \
<span data-ttu-id="b68d7-106">in Die ID der Funktion, deren Start Adressen für den ursprünglichen Code zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b68d7-106">[in] The ID of the function whose native code start addresses should be returned.</span></span>

`reJitId` \
<span data-ttu-id="b68d7-107">[in] Die Identität der erneut JIT-kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="b68d7-107">[in] The identity of the JIT-recompiled function.</span></span>

`cCodeStartAddresses` \
<span data-ttu-id="b68d7-108">[in] Die maximale Größe des `codeStartAddresses`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="b68d7-108">[in] The maximum size of the `codeStartAddresses` array.</span></span>

`pcCodeStartAddresses` \
<span data-ttu-id="b68d7-109">vorgenommen Die Anzahl der verfügbaren Adressen.</span><span class="sxs-lookup"><span data-stu-id="b68d7-109">[out] The number of available addresses.</span></span>

`codeStartAddresses` \
<span data-ttu-id="b68d7-110">vorgenommen Ein-Array `UINT_PTR`, von dem jeder die Startadresse für einen systemeigenen Text für die angegebene Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="b68d7-110">[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="b68d7-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b68d7-111">Remarks</span></span>

<span data-ttu-id="b68d7-112">Wenn die mehrstufige Kompilierung aktiviert ist, kann eine Funktion mehr als einen nativen Code Körper aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b68d7-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="b68d7-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b68d7-113">Requirements</span></span>

<span data-ttu-id="b68d7-114">**Formen** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="b68d7-114">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="b68d7-115">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="b68d7-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="b68d7-116">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b68d7-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b68d7-117">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b68d7-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b68d7-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b68d7-118">See also</span></span>

- [<span data-ttu-id="b68d7-119">ICorProfilerInfo9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b68d7-119">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)
