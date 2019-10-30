---
title: ICorDebugILCode2::GetInstrumentedILMap-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
ms.openlocfilehash: 7dede4e5af702f1b86b430450db4a669c326c062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131066"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a>ICorDebugILCode2::GetInstrumentedILMap-Methode
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Gibt eine Zuordnung von Profiler-instrumentierten Intermediate Language (IL) Offsets zu ILs der ursprünglichen Methode für diese Instanz aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 cMap  
 [in] Die Speicherkapazität für das `map`-Array. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 pcMap  
 vorgenommen Die Anzahl der COR_IL_MAP-Werte, die in das Karten Array geschrieben werden.  
  
 Zuordnung  
 vorgenommen Ein Array von COR_IL_MAP-Werten, die Informationen zu Zuordnungen von Profiler-instrumentierter Il zum Il der ursprünglichen Methode bereitstellen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Profiler die Zuordnung durch Aufrufen der [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) -Methode festlegt, kann der Debugger diese Methode aufrufen, um die Zuordnung abzurufen und die Zuordnung intern zu verwenden, wenn IL-Offsets für Stapel Überwachungen und Variablen berechnet werden. Lebensdauer.  
  
 Wenn `cMap` 0 und `pcMap` nicht**null**ist, wird `pcMap` auf die Anzahl der verfügbaren COR_IL_MAP-Werte festgelegt. Wenn `cMap` nicht NULL ist, stellt es die Speicherkapazität des `map`-Arrays dar. Wenn die Methode zurückgibt, enthält `map` maximal `cMap` Elemente, und `pcMap` auf die Anzahl der COR_IL_MAP-Werte festgelegt, die tatsächlich in das `map` Array geschrieben wurden.  
  
 Wenn das IL instrumentiert oder die Zuordnung nicht von einem Profiler bereitgestellt wurde, gibt diese Methode `S_OK` aus und legt `pcMap` auf 0 fest.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo:: Setup-Code Map](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [ICorDebugILCode2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
