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
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a>ICorProfilerInfo9:: getnativecodestartadressen-Methode

Listet bei Angabe von FunctionID und rejitid die Startadresse des systemeigenen Codes aller JIT-Versionen dieses Codes auf, die derzeit vorhanden sind.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

#### <a name="parameters"></a>Parameter

`functionId` \
in Die ID der Funktion, deren Start Adressen für den ursprünglichen Code zurückgegeben werden sollen.

`reJitId` \
[in] Die Identität der erneut JIT-kompilierten Funktion.

`cCodeStartAddresses` \
[in] Die maximale Größe des `codeStartAddresses`-Arrays.

`pcCodeStartAddresses` \
vorgenommen Die Anzahl der verfügbaren Adressen.

`codeStartAddresses` \
vorgenommen Ein-Array `UINT_PTR`, von dem jeder die Startadresse für einen systemeigenen Text für die angegebene Funktion ist.

## <a name="remarks"></a>Hinweise

Wenn die mehrstufige Kompilierung aktiviert ist, kann eine Funktion mehr als einen nativen Code Körper aufweisen.

## <a name="requirements"></a>Anforderungen

**Formen** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).

**Header:** Corprof. idl, Corprof. h

**Fern** CorGuids.lib

**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo9-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)
