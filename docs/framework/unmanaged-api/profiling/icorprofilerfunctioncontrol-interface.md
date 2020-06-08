---
title: ICorProfilerFunctionControl-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
ms.openlocfilehash: 177127c8c53e4fee31f7007d04c49cc337cca458
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498725"
---
# <a name="icorprofilerfunctioncontrol-interface"></a>ICorProfilerFunctionControl-Schnittstelle
Stellt Methoden bereit, die einem Codeprofiler ermöglichen, mit der CLR (Common Language Runtime) zu kommunizieren, um zu steuern, wie der JIT-Compiler Code generieren soll, wenn er eine bestimmte Methode neu kompiliert.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[SetCodegenFlags-Methode](icorprofilerfunctioncontrol-setcodegenflags-method.md)|Legt ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) -Enumeration fest, um die Codegenerierung für die neu kompilierte Just-in-time (JIT)-Funktion zu steuern.|  
|[SetILFunctionBody-Methode](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|Ersetzt den CIL-Text (Common Intermediate Language) der Methode.|  
|[SetILInstrumentedCodeMap-Methode](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|Legt eine Codezuordnung für die angegebene Funktion mit den angegebenen Common Intermediate Language (CIL)-Zuordnungseinträgen fest.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die `ICorProfilerFunctionControl`-Schnittstelle stellt Methoden zum Steuern der Codegenerierung für eine einzelne neu kompilierte Funktion bereit. Der Profiler Ruft eine Instanz dieser Schnittstelle über den [ICorProfilerCallback4:: getrejitparameters](icorprofilercallback4-getrejitparameters-method.md) -Rückruf ab. Jede Instanz von `ICorProfilerFunctionControl` steuert alle Instanzen einer Funktion.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo4-Schnittstelle](icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [EnumJITedFunctions2-Methode](icorprofilerinfo4-enumjitedfunctions2-method.md)
