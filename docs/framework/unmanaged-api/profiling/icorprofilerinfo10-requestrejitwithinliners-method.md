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
ms.openlocfilehash: c33a868b643cb3e3fd5dfaf436e3078bc590705c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449820"
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

#### <a name="parameters"></a>Parameter

`dwRejitFlags` \
in Eine Bitmaske [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).

`cFunctions` \
[in] Die Anzahl der neu zu kompilierenden Funktionen.

`moduleIds` \
[in] Gibt den `moduleId`-Teil der (`module`, `methodDef`)-Paare an, mit denen die neu zu kompilierenden Funktionen identifiziert werden.

`methodIds` \
[in] Gibt den `methodId`-Teil der (`module`, `methodDef`)-Paare an, mit denen die neu zu kompilierenden Funktionen identifiziert werden.

## <a name="remarks"></a>Hinweise

[Requestrejit](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) führt keine Nachverfolgung von Inline Methoden aus. Der Profiler sollte entweder Inlining blockieren oder Inlining nachverfolgen und `RequestReJIT` für alle inlineanrufe abrufen, um sicherzustellen, dass jede Instanz einer Inline Methode erneut generiert wurde. Dies stellt ein Problem mit ReJIT beim Anfügen dar, da der Profiler nicht zum Überwachen des Inlining vorhanden ist. Diese Methode kann aufgerufen werden, um sicherzustellen, dass auch der vollständige Satz von Inliners erneut generiert wird.

## <a name="requirements"></a>Voraussetzungen

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo10-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
