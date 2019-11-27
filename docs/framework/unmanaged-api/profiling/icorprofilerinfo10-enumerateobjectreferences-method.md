---
title: 'ICorProfilerInfo10:: enumerateobjectreferences'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: d6518612c213d21c2dc7d80878121ccd3b7e2abb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449853"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a>ICorProfilerInfo10:: enumerateobjectreferences-Methode

Bei Angabe von ObjectID, Callback und clientData listet alle Objekt Verweise auf (sofern vorhanden).

## <a name="syntax"></a>Syntax

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

#### <a name="parameters"></a>Parameter

`objectId` \
in Das Objekt, auf das Verweise aufgelistet werden sollen.

`callback` \
in Die Funktion, die mit den verweisen für das-Objekt aufgerufen wird.

`clientData` \
in Vom Profiler bereitgestellte Daten, die an die `callback`-Funktion übergeben werden.

## <a name="remarks"></a>Hinweise

Die `EnumerateObjectReferences`-Methode ähnelt [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), mit dem Unterschied, dass Sie die Verweise nach Bedarf für den Profiler durchläuft, anstatt ein Array zum Speichern der Verweise vorab zuzuordnen.

## <a name="requirements"></a>Voraussetzungen

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo10-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
