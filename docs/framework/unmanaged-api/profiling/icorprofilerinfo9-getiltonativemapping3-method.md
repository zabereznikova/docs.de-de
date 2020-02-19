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
ms.openlocfilehash: 22fe5608b0a3f86baf80abb3810a512077954ac3
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449750"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a>ICorProfilerInfo9:: GetILToNativeMapping3-Methode

Gibt bei der Startadresse des systemeigenen Codes die nativen to Il-Mapping-Informationen für diese JIT-Version des Codes zurück.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

## <a name="parameters"></a>Parameter

- `pNativeCodeStartAddress`

  \[in] ein Zeiger auf den Anfang einer nativen Funktion.

- `cMap`

  \[in] die maximale Größe des `map` Arrays.

- `pcMap`

  \[out] die Gesamtzahl der verfügbaren COR_DEBUG_IL_TO_NATIVE_MAP Strukturen.

- `map`

  \[out] ein Array von [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) Strukturen, von denen jede die Offsets angibt. Nach Rückgabe der `GetILToNativeMapping3`-Methode enthält `map` einige oder alle `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen.

## <a name="remarks"></a>Hinweise

Wenn die mehrstufige Kompilierung aktiviert ist, kann eine Methode mehr als einen nativen Code Körper aufweisen. [ICorProfilerInfo9:: getnativecodestartadressen](icorprofilerinfo9-getnativecodestartaddresses-method.md) gibt die Start Adressen für alle systemeigenen Code Körper zurück.

## <a name="requirements"></a>Voraussetzungen

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo9-Schnittstelle](icorprofilerinfo9-interface.md)
