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
ms.openlocfilehash: ce29703a181106353695414e8b291b14c697fc56
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444787"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a>ICorProfilerInfo9::GetCodeInfo4 Method

Given the native code start address, returns the blocks of virtual memory that store this code.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

#### <a name="parameters"></a>Parameter

`pNativeCodeStartAddress` \
[in] A pointer to the start of a native function.

`cCodeInfos` \
[in] Die Größe des `codeInfos`-Arrays.

`pcCodeInfos` \
[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.

`codeInfos` \
[out] Ein vom Aufrufer bereitgestellter Puffer. Nach dem Ausführen enthält die Methode ein Array aus `COR_PRF_CODE_INFO`-Strukturen, von denen jede einen Block des systemeigenen Codes beschreibt.

## <a name="remarks"></a>Hinweise

The `GetCodeInfo4` method is similar to [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.

> [!NOTE]
> `GetCodeInfo4` can trigger a garbage collection.

Die Wertebereiche sind in aufsteigender Reihenfolge des CIL-Offsets (Common Intermediate Language) sortiert.

After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures. Vergleichen Sie hierzu den Wert von `cCodeInfos` mit dem Wert des `cchName`-Parameters. If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.

Alternativ können Sie zuerst `GetCodeInfo4` mit einem `codeInfos`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln. You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.

## <a name="requirements"></a>Anforderungen

**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo9 Interface](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)
