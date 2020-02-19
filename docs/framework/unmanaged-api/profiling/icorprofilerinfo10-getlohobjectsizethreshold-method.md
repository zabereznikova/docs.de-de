---
title: 'ICorProfilerInfo10:: getlohobjectsizethreshold'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 7a0f6f6bea5bc919ebfe9c9acc3b02a31eaa7cd0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452213"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a>ICorProfilerInfo10:: getlohobjectsizethreshold-Methode

Ruft den Wert des konfigurierten Heap-Schwellenwerts (Large Object Heap) ab.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a>Parameter

- `pThreshold`

  \[out] der Schwellenwert für große Objekt Heaps in Bytes.

## <a name="remarks"></a>Hinweise

Objekte, die größer sind als der Schwellenwert für den großen Objekt Heap, werden auf dem großen Objekt Heap zugeordnet. Ab .net Core 3,0 ist der Schwellenwert für den großen Objekt Heap konfigurierbar, `pThreshold` den Schwellenwert für den aktiven Heap für große Objekte in Bytes enthält.

## <a name="requirements"></a>Voraussetzungen

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo10-Schnittstelle](icorprofilerinfo10-interface.md)
