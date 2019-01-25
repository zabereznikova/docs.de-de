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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2abb24a319d8d3aff940ddb7eabd16b3e238862
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611747"
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
  
#### <a name="parameters"></a>Parameter  
 cMap  
 [in] Die Speicherkapazität für das `map`-Array. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 pcMap  
 [out] Die Anzahl der COR_IL_MAP-Werte, die in das Zuordnungsarray geschrieben werden soll.  
  
 Zuordnung  
 [out] Ein Array von COR_IL_MAP-Werte, die Informationen auf Zuordnungen von Profiler-instrumentierter IL zur IL der ursprünglichen Methode bereitstellen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn bei der Profiler die Zuordnung durch Aufrufen der [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) -Methode der Debugger kann diese Methode aufrufen und die Zuordnung verwenden intern beim Berechnen des IL-für Stack Offsets aufrufen ablaufverfolgungen und Variable Lebensdauer.  
  
 Wenn `cMap` ist 0 und `pcMap` nicht**null**, `pcMap` auf die Anzahl der verfügbaren COR_IL_MAP-Werte festgelegt ist. Wenn `cMap` ungleich null ist, stellt es die Speicherkapazität des `map`-Arrays dar. Wenn die Methode zurückgibt, `map` enthält maximal `cMap` Elemente und `pcMap` festgelegt ist, auf die Anzahl der tatsächlich geschriebenen COR_IL_MAP-Werte der `map` Array.  
  
 Wenn das IL instrumentiert oder die Zuordnung nicht von einem Profiler bereitgestellt wurde, gibt diese Methode `S_OK` aus und legt `pcMap` auf 0 fest.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [ICorDebugILCode2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
