---
title: 'ICorProfilerCallback7:: moduleinmemorysymbolsupveraltet-Methode'
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: 248d2f749ddcbd772313558af2b2721f4d1c0f58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723089"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>ICorProfilerCallback7:: moduleinmemorysymbolsupveraltet-Methode

[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Benachrichtigt den Profiler, wenn der einem in-Memory-Modul zugeordnete Symbol Datenstrom aktualisiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a>Parameter  

 [in] `moduleId`  
 Der Bezeichner des Moduls im Arbeitsspeicher, dessen symbolstream aktualisiert wird.  
  
## <a name="remarks"></a>Hinweise  

 Dieser Rückruf wird gesteuert, indem das Flag für die [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) -Ereignis Maske beim Aufrufen der [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) -Methode festgelegt wird.  
  
> [!NOTE]
> Dieses Ereignis wird derzeit nicht für Symbole ausgelöst, die über APIs implizit erstellt oder geändert werden <xref:System.Reflection.Emit> .  
  
 Auch wenn Symbole im Vordergrund in einem Aufrufs einer der über Ladungen der verwalteten Methoden bereitgestellt werden, die <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> ein- `rawSymbolStore` Argument zum Angeben der Symbole für die Assembly enthalten, ordnet die Runtime die symbolischen Daten möglicherweise erst dann dem Modul zu, wenn der [moduleloadbeendeten](icorprofilercallback-moduleloadfinished-method.md) -Rückruf aufgetreten ist. Dieses Ereignis bietet eine spätere Gelegenheit, Symbole für solche Module zu erfassen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ModuleLoadFinished-Methode](icorprofilercallback-moduleloadfinished-method.md)
- [SetEventMask2-Methode](icorprofilerinfo5-seteventmask2-method.md)
- [ICorProfilerCallback7-Schnittstelle](icorprofilercallback7-interface.md)
