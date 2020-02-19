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
ms.openlocfilehash: 9aadf9701444d215291b6fc19cc8cd61ca832837
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452239"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a>ICorProfilerInfo10:: enumerateobjectreferences-Methode

Bei Angabe von ObjectID, Callback und clientData listet alle Objekt Verweise auf (sofern vorhanden).

## <a name="syntax"></a>Syntax

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a>Parameter

- `objectId`

  \[in] das-Objekt, für das Verweise aufgelistet werden sollen.

- `callback`

  \[in] die Funktion, die mit den verweisen für das-Objekt aufgerufen wird.

- `clientData`

  \[in] vom Profiler bereitgestellte Daten, die an die `callback`-Funktion übergeben werden.

## <a name="remarks"></a>Hinweise

Die `EnumerateObjectReferences`-Methode ähnelt [ObjectReferences](icorprofilercallback-objectreferences-method.md), mit dem Unterschied, dass Sie die Verweise nach Bedarf für den Profiler durchläuft, anstatt ein Array zum Speichern der Verweise vorab zuzuordnen.

## <a name="requirements"></a>Voraussetzungen

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo10-Schnittstelle](icorprofilerinfo10-interface.md)
