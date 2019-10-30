---
title: ICorProfilerInfo::SetEventMask-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type:
- apiref
ms.openlocfilehash: b79668130570dc69a580fbf7da4dc122389d9ef0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136700"
---
# <a name="icorprofilerinfoseteventmask-method"></a>ICorProfilerInfo::SetEventMask-Methode
Legt einen Wert fest, der die Ereignistypen angibt, für die der Profiler Benachrichtigungen von der Common Language Runtime (CLR) erhalten soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwEvents`  
 [in] Ein 4-Byte-Wert, der die Ereigniskategorien angibt. Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp. Die Bits werden in der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) -Enumeration beschrieben.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Anstelle dieser Methode sollte die [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) -Methode aufgerufen werden. Obwohl die `SetEventMask`-Methode weiterhin unterstützt wird, bietet [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) zusätzliche Funktionen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [SetEventMask2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
