---
title: ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: 6fbb86fc63a26599ae83c81817dbcb9abfb88cc8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864687"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Benachrichtigt den Profiler, wenn der einem in-Memory-Modul zugeordnete Symbol Datenstrom aktualisiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a>Parameters  
 [in] `moduleId`  
 Der Bezeichner des Moduls im Arbeitsspeicher, dessen symbolstream aktualisiert wird.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Rückruf wird gesteuert, indem das Flag für die [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) -Ereignis Maske beim Aufrufen der [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) -Methode festgelegt wird.  
  
> [!NOTE]
> Dieses Ereignis wird derzeit nicht für Symbole ausgelöst, die über <xref:System.Reflection.Emit> APIs implizit erstellt oder geändert werden.  
  
 Auch wenn Symbole in einem Aufrufs einer der über Ladungen der verwalteten <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methoden bereitgestellt werden, die ein `rawSymbolStore`-Argument zum Angeben der Symbole für die Assembly enthalten, ordnet die Runtime die symbolischen Daten möglicherweise erst dann dem Modul zu, wenn der [moduleloadbeendeten](icorprofilercallback-moduleloadfinished-method.md) -Rückruf aufgetreten ist. Dieses Ereignis bietet eine spätere Gelegenheit, Symbole für solche Module zu erfassen.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ModuleLoadFinished-Methode](icorprofilercallback-moduleloadfinished-method.md)
- [SetEventMask2-Methode](icorprofilerinfo5-seteventmask2-method.md)
- [CorProfilerCallback7-Schnittstelle](icorprofilercallback7-interface.md)
