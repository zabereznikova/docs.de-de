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
ms.openlocfilehash: cbd7c0d8fff55766a98e727ce22c77dd5214611b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448003"
---
# <a name="icorprofilerinfo4-interface"></a>ICorProfilerInfo4-Schnittstelle
Stellt Methoden bereit, die Code Profiler für die Kommunikation mit dem Common Language Runtime (CLR) verwenden, um die Ereignisüberwachung und Anforderungs Informationen zu steuern. . Die `ICorProfilerInfo4`-Schnittstelle ist eine Erweiterung der anderen `ICorProfilerInfo` Schnittstellen. Es bietet neue Methoden zur Unterstützung der JIT-Neukompilierung (Just-in-Time), die in der .NET Framework 4,5 hinzugefügt wurde.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumJITedFunctions2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|Gibt einen Enumerator für alle Funktionen zurück, die zuvor JIT-kompiliert und JIT-neu kompiliert wurden.|  
|[EnumThreads-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|Ruft einen Enumerator ab, der Methoden zum sequenziellen durchlaufen der Auflistung aller verwalteten Threads im Profil Erstellungs Prozess bereitstellt.|  
|[GetCodeInfo3-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|Ruft die Erweiterungen des systemeigenen Codes ab, die der JIT-kompilierten Version der angegebenen Funktion zugeordnet sind.|  
|[GetFunctionFromIP2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|Ordnet einen Anweisungs Zeiger für verwalteten Code der JIT-neu kompilierten Version einer angegebenen Funktion zu.|  
|[GetILToNativeMapping2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|Ruft eine Zuordnung von MSIL-Offsets (Microsoft Intermediate Language) zu nativen Offsets für den Code ab, der in der JIT-neu kompilierten Version der angegebenen Funktion enthalten ist.|  
|[GetObjectSize2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|Gibt die Größe eines angegebenen-Objekts zurück.|  
|[GetReJITIDs-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|Gibt ein Array von IDs zurück, die alle JIT-neu kompilierten Versionen der angegebenen Funktion identifizieren, die noch zugeordnet sind.|  
|[InitializeCurrentThread-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|Initialisiert den aktuellen Thread vor nachfolgenden Profiler-API-aufrufen im gleichen Thread, sodass der Deadlock vermieden werden kann.|  
|[RequestReJIT-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|Fordert eine JIT-Neukompilierung aller Instanzen der angegebenen Funktionen an.|  
|[RequestRevert-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|Setzt alle Instanzen der angegebenen Funktionen auf die ursprünglichen Versionen zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR implementiert die Methoden der `ICorProfilerInfo4`-Schnittstelle mithilfe des Freethreadmodells. Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben. Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
