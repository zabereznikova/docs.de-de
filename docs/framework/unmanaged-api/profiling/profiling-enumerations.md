---
title: Profilerstellungsenumerationen
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: 1a9781fa1b4b608152faa7d5edc80bd4866f0c81
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868134"
---
# <a name="profiling-enumerations"></a>Profilerstellungsenumerationen
Dieser Abschnitt beschreibt die nicht verwalteten Enumerationen, die die Profilerstellungs-API verwendet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [COR_PRF_CLAUSE_TYPE-Enumeration](cor-prf-clause-type-enumeration.md)  
 Zeigt den Typ der Ausnahmeklausel an, die der Code gerade eben eingegeben oder zurückgelassen hat.  
  
 [COR_PRF_CODEGEN_FLAGS-Enumeration](cor-prf-codegen-flags-enumeration.md)  
 Definiert die Codegenerierungs-Flags, die mit der [icorprofilerfunctioncontrol:: setcodegenflags](icorprofilerfunctioncontrol-setcodegenflags-method.md) -Methode festgelegt werden können.  
  
 [COR_PRF_FINALIZER_FLAGS-Enumeration](cor-prf-finalizer-flags-enumeration.md)  
 Beschreibt den Finalizer für ein Objekt.  
  
 [COR_PRF_GC_GENERATION-Enumeration](cor-prf-gc-generation-enumeration.md)  
 Identifiziert die Erstellung der Garbage Collection.  
  
 [COR_PRF_GC_REASON-Enumeration](cor-prf-gc-reason-enumeration.md)  
 Zeigt den Grund, weshalb die Garbage Collection stattfindet.  
  
 [COR_PRF_GC_ROOT_FLAGS-Enumeration](cor-prf-gc-root-flags-enumeration.md)  
 Zeigt die Eigenschaften eines Garbage Collector-Stamms.  
  
 [COR_PRF_GC_ROOT_KIND-Enumeration](cor-prf-gc-root-kind-enumeration.md)  
 Gibt die Art des Garbage Collector Stamms an, der durch den Rückruf " [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) " verfügbar gemacht wird.  
  
 [COR_PRF_HIGH_MONITOR-Enumeration](cor-prf-high-monitor-enumeration.md)  
 Bietet zusätzlich zu den in der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) Enumeration gefundenen Flags, die der Profiler beim Laden an die [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) -Methode angeben kann.  
  
 [COR_PRF_JIT_CACHE-Enumeration](cor-prf-jit-cache-enumeration.md)  
 Zeigt das Ergebnis einer zwischengespeicherten Funktionssuche.  
  
 [COR_PRF_MISC-Enumeration](cor-prf-misc-enumeration.md)  
 Enthält Konstantenwerte, die spezielle Bezeichner angeben.  
  
 [COR_PRF_MODULE_FLAGS-Enumeration](cor-prf-module-flags-enumeration.md)  
 Gibt die Eigenschaften eines Moduls an.  
  
 [COR_PRF_MONITOR-Enumeration](cor-prf-monitor-enumeration.md)  
 Enthält Werte, die zum Angeben von Verhalten, Funktionen oder Ereignissen verwendet werden, die der Profiler abonnieren muss.  
  
 [COR_PRF_RUNTIME_TYPE-Enumeration](cor-prf-runtime-type-enumeration.md)  
 Enthält Werte, die die Version der Common Language Runtime angeben.  
  
 [COR_PRF_SNAPSHOT_INFO-Enumeration](cor-prf-snapshot-info-enumeration.md)  
 Gibt an, wie viele Daten in jedem Aufruf an die `StackSnapshotCallback`-Funktion des Profilers an eine Stapelmomentaufnahmeme zurückgegeben werden.  
  
 [COR_PRF_STATIC_TYPE-Enumeration](cor-prf-static-type-enumeration.md)  
 Zeigt an, ob ein Feld statisch ist und, falls dies der Fall ist, ob die statische Qualität für das Feld gilt.  
  
 [COR_PRF_SUSPEND_REASON-Enumeration](cor-prf-suspend-reason-enumeration.md)  
 Zeigt den Grund an, aus dem die Laufzeit angehalten wurde.  
  
 [COR_PRF_TRANSITION_REASON-Enumeration](cor-prf-transition-reason-enumeration.md)  
 Zeigt den Grund für einen Übergang von verwaltetem zu nicht verwaltetem Code an oder umgekehrt.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Übersicht über die Profilerstellung](profiling-overview.md)  
  
 [Profilerstellungsschnittstellen](profiling-interfaces.md)  
  
 [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)  
  
 [Profilerstellungsstrukturen](profiling-structures.md)
