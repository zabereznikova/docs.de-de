---
title: ICorProfilerInfo5::GetEventMask2-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8ebddf9a16b2eddbbc58342f68b517064e8d794
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041040"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a>ICorProfilerInfo5::GetEventMask2-Methode
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Ruft die aktuellen Ereigniskategorien ab, für die der Profiler Benachrichtigungen von der Common Language Runtime (CLR) empfangen soll.  Es bietet Funktionalität, die nicht von der [ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pdwEventsLow`  
 [out] Ein Zeiger auf einen 4-Byte-Wert, der die Ereigniskategorien angibt. Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp. Die Bits werden beschrieben, der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration.  
  
 `pdwEventsHigh`  
 [out] Ein Zeiger auf einen 4-Byte-Wert, der die Ereigniskategorien angibt.  Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp. Die Bits werden beschrieben, der [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) Enumeration.  
  
## <a name="remarks"></a>Hinweise  
 Die Methode `GetEventMask2` wird verwendet um feststellen, welchen Rückruf der Profiler abonniert hat. In der Regel ein logisches OR der Durchführung der `pdwEventsLow` und `pdwEventsHigh` Werte sowie neuer Bits festgelegt, und klicken Sie dann aufgerufen werden soll die [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methode.  
  
 Diese Methode ist die empfohlene Alternative zur der [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo5-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [SetEventMask2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
