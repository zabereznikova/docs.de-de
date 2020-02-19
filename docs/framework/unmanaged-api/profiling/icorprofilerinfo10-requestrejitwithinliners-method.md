---
title: 'ICorProfilerInfo10:: requestrejitwithinliners'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 99b6893854c358720259095bf3c0270cb3676483
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452174"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a>ICorProfilerInfo10:: requestrejitwithinliners-Methode

Rejits die angeforderten Methoden sowie alle inlinder angeforderten Methoden.

## <a name="syntax"></a>Syntax

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

## <a name="parameters"></a>Parameter

- `dwRejitFlags`

  \[in] eine Bitmaske [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).

- `cFunctions`

  \[in] die Anzahl der neu zu kompilierenden Funktionen.

- `moduleIds`

  \[in] gibt den `moduleId` Teil der (`module`, `methodDef`) Paare an, die die neu zu kompilierenden Funktionen identifizieren.

- `methodIds`

  \[in] gibt den `methodId` Teil der (`module`, `methodDef`) Paare an, die die neu zu kompilierenden Funktionen identifizieren.

## <a name="remarks"></a>Hinweise

[Requestrejit](icorprofilerinfo4-requestrejit-method.md) führt keine Nachverfolgung von Inline Methoden aus. Der Profiler sollte entweder Inlining blockieren oder Inlining nachverfolgen und `RequestReJIT` für alle inlineanrufe abrufen, um sicherzustellen, dass jede Instanz einer Inline Methode erneut generiert wurde. Dies stellt ein Problem mit ReJIT beim Anfügen dar, da der Profiler nicht zum Überwachen des Inlining vorhanden ist. Diese Methode kann aufgerufen werden, um sicherzustellen, dass auch der vollständige Satz von Inliners erneut generiert wird.

## <a name="requirements"></a>Voraussetzungen

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo10-Schnittstelle](icorprofilerinfo10-interface.md)
