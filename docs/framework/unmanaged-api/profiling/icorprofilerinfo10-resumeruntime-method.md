---
title: 'ICorProfilerInfo10:: resumeruntime'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.ResumeRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 49de3383902791b1278e7c9221a80c3454eb12a2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868919"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a>ICorProfilerInfo10:: resumeruntime-Methode

Setzt die Laufzeit fort, ohne eine GC auszuführen.

## <a name="syntax"></a>Syntax

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo10-Schnittstelle](icorprofilerinfo10-interface.md)
