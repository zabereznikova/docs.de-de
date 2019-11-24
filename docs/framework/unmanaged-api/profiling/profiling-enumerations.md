---
title: Profilerstellungsenumerationen
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: bc90743fb348c31bd2f7487c1573ec38a43bd3af
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447450"
---
# <a name="profiling-enumerations"></a>Profilerstellungsenumerationen
Dieser Abschnitt beschreibt die nicht verwalteten Enumerationen, die die Profilerstellungs-API verwendet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [COR_PRF_CLAUSE_TYPE-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)  
 Zeigt den Typ der Ausnahmeklausel an, die der Code gerade eben eingegeben oder zurückgelassen hat.  
  
 [COR_PRF_CODEGEN_FLAGS-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)  
 Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.  
  
 [COR_PRF_FINALIZER_FLAGS-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md)  
 Beschreibt den Finalizer für ein Objekt.  
  
 [COR_PRF_GC_GENERATION-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)  
 Identifiziert die Erstellung der Garbage Collection.  
  
 [COR_PRF_GC_REASON-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)  
 Zeigt den Grund, weshalb die Garbage Collection stattfindet.  
  
 [COR_PRF_GC_ROOT_FLAGS-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md)  
 Zeigt die Eigenschaften eines Garbage Collector-Stamms.  
  
 [COR_PRF_GC_ROOT_KIND-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md)  
 Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.  
  
 [COR_PRF_HIGH_MONITOR-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)  
 Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.  
  
 [COR_PRF_JIT_CACHE-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md)  
 Zeigt das Ergebnis einer zwischengespeicherten Funktionssuche.  
  
 [COR_PRF_MISC-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-misc-enumeration.md)  
 Enthält Konstantenwerte, die spezielle Bezeichner angeben.  
  
 [COR_PRF_MODULE_FLAGS-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md)  
 Gibt die Eigenschaften eines Moduls an.  
  
 [COR_PRF_MONITOR-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 Enthält Werte, die zum Angeben von Verhalten, Funktionen oder Ereignissen verwendet werden, die der Profiler abonnieren muss.  
  
 [COR_PRF_RUNTIME_TYPE-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-runtime-type-enumeration.md)  
 Enthält Werte, die die Version der Common Language Runtime angeben.  
  
 [COR_PRF_SNAPSHOT_INFO-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)  
 Gibt an, wie viele Daten in jedem Aufruf an die `StackSnapshotCallback`-Funktion des Profilers an eine Stapelmomentaufnahmeme zurückgegeben werden.  
  
 [COR_PRF_STATIC_TYPE-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)  
 Zeigt an, ob ein Feld statisch ist und, falls dies der Fall ist, ob die statische Qualität für das Feld gilt.  
  
 [COR_PRF_SUSPEND_REASON-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)  
 Zeigt den Grund an, aus dem die Laufzeit angehalten wurde.  
  
 [COR_PRF_TRANSITION_REASON-Enumeration](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)  
 Zeigt den Grund für einen Übergang von verwaltetem zu nicht verwaltetem Code an oder umgekehrt.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Übersicht über die Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [Profilerstellungsstrukturen](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
