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
ms.openlocfilehash: 61c3867540195329d5322686433e2896d398330d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429974"
---
# <a name="icorprofilerfunctioncontrol-interface"></a>ICorProfilerFunctionControl-Schnittstelle
Stellt Methoden bereit, die einem Codeprofiler ermöglichen, mit der CLR (Common Language Runtime) zu kommunizieren, um zu steuern, wie der JIT-Compiler Code generieren soll, wenn er eine bestimmte Methode neu kompiliert.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[SetCodegenFlags-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|Legt ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) -Enumeration fest, um die Codegenerierung für die neu kompilierte Just-in-time (JIT)-Funktion zu steuern.|  
|[SetILFunctionBody-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|Ersetzt den CIL-Text (Common Intermediate Language) der Methode.|  
|[SetILInstrumentedCodeMap-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|Legt eine Codezuordnung für die angegebene Funktion mit den angegebenen Common Intermediate Language (CIL)-Zuordnungseinträgen fest.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorProfilerFunctionControl`-Schnittstelle stellt Methoden zum Steuern der Codegenerierung für eine einzelne neu kompilierte Funktion bereit. Der Profiler Ruft eine Instanz dieser Schnittstelle über den [ICorProfilerCallback4:: getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) -Rückruf ab. Jede Instanz von `ICorProfilerFunctionControl` steuert alle Instanzen einer Funktion.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [EnumJITedFunctions2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
