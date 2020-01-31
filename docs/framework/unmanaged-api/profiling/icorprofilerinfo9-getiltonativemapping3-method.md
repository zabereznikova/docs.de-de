---
title: ICorProfilerInfo9::GetILToNativeMapping3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetILToNativeMapping3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 5c49d75432980d2f3af77ee040bc6eb20886b027
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861670"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="2b57a-102">ICorProfilerInfo9:: GetILToNativeMapping3-Methode</span><span class="sxs-lookup"><span data-stu-id="2b57a-102">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>

<span data-ttu-id="2b57a-103">Gibt bei der Startadresse des systemeigenen Codes die nativen to Il-Mapping-Informationen für diese JIT-Version des Codes zurück.</span><span class="sxs-lookup"><span data-stu-id="2b57a-103">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>

## <a name="syntax"></a><span data-ttu-id="2b57a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b57a-104">Syntax</span></span>

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

## <a name="parameters"></a><span data-ttu-id="2b57a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2b57a-105">Parameters</span></span>

- `pNativeCodeStartAddress`

  <span data-ttu-id="2b57a-106">\[in] ein Zeiger auf den Anfang einer nativen Funktion.</span><span class="sxs-lookup"><span data-stu-id="2b57a-106">\[in] A pointer to the start of a native function.</span></span>

- `cMap`

  <span data-ttu-id="2b57a-107">\[in] die maximale Größe des `map` Arrays.</span><span class="sxs-lookup"><span data-stu-id="2b57a-107">\[in] The maximum size of the `map` array.</span></span>

- `pcMap`

  <span data-ttu-id="2b57a-108">\[out] die Gesamtzahl der verfügbaren COR_DEBUG_IL_TO_NATIVE_MAP Strukturen.</span><span class="sxs-lookup"><span data-stu-id="2b57a-108">\[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

- `map`

  <span data-ttu-id="2b57a-109">\[out] ein Array von [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) Strukturen, von denen jede die Offsets angibt.</span><span class="sxs-lookup"><span data-stu-id="2b57a-109">\[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="2b57a-110">Nach Rückgabe der `GetILToNativeMapping3`-Methode enthält `map` einige oder alle `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="2b57a-110">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b57a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b57a-111">Remarks</span></span>

<span data-ttu-id="2b57a-112">Wenn die mehrstufige Kompilierung aktiviert ist, kann eine Methode mehr als einen nativen Code Körper aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2b57a-112">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="2b57a-113">[ICorProfilerInfo9:: getnativecodestartadressen](icorprofilerinfo9-getnativecodestartaddresses-method.md) gibt die Start Adressen für alle systemeigenen Code Körper zurück.</span><span class="sxs-lookup"><span data-stu-id="2b57a-113">[ICorProfilerInfo9::GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="2b57a-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b57a-114">Requirements</span></span>

<span data-ttu-id="2b57a-115">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="2b57a-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="2b57a-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2b57a-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="2b57a-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b57a-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2b57a-118">**.NET Framework Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b57a-118">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2b57a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b57a-119">See also</span></span>

- [<span data-ttu-id="2b57a-120">ICorProfilerInfo9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b57a-120">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
