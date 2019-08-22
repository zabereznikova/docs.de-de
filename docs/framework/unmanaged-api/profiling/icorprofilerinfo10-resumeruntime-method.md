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
ms.openlocfilehash: cf599e5ded73b09d54c98dcd99f51b30c6a4ba82
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661208"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a>ICorProfilerInfo10:: resumeruntime-Methode

Setzt die Laufzeit fort, ohne eine GC auszuführen.

## <a name="syntax"></a>Syntax

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a>Anforderungen

**Formen** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).

**Header:** Corprof. idl, Corprof. h

**Fern** CorGuids.lib

**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo10-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
