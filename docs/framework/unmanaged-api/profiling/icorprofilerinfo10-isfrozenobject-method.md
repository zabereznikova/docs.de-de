---
title: 'ICorProfilerInfo10:: isfrozenobject'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 21f9cb415f913a9c865a487f6e80523344db811e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452187"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a>ICorProfilerInfo10:: isfrozenobject-Methode

Bestimmt bei Angabe einer ObjectID, ob das Objekt ein Schreib geschütztes Segment ist.

## <a name="syntax"></a>Syntax

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a>Parameter

- `objectId`

  \[in] das zu überprüfende-Objekt.

- `pbFrozen`

  \[out] ein `BOOL`, der angibt, ob das Objekt ein Schreib geschütztes Segment ist.

## <a name="requirements"></a>Voraussetzungen

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo10-Schnittstelle](icorprofilerinfo10-interface.md)
