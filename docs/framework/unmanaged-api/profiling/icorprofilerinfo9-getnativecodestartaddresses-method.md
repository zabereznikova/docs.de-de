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

## <a name="parameters"></a>Parameters

- `functionId`

  \[in] die ID der Funktion, deren Start Adressen für den nativen Code zurückgegeben werden sollen.

- `reJitId`

  \[in] die Identität der JIT-neu kompilierten Funktion.

- `cCodeStartAddresses`

  \[in] die maximale Größe des `codeStartAddresses` Arrays.

- `pcCodeStartAddresses`

  \[out] die Anzahl der verfügbaren Adressen.

- `codeStartAddresses`

  \[out] ein Array von `UINT_PTR`, von denen jedes die Startadresse für einen systemeigenen Text für die angegebene Funktion ist.

## <a name="remarks"></a>Hinweise

Wenn die mehrstufige Kompilierung aktiviert ist, kann eine Funktion mehr als einen nativen Code Körper aufweisen.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo9-Schnittstelle](icorprofilerinfo9-interface.md)
