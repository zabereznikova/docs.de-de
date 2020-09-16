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
ms.openlocfilehash: e3d5a09730cb8e477bd506749017a403acff1696
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540557"
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

  \[in] eine Bitmaske von [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).

- `cFunctions`

  \[in] die Anzahl der neu zu kompilierenden Funktionen.

- `moduleIds`

  \[in] gibt den- `moduleId` Teil der ( `module` , `methodDef` )-Paare an, mit denen die neu zu kompilierenden Funktionen identifiziert werden.

- `methodIds`

  \[in] gibt den- `methodId` Teil der ( `module` , `methodDef` )-Paare an, mit denen die neu zu kompilierenden Funktionen identifiziert werden.

## <a name="remarks"></a>Hinweise

[Requestrejit](icorprofilerinfo4-requestrejit-method.md) führt keine Nachverfolgung von Inline Methoden aus. Es wurde erwartet, dass der Profiler Inlining blockiert oder Inline nachverfolgt und `RequestReJIT` für alle Inlinedaten aufruft, um sicherzustellen, dass jede Instanz einer Inline Methode erneut generiert wurde. Dies stellt ein Problem mit ReJIT beim Anfügen dar, da der Profiler nicht zum Überwachen des Inlining vorhanden ist. Diese Methode kann aufgerufen werden, um sicherzustellen, dass auch der vollständige Satz von Inliners erneut generiert wird.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/windows.md?pivots=os-windows).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET-Versionen:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo10-Schnittstelle](icorprofilerinfo10-interface.md)
