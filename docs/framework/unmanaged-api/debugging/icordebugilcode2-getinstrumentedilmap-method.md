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
ms.openlocfilehash: 097502f4321531922d6c4385e2eccbf32f66f026
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688353"
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
 [out] Die Anzahl von COR_IL_MAP-Werten, die in das Zuordnungsarray geschrieben wurden.  
  
 map  
 [out] Ein Array von COR_IL_MAP-Werten, die Informationen über Zuordnungen von Profiler-instrumentierter IL zur IL der ursprünglichen Methode enthalten.  
  
## <a name="remarks"></a>Hinweise  

 Wenn der Profiler die Zuordnung durch Aufrufen der [ICorProfilerInfo:: SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) -Methode festlegt, kann der Debugger diese Methode aufrufen, um die Zuordnung abzurufen und die Zuordnung intern zu verwenden, wenn IL-Offsets für Stapel Überwachungen und die Lebensdauer von Variablen berechnet werden.  
  
 Wenn `cMap` 0 (null) und `pcMap` nicht **null** ist, `pcMap` wird auf die Anzahl der verfügbaren COR_IL_MAP Werte festgelegt. Wenn `cMap` nicht NULL ist, stellt es die Speicherkapazität des `map`-Arrays dar. Wenn die-Methode zurückgibt, `map` enthält maximal `cMap` Elemente und `pcMap` ist auf die Anzahl der COR_IL_MAP Werte festgelegt, die tatsächlich in das Array geschrieben wurden `map` .  
  
 Wenn das IL instrumentiert oder die Zuordnung nicht von einem Profiler bereitgestellt wurde, gibt diese Methode `S_OK` aus und legt `pcMap` auf 0 fest.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo::SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [ICorDebugILCode2-Schnittstelle](icordebugilcode2-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
