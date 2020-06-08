---
title: ICorProfilerInfo4::RequestReJIT-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestReJIT
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestReJIT
helpviewer_keywords:
- RequestReJIT method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestReJIT method [.NET Framework profiling]
ms.assetid: 781ed736-f30c-4816-920e-3552e36542c6
topic_type:
- apiref
ms.openlocfilehash: 7dd82f2dfab885070df4789fe5efc16a49d50e06
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495800"
---
# <a name="icorprofilerinfo4requestrejit-method"></a>ICorProfilerInfo4::RequestReJIT-Methode
Fordert eine JIT-Neukompilierung aller Instanzen der angegebenen Funktionen an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RequestReJIT (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cFunctions`  
 [in] Die Anzahl der neu zu kompilierenden Funktionen.  
  
 `moduleIds`  
 [in] Gibt den `moduleId`-Teil der (`module`, `methodDef`)-Paare an, mit denen die neu zu kompilierenden Funktionen identifiziert werden.  
  
 `methodIds`  
 [in] Gibt den `methodId`-Teil der (`module`, `methodDef`)-Paare an, mit denen die neu zu kompilierenden Funktionen identifiziert werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Es wurde versucht, alle Methoden für die JIT-Neukompilierung zu markieren. Der Profiler muss die [ICorProfilerCallback4:: rejiterror](icorprofilercallback4-rejiterror-method.md) -Methode implementieren, um zu bestimmen, welche Methoden erfolgreich für die JIT-Neukompilierung gekennzeichnet wurden.|  
|CORPROF_E_CALLBACK4_REQUIRED|Der Profiler muss die [ICorProfilerCallback4](icorprofilercallback4-interface.md) -Schnittstelle implementieren, damit dieser-Befehl unterstützt wird.|  
|CORPROF_E_REJIT_NOT_ENABLED|Die JIT-Neukompilierung wurde nicht aktiviert. Sie müssen die JIT-Neukompilierung während der Initialisierung aktivieren, indem Sie die [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um das-Flag festzulegen `COR_PRF_ENABLE_REJIT` .|  
|E_INVALIDARG|`cFunctions` ist 0, oder `moduleIds` oder `methodIds` ist `NULL`.|  
|||  
|E_OUTOFMEMORY|Die CLR konnte die Anforderung nicht abschließen, da nicht genügend Arbeitsspeicher vorhanden war.|  
  
## <a name="remarks"></a>Bemerkungen  
 Rufen Sie `RequestReJIT` auf, damit die Common Language Runtime einen angegebenen Satz von Funktionen neu kompiliert. Ein Codeprofiler kann dann die [icorprofilerfunctioncontrol](icorprofilerfunctioncontrol-interface.md) -Schnittstelle verwenden, um den Code anzupassen, der generiert wird, wenn die Funktionen erneut kompiliert werden. Dies wirkt sich nicht auf derzeit ausgeführte Funktionen, sondern nur auf zukünftige Funktionsaufrufe aus. Wenn eine der angegebenen Funktionen bereits zuvor erneut JIT-kompiliert wurde, entspricht das Anfordern einer Neukompilierung dem Zurücksetzen und erneuten Kompilieren der Funktion. Um die Umkehrbarkeit zu bewahren, berücksichtigt der JIT-Compiler beim Kompilieren der ursprünglichen Version einer Funktion nur die ursprünglichen Versionen der Aufgerufenen bei Entscheidungen zum Inlining. Wenn der JIT-Compiler eine Funktion neu kompiliert, berücksichtigt er die aktuellen Versionen (erneut kompilierte oder ursprüngliche Versionen) der Aufgerufenen für das Inlining.  
  
 Ein Profiler ruft in der Regel `RequestReJIT` als Reaktion auf eine Benutzereingabe auf, mit der angefordert wird, dass der Profiler eine oder mehrere Methoden instrumentiert. `RequestReJIT` hält normalerweise die Common Language Runtime an, um einige Aufgaben auszuführen, und kann möglicherweise eine Garbage Collection auslösen. Daher sollte der Profiler `RequestReJIT` aus einem zuvor erstellten Thread aufrufen und nicht aus einem durch die CLR erstellten Thread, der aktuell einen Profilerrückruf ausführt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo4-Schnittstelle](icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
