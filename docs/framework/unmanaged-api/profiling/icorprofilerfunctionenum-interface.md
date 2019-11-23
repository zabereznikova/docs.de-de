---
title: ICorProfilerFunctionEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum
helpviewer_keywords:
- ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type:
- apiref
ms.openlocfilehash: 17f7243096b7ac18e456f8f31196055492015346
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447799"
---
# <a name="icorprofilerfunctionenum-interface"></a>ICorProfilerFunctionEnum-Schnittstelle
Stellt Methoden bereit, um eine Auflistung von Funktionen in der CLR (Common Language Runtime) sequenziell zu durchlaufen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Clone-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|Ruft einen Schnittstellenzeiger auf eine Kopie dieser `ICorProfilerFunctionEnum`-Schnittstelle ab.|  
|[GetCount-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|Ruft die Anzahl der Funktionen ab, die von der Anwendung oder erzwungen vom Profiler geladen wurden.|  
|[Next-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|Ruft die angegebene Anzahl von zusammenhängenden Funktionen aus einer sequenziellen Auflistung von Funktionen ab und beginnt damit an der aktuellen Position des Enumerators in der Sequenz.|  
|[Reset-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|Verschiebt den Cursor des Enumerators an die Anfangsposition der Sequenz.|  
|[Skip-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|Verschiebt den Cursor des Enumerators so aus seiner aktuellen Position, dass die angegebene Anzahl von Elementen übersprungen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorProfilerFunctionEnum`-Schnittstelle ist ein Enumerator. Hiermit kann der Empfänger eines Arrays mit einer Rate, die für den Empfänger geeignet ist, Elemente vom Absender abrufen. Anders ausgedrückt: Der Empfänger kann explizit den Fluss der Arrayelemente steuern und auf diese Weise Probleme im Zusammenhang mit der Übergabe großer Arrays als Methodenparameter vermeiden.  
  
 `ICorProfilerFunctionEnum` zählt Funktionen auf, die bereits mit JIT kompiliert wurden, jedoch keine Funktionen, die aus mit "Ngen.exe" generierten systemeigenen Images geladen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [EnumJITedFunctions-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
