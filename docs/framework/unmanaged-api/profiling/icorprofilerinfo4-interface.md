---
title: ICorProfilerInfo4-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: 58d11e9084f53c69f2656b4f0ee6bc7d2cc4ae21
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495865"
---
# <a name="icorprofilerinfo4-interface"></a>ICorProfilerInfo4-Schnittstelle
Stellt Methoden bereit, die Code Profiler für die Kommunikation mit dem Common Language Runtime (CLR) verwenden, um die Ereignisüberwachung und Anforderungs Informationen zu steuern. . Die- `ICorProfilerInfo4` Schnittstelle ist eine Erweiterung der anderen `ICorProfilerInfo` Schnittstellen. Es bietet neue Methoden zur Unterstützung der JIT-Neukompilierung (Just-in-Time), die in der .NET Framework 4,5 hinzugefügt wurde.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnumJITedFunctions2-Methode](icorprofilerinfo4-enumjitedfunctions2-method.md)|Gibt einen Enumerator für alle Funktionen zurück, die zuvor JIT-kompiliert und JIT-neu kompiliert wurden.|  
|[EnumThreads-Methode](icorprofilerinfo4-enumthreads-method.md)|Ruft einen Enumerator ab, der Methoden zum sequenziellen durchlaufen der Auflistung aller verwalteten Threads im Profil Erstellungs Prozess bereitstellt.|  
|[GetCodeInfo3-Methode](icorprofilerinfo4-getcodeinfo3-method.md)|Ruft die Erweiterungen des systemeigenen Codes ab, die der JIT-kompilierten Version der angegebenen Funktion zugeordnet sind.|  
|[GetFunctionFromIP2-Methode](icorprofilerinfo4-getfunctionfromip2-method.md)|Ordnet einen Anweisungs Zeiger für verwalteten Code der JIT-neu kompilierten Version einer angegebenen Funktion zu.|  
|[GetILToNativeMapping2-Methode](icorprofilerinfo4-getiltonativemapping2-method.md)|Ruft eine Zuordnung von MSIL-Offsets (Microsoft Intermediate Language) zu nativen Offsets für den Code ab, der in der JIT-neu kompilierten Version der angegebenen Funktion enthalten ist.|  
|[GetObjectSize2-Methode](icorprofilerinfo4-getobjectsize2-method.md)|Gibt die Größe eines angegebenen-Objekts zurück.|  
|[GetReJITIDs-Methode](icorprofilerinfo4-getrejitids-method.md)|Gibt ein Array von IDs zurück, die alle JIT-neu kompilierten Versionen der angegebenen Funktion identifizieren, die noch zugeordnet sind.|  
|[InitializeCurrentThread-Methode](icorprofilerinfo4-initializecurrentthread-method.md)|Initialisiert den aktuellen Thread vor nachfolgenden Profiler-API-aufrufen im gleichen Thread, sodass der Deadlock vermieden werden kann.|  
|[RequestReJIT-Methode](icorprofilerinfo4-requestrejit-method.md)|Fordert eine JIT-Neukompilierung aller Instanzen der angegebenen Funktionen an.|  
|[RequestRevert-Methode](icorprofilerinfo4-requestrevert-method.md)|Setzt alle Instanzen der angegebenen Funktionen auf die ursprünglichen Versionen zurück.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die CLR implementiert die Methoden der `ICorProfilerInfo4`-Schnittstelle mithilfe des Freethreadmodells. Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben. Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
