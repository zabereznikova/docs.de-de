---
title: ICorProfilerInfo4-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 83629d0fc8288d118ec31c38473cb63335bb1d48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4-interface"></a>ICorProfilerInfo4-Schnittstelle
Enthält Methoden, mit denen Codeprofiler mit der common Language Runtime (CLR), um die ereignisüberwachung zu steuern und Informationen zu kommunizieren. sein. Die `ICorProfilerInfo4` Schnittstelle ist eine Erweiterung der anderen `ICorProfilerInfo` Schnittstellen. Es bietet neue Methoden zur Unterstützung von Just-in-Time (JIT)-Neukompilierung hinzugefügt, der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumJITedFunctions2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|Gibt einen Enumerator für alle Funktionen, die bereits JIT-kompiliert und JIT-kompiliert wurden.|  
|[EnumThreads-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|Ruft einem Enumerator ab, das Methoden zum sequenziellen iterieren durch die Auflistung aller verwalteten Threads im profilierten Prozess bereitstellt.|  
|[GetCodeInfo3-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|Ruft die Erweiterungen des nativen Codes ab, die der JIT-kompilierten Version der angegebenen Funktion zugeordnet sind.|  
|[GetFunctionFromIP2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|Ordnet einen verwalteten Code Anweisungszeiger der JIT-kompilierten Version einer angegebenen Funktion.|  
|[GetILToNativeMapping2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|Ruft eine Zuordnung von Microsoft intermediate Language (MSIL)-und systemeigenen Offsets für den in der JIT-kompilierten Version der angegebenen Funktion enthaltenen Code Offsets ab.|  
|[GetObjectSize2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|Gibt die Größe eines angegebenen Objekts zurück.|  
|[GetReJITIDs-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|Gibt ein Array von IDs, die alle JIT-kompilierten Version der angegebenen Funktion zu identifizieren, die dennoch zugeordnet sind.|  
|[InitializeCurrentThread-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|Initialisiert den aktuellen Thread im Vorfeld nachfolgende Profiler, die auf dem gleichen Thread-API-Aufrufe, sodass dieser Deadlock vermieden werden kann.|  
|[RequestReJIT-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|Fordert eine JIT-Neukompilierung aller Instanzen der angegebenen Funktionen an.|  
|[RequestRevert-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|Setzt alle Instanzen der angegebenen Funktionen auf die ursprünglichen Versionen zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR implementiert die Methoden der `ICorProfilerInfo4`-Schnittstelle mithilfe des Freethreadmodells. Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben. Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
