---
title: ICorProfilerModuleEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
ms.openlocfilehash: 98b64289b7d512c4e73cf4d40e89319532c6704a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722816"
---
# <a name="icorprofilermoduleenum-interface"></a>ICorProfilerModuleEnum-Schnittstelle

Stellt Methoden bereit, um eine Auflistung von Modulen, die von der Anwendung oder dem Profiler geladen wurden, sequenziell zu durchlaufen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Clone-Methode](icorprofilermoduleenum-clone-method.md)|Ruft einen Schnittstellenzeiger auf eine Kopie dieser `ICorProfilerModuleEnum`-Schnittstelle ab.|  
|[GetCount-Methode](icorprofilermoduleenum-getcount-method.md)|Ruft die Anzahl der verwalteten Module ab, die in die Anwendung geladen wurden.|  
|[Next-Methode](icorprofilermoduleenum-next-method.md)|Ruft die angegebene Anzahl zusammenhängender Module aus einer sequenziellen Auflistung von Objekten ab und beginnt damit an der aktuellen Position des Enumerators in der Sequenz.|  
|[Reset-Methode](icorprofilermoduleenum-reset-method.md)|Verschiebt den Cursor des Enumerators an die Anfangsposition der Sequenz.|  
|[Skip-Methode](icorprofilermoduleenum-skip-method.md)|Verschiebt die Cursorposition des Enumerators so, dass die angegebene Anzahl von Elementen übersprungen wird.|  
  
## <a name="remarks"></a>Hinweise  

 Die `ICorProfilerModuleEnum`-Schnittstelle ist ein Enumerator. Hiermit kann der Empfänger eines Arrays mit einer Rate, die für den Empfänger geeignet ist, Elemente vom Absender abrufen. Anders ausgedrückt: Der Empfänger kann explizit den Fluss der Arrayelemente steuern und auf diese Weise Probleme im Zusammenhang mit der Übergabe großer Arrays als Methodenparameter vermeiden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [EnumModules-Methode](icorprofilerinfo3-enummodules-method.md)
