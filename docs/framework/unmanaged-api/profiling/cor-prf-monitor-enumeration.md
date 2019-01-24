---
title: COR_PRF_MONITOR-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a07442d990694099c9402989b41c937360842316
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569874"
---
# <a name="corprfmonitor-enumeration"></a>COR_PRF_MONITOR-Enumeration
Enthält Werte, die zur Angabe von Verhalten, Funktionen oder Ereignissen verwendet werden, die der Profiler abonnieren möchte.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |   
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |   
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a>Member  
 Den folgenden Abschnitten `COR_PRF_MONITOR` Enumerationsmember nach Kategorie. Die Kategorien sind:  
  
-   [Keine Flags festgelegt](#None)  
  
-   [Rückruf-flags](#Callback)  
  
-   [Flags zur Aktivierung von Feature](#Feature)  
  
-   [Konfigurationsflags](#Config)  
  
-   [Kombinierte flags](#Composite)  
  
<a name="None"></a>   
### <a name="no-flags-set"></a>Keine Flags festgelegt  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|Es sind keine Flags festgelegt.|  
  
<a name="Callback"></a>   
### <a name="callback-flags"></a>Rückruf-Flags  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|Aktiviert alle Rückrufereignisse.|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|Steuerelemente der `AppDomainCreation*` und `AppDomainShutdown*` Rückrufe in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|Steuerelemente der `AssemblyLoad*` und `AssemblyUnload*` Rückrufe in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|Steuerelemente der `JITCachedFunctionSearch*` Rückrufe in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.<br /><br /> Das Verhalten dieses Flags ändert sich in Version 2.0 von .NET Framework.|  
|`COR_PRF_MONITOR_CCW`|Steuerelemente der `COMClassicVTable*` Rückrufe in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.|  
|`COR_PRF_MONITOR_CLASS_LOADS`|Steuerelemente der `ClassLoad*` und `ClassUnload*` Rückrufe in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|Steuerelemente der `ExceptionCLRCatcher*` Rückrufe in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|Steuerelemente der [UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) und [ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) Rückrufe in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle|  
|`COR_PRF_MONITOR_ENTERLEAVE`|Steuerelemente der `FunctionEnter*`, `FunctionLeave*`, und `FunctionTailCall*` [profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md).|  
|`COR_PRF_MONITOR_EXCEPTIONS`|Steuerelemente der [ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md) Rückruf und den `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, und `ExceptionCatcher*` Rückrufe in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|Steuerelemente der [FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md) Rückruf in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.|  
|`COR_PRF_MONITOR_GC`|Steuerelemente der [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md), [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md), [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md), [ SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md), [SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md), [ RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md), [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md), [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md), und [FinalizeableObjectQueued ](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) Rückrufe in die `ICorProfilerCallback*` Schnittstellen.|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|Steuerelemente der `JITCompilation*`, [JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md), und [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) Rückrufe in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.|  
|`COR_PRF_MONITOR_MODULE_LOADS`|Steuerelemente der `ModuleLoad*`, `ModuleUnload*`, und [ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) Rückrufe in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|Steuerelemente der [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) Rückruf in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.|  
|`COR_PRF_MONITOR_REMOTING`|Steuerelemente der `Remoting*` Rückrufe in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|Steuert, ob die `Remoting*`-Rückrufe asynchrone Ereignisse überwachen.|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|Steuert, ob ein Cookie an `Remoting*`-Rückrufe übergeben wird.|  
|`COR_PRF_MONITOR_SUSPENDS`|Steuerelemente der `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md), und [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md) Rückrufe in die [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) Schnittstelle.|  
|`COR_PRF_MONITOR_THREADS`|Steuerelemente der [ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md), [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md), [ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md), und [ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md) Rückrufe in der [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) und [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) Schnittstellen.|  
  
<a name="Feature"></a>   
### <a name="feature-enabling-flags"></a>Flags zur Aktivierung von Funktionen  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|Ermöglicht das Abrufen einer genauen `ClassID` für eine generische Funktion durch Aufrufen der [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) -Methode mit einem `COR_PRF_FRAME_INFO` Rückgabewert von der [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) Rückruf.|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|Ermöglicht mit der [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) Rückruf oder [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) Rückruf und den [GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) Methode.|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|Ermöglicht die Verfolgung von Werten mit der [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) Rückruf oder [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) Rückruf und [GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) Methode.|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|Veraltet.<br /><br /> Prozessinternes Debuggen wird nicht unterstützt. Dieses Flag hat keine Wirkung.|  
|`COR_PRF_ENABLE_JIT_MAPS`|Veraltet.<br /><br /> Ermöglicht es dem Profiler zum Abrufen von IL-Code und systemeigenem Zuordnungen mit [GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md). In .NET Framework, Version 2.0 werden Zuordnungen zwischen IL-Code und systemeigenem Code von der CLR immer nachverfolgt, daher gilt dieses Flag immer als gesetzt.|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|Teilt der CLR mit, dass der Profiler u. U. über Objektzuordnungen benachrichtigt werden soll. Dies muss während der Initialisierung festgelegt werden. Kann der Profiler anschließend verwendet der `COR_PRF_MONITOR_OBJECT_ALLOCATED` Flag zum Empfangen von [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) Rückrufe.|  
|`COR_PRF_ENABLE_REJIT`|Aktiviert Aufrufe der [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) und [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) Methoden. Der Profiler muss dieses Flag beim Start festlegen.  Wenn der Profiler dieses Flag angibt, muss er auch `COR_PRF_DISABLE_ALL_NGEN_IMAGES` angeben.|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|Aktiviert Aufrufe der [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) Methode.|  
  
<a name="Config"></a>   
### <a name="configuration-flags"></a>Konfigurationsflags  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|Bewirkt, dass die systemeigene Abbildsuche nach Abbildern (einschließlich durch Profiler verbesserte) sucht.  Wenn dieses Flag und das `COR_PRF_USE_PROFILE_IMAGES`-Flag beide angegeben sind, wird `COR_PRF_DISABLE_ALL_NGEN_IMAGES` verwendet.|  
|`COR_PRF_DISABLE_INLINING`|Deaktiviert das gesamte Inlining.|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|Deaktiviert alle Codeoptimierungen.|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|Deaktiviert Sicherheitstransparenzprüfungen, die normalerweise während Just-In-Time (JIT)-Kompilierungen und dem Laden von Klassen für vollständig vertrauenswürdige Assemblys durchgeführt werden. Dies kann die Ausführung einiger Instrumentationsvorgänge erleichtern.|  
|`COR_PRF_USE_PROFILE_IMAGES`|Bewirkt, dass die systemeigene Abbildsuche nach durch Profiler verbesserten Abbildern sucht. Wenn für eine Assembly kein durch Profiler verbessertes Bild gefunden wird, greift die Common Language Runtime für die betreffende Assembly wieder auf JIT zurück. Wenn dieses Flag und das `COR_PRF_DISABLE_ALL_NGEN_IMAGES`-Flag beide angegeben sind, wird `COR_PRF_DISABLE_ALL_NGEN_IMAGES` verwendet.|  
  
<a name="Composite"></a>   
### <a name="composite-flags"></a>Kombinierte Flags  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_ALL`|Stellt alle `COR_PRF_MONITOR`-Flagwerte dar.|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|Stellt alle `COR_PRF_MONITOR`-Flags dar, die festgelegt werden können, wenn der Profiler mit einer ausgeführten App verknüpft wurde. Der Syntaxabschnitt gibt die einzelnen Flags an, die in dieser Bitmask vorhanden sind.|  
|`COR_PRF_MONITOR_ALL`|Aktiviert alle Rückrufereignisse.|  
|`COR_PRF_MONITOR_IMMUTABLE`|Stellt alle `COR_PRF_MONITOR`-Flags dar, die nur während der Initialisierung festgelegt werden können. Wenn Sie versuchen, eines dieser Flags nach der Initialisierung zu ändern, führt dies zu einem `HRESULT`-Wert, der auf einen Fehler hinweist.|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|Stellt alle `COR_PRF_MONITOR`-Flags dar, die durch Profiler verbesserte Bilder erfordern.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `COR_PRF_MONITOR` Wert wird verwendet, mit der [ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) und [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methoden, um die ereignisbenachrichtigungen zu definieren, die die common Language Runtime stellt der Profiler.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [GetEventMask-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)
- [SetEventMask-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)
