---
title: ICorDebugILCode2::GetInstrumentedILMap-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0499813bc2192d419dc21d9dbb84aff17894544f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
 [out] Die Anzahl der COR_IL_MAP-Werte, die in das Zuordnungsarray geschrieben.  
  
 Zuordnung  
 [out] Ein Array von COR_IL_MAP-Werte, die Informationen über Zuordnungen von Profiler-instrumentierter IL zur IL der ursprünglichen Methode enthalten.  
  
## <a name="remarks"></a>Hinweise  
 Wenn bei der Profiler die Zuordnung durch Aufrufen der [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) -Methode, der Debugger kann diese Methode zum Abrufen der Zuordnung und die Zuordnung verwendet intern beim Berechnen des IL-für die Stack Offsets aufrufen ablaufverfolgungen und Variable Lebensdauer.  
  
 Wenn `cMap` ist 0 und `pcMap` nicht**null**, `pcMap` auf die Anzahl der verfügbaren COR_IL_MAP-Werte festgelegt ist. Wenn `cMap` ungleich null ist, stellt es die Speicherkapazität des `map`-Arrays dar. Wenn die Methode zurückkehrt, `map` höchstens `cMap` Elemente und `pcMap` festgelegt ist, um die Anzahl der tatsächlich geschriebenen COR_IL_MAP-Werte der `map` Array.  
  
 Wenn das IL instrumentiert oder die Zuordnung nicht von einem Profiler bereitgestellt wurde, gibt diese Methode `S_OK` aus und legt `pcMap` auf 0 fest.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)  
 [ICorDebugILCode2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
