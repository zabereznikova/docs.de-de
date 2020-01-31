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
ms.openlocfilehash: d4d498c1d75625b2abc37dc1f4c88d73b58ec675
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790016"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a>ICorProfilerInfo10:: getlohobjectsizethreshold-Methode

Ruft den Wert des konfigurierten Heap-Schwellenwerts (Large Object Heap) ab.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a>Parameters

- `pThreshold`

  \[out] der Schwellenwert für große Objekt Heaps in Bytes.

## <a name="remarks"></a>Hinweise

Objekte, die größer sind als der Schwellenwert für den großen Objekt Heap, werden auf dem großen Objekt Heap zugeordnet. Ab .net Core 3,0 ist der Schwellenwert für den großen Objekt Heap konfigurierbar, `pThreshold` den Schwellenwert für den aktiven Heap für große Objekte in Bytes enthält.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo10-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
