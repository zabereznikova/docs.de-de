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
ms.openlocfilehash: 2d7984ce109fb2bac5a36ab5e4c83f386de5a488
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867099"
---
# <a name="cor_prf_monitor-enumeration"></a>COR_PRF_MONITOR-Enumeration
Enthält Werte, die zum Angeben von Verhalten, Funktionen oder Ereignissen verwendet werden, die der Profiler abonnieren muss.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 In den folgenden Abschnitten werden `COR_PRF_MONITOR` Enumerationsmember nach Kategorie aufgelistet. Die Kategorien lauten:  
  
- [Keine Flags festgelegt.](#None)  
  
- [Rückruf-Flags](#Callback)  
  
- [Funktionsaktivierungsflags](#Feature)  
  
- [Konfigurationsflags](#Config)  
  
- [Zusammengesetzte Flags](#Composite)  
  
<a name="None"></a>   
### <a name="no-flags-set"></a>Keine Flags festgelegt.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|Es sind keine Flags festgelegt.|  
  
<a name="Callback"></a>   
### <a name="callback-flags"></a>Rückruf-Flags  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|Aktiviert alle Rückrufereignisse.|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|Steuert die `AppDomainCreation*` und `AppDomainShutdown*` Rückrufe in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|Steuert die `AssemblyLoad*` und `AssemblyUnload*` Rückrufe in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|Steuert die `JITCachedFunctionSearch*` Rückrufe in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.<br /><br /> Das Verhalten dieses Flags ändert sich in Version 2.0 von .NET Framework.|  
|`COR_PRF_MONITOR_CCW`|Steuert die `COMClassicVTable*` Rückrufe in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_CLASS_LOADS`|Steuert die `ClassLoad*` und `ClassUnload*` Rückrufe in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|Steuert die `ExceptionCLRCatcher*` Rückrufe in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|Steuert die Rückrufe [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) und [ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_ENTERLEAVE`|Steuert die `FunctionEnter*`-, `FunctionLeave*`-und `FunctionTailCall*`[Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md).|  
|`COR_PRF_MONITOR_EXCEPTIONS`|Steuert den [exceptiondent](icorprofilercallback-exceptionthrown-method.md) -Rückruf und die `ExceptionSearch*`-, `ExceptionOSHandler*`-, `ExceptionUnwind*`-und `ExceptionCatcher*` Rückrufe in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|Steuert den [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) -Rückruf in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_GC`|Steuert die Rückrufe [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionfinished-method.md), [muvedreferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md), [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md), [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md), [objectsallogatedbyclass](icorprofilercallback-objectsallocatedbyclass-method.md), [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [gscreated](icorprofilercallback2-handlecreated-method.md), [lenzerstört](icorprofilercallback2-handledestroyed-method.md)und [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) in den `ICorProfilerCallback*`-Schnittstellen. Wenn `COR_PRF_MONITOR_GC` zugeordnet ist, wird die gleichzeitige Garbage Collection deaktiviert.|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|Steuert die Rückrufe `JITCompilation*`, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md)und [JITInlining](icorprofilercallback-jitinlining-method.md) in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_MODULE_LOADS`|Steuert die Rückrufe `ModuleLoad*`, `ModuleUnload*`und [moduleattachedonassembly](icorprofilercallback-moduleattachedtoassembly-method.md) in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|Steuert den [ObjectAllocated](icorprofilercallback-objectallocated-method.md) -Rückruf in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_REMOTING`|Steuert die `Remoting*` Rückrufe in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|Steuert, ob die `Remoting*`-Rückrufe asynchrone Ereignisse überwachen.|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|Steuert, ob ein Cookie an `Remoting*`-Rückrufe übergeben wird.|  
|`COR_PRF_MONITOR_SUSPENDS`|Steuert die Rückrufe `RuntimeSuspend*`, `RuntimeResume*`, [runtimethleseangeh](icorprofilercallback-runtimethreadsuspended-method.md)alten und [runtimethread](icorprofilercallback-runtimethreadresumed-method.md) fortsetzen in der [ICorProfilerCallback](icorprofilercallback-interface.md) -Schnittstelle.|  
|`COR_PRF_MONITOR_THREADS`|Steuert die Rückrufe [ThreadCreated](icorprofilercallback-threadcreated-method.md), [threadzerstört](icorprofilercallback-threaddestroyed-method.md), [threadassigneddeosthread](icorprofilercallback-threadassignedtoosthread-method.md)und [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) in den [ICorProfilerCallback](icorprofilercallback-interface.md) -und [ICorProfilerCallback2](icorprofilercallback2-interface.md) -Schnittstellen.|  
  
<a name="Feature"></a>   
### <a name="feature-enabling-flags"></a>Flags zur Aktivierung von Funktionen  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|Ermöglicht das Abrufen eines exakten `ClassID` für eine generische Funktion durch Aufrufen der [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) -Methode mit einem `COR_PRF_FRAME_INFO` Wert, der vom [FunctionEnter2](functionenter2-function.md) -Rückruf zurückgegeben wird.|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|Aktiviert die Argument Ablauf Verfolgung mit dem [FunctionEnter2](functionenter2-function.md) -Rückruf oder dem [FunctionEnter3WithInfo](functionenter3withinfo-function.md) -Rückruf und der [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) -Methode.|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|Ermöglicht die Ablauf Verfolgung von Rückgabe Werten mit dem [FunctionLeave2](functionleave2-function.md) -Rückruf oder dem [FunctionLeave3WithInfo](functionleave3withinfo-function.md) -Rückruf und der [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) -Methode.|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|Veraltet.<br /><br /> Prozessinternes Debuggen wird nicht unterstützt. Dieses Flag hat keine Wirkung.|  
|`COR_PRF_ENABLE_JIT_MAPS`|Veraltet.<br /><br /> Ermöglicht dem Profiler das Abrufen von Il-to-Native-Zuordnungen mithilfe von [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md). In .NET Framework, Version 2.0 werden Zuordnungen zwischen IL-Code und systemeigenem Code von der CLR immer nachverfolgt, daher gilt dieses Flag immer als gesetzt.|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|Teilt der CLR mit, dass der Profiler u. U. über Objektzuordnungen benachrichtigt werden soll. Dies muss während der Initialisierung festgelegt werden. Dies ermöglicht es dem Profiler, das `COR_PRF_MONITOR_OBJECT_ALLOCATED`-Flag zu verwenden, um [objectallokalisierte](icorprofilercallback-objectallocated-method.md) Rückrufe zu empfangen.|  
|`COR_PRF_ENABLE_REJIT`|Aktiviert Aufrufe der Methoden [requestrejit](icorprofilerinfo4-requestrejit-method.md) und [requestrevert](icorprofilerinfo4-requestrevert-method.md) . Der Profiler muss dieses Flag beim Start festlegen.  Wenn der Profiler dieses Flag angibt, muss er auch `COR_PRF_DISABLE_ALL_NGEN_IMAGES` angeben.|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|Aktiviert Aufrufe der [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode.|  
  
<a name="Config"></a>   
### <a name="configuration-flags"></a>Konfigurationsflags  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|Bewirkt, dass die systemeigene Abbildsuche nach Abbildern (einschließlich durch Profiler verbesserte) sucht.  Wenn dieses Flag und das `COR_PRF_USE_PROFILE_IMAGES`-Flag beide angegeben sind, wird `COR_PRF_DISABLE_ALL_NGEN_IMAGES` verwendet.|  
|`COR_PRF_DISABLE_INLINING`|Deaktiviert das gesamte Inlining.|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|Deaktiviert alle Codeoptimierungen.|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|Deaktiviert Sicherheitstransparenzprüfungen, die normalerweise während Just-In-Time (JIT)-Kompilierungen und dem Laden von Klassen für vollständig vertrauenswürdige Assemblys durchgeführt werden. Dies kann die Ausführung einiger Instrumentierungsvorgänge erleichtern.|  
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
 Ein `COR_PRF_MONITOR` Wert wird zusammen mit der [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) -Methode und der [ICorProfilerInfo:: lteventmask](icorprofilerinfo-seteventmask-method.md) -Methode verwendet, um die Ereignis Benachrichtigungen zu definieren, die die Common Language Runtime an den Profiler vornimmt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsenumerationen](profiling-enumerations.md)
- [GetEventMask-Methode](icorprofilerinfo-geteventmask-method.md)
- [SetEventMask-Methode](icorprofilerinfo-seteventmask-method.md)
