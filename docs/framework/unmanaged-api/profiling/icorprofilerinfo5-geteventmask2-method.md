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
ms.openlocfilehash: 81509db178b0ab1a524dcc4b00f39264e87a220d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682782"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a>ICorProfilerInfo5::GetEventMask2-Methode

[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Ruft die aktuellen Ereigniskategorien ab, für die der Profiler Benachrichtigungen von der Common Language Runtime (CLR) empfangen soll.  Sie stellt Funktionen bereit, die nicht von der [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) -Methode bereitgestellt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pdwEventsLow`  
 [out] Ein Zeiger auf einen 4-Byte-Wert, der die Ereigniskategorien angibt. Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp. Die Bits werden in der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration beschrieben.  
  
 `pdwEventsHigh`  
 [out] Ein Zeiger auf einen 4-Byte-Wert, der die Ereigniskategorien angibt.  Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp. Die Bits werden in der [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) -Enumeration beschrieben.  
  
## <a name="remarks"></a>Hinweise  

 Die Methode `GetEventMask2` wird verwendet um feststellen, welchen Rückruf der Profiler abonniert hat. Normalerweise führen Sie ein logisches OR der `pdwEventsLow` Werte und `pdwEventsHigh` und neuer Bits aus, die Sie festlegen möchten, und dann die [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) -Methode.  
  
 Diese Methode ist die empfohlene Alternative zur [GetEventMask](icorprofilerinfo-geteventmask-method.md) -Methode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo5-Schnittstelle](icorprofilerinfo5-interface.md)
- [SetEventMask2-Methode](icorprofilerinfo5-seteventmask2-method.md)
