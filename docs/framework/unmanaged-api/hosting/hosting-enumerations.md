---
title: Hosten von Enumerationen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged enumerations [.NET Framework], hosting
- enumerations [.NET Framework hosting]
- hosting enumerations [.NET Framework]
ms.assetid: e09131eb-1f7d-4f52-ae42-7393e9b62ef6
ms.openlocfilehash: 907b1343ddbfa28b97ac2210e28b99cd38aa6fd4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721828"
---
# <a name="hosting-enumerations"></a>Hosten von Enumerationen

In diesem Abschnitt werden die nicht verwalteten Enumerationen beschrieben, die von der Hosting-API verwendet werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [CLSID_RESOLUTION_FLAGS-Enumeration](clsid-resolution-flags-enumeration.md)  
 Enthält Werte, die angeben, wie die Common Language Runtime (CLR) eine auflösen soll `CLSID` .  
  
 [COR_GC_STAT_TYPES-Enumeration](cor-gc-stat-types-enumeration.md)  
 Gibt die Statistiken an, die für eine Garbage Collection aufgezeichnet werden sollen.  
  
 [COR_GC_THREAD_STATS_TYPES-Enumeration](cor-gc-thread-stats-types-enumeration.md)  
 Gibt die Garbage Collection Statistiken für einen Thread an.  
  
 [EApiCategories-Enumeration](eapicategories-enumeration.md)  
 Beschreibt die Kategorien von Funktionen, die der Host für die Ausführung in teilweise vertrauenswürdigem Code blockieren kann.  
  
 [EBindPolicyLevels-Enumeration](ebindpolicylevels-enumeration.md)  
 Stellt Flags bereit, die die Ebene angeben, auf der die Assemblyrichtlinie angewendet oder geändert werden soll.  
  
 [ECLRAssemblyIdentityFlags-Enumeration](eclrassemblyidentityflags-enumeration.md)  
 Gibt den Typ der Identität einer Assembly an.  
  
 [EClrEvent-Enumeration](eclrevent-enumeration.md)  
 Beschreibt die CLR-Ereignisse, für die der Host Rückrufe registrieren kann.  
  
 [EClrFailure-Enumeration](eclrfailure-enumeration.md)  
 Beschreibt den Satz von Fehlern, bei denen ein Host Richtlinien Aktionen festlegen kann.  
  
 [EClrOperation-Enumeration](eclroperation-enumeration.md)  
 Beschreibt den Satz von Vorgängen, für die ein Host Richtlinien Aktionen anwenden kann.  
  
 [EClrUnhandledException-Enumeration](eclrunhandledexception-enumeration.md)  
 Beschreibt die verfügbaren Optionen zum Verwalten von Ausnahmen, die im Benutzercode nicht behandelt werden.  
  
 [EContextType-Enumeration](econtexttype-enumeration.md)  
 Beschreibt den Sicherheitskontext des aktuell ausgeführten Threads.  
  
 [ECustomDumpFlavor-Enumeration](ecustomdumpflavor-enumeration.md)  
 Enthält Werte, die angeben, welche Elemente in eine benutzerdefinierte Teilmenge eines Heap Abbilds eingeschlossen werden sollen, wenn Fehler gemeldet werden.  
  
 [ECustomDumpItemKind-Enumeration](ecustomdumpitemkind-enumeration.md)  
 Reserviert für zukünftige Erweiterungen der [CustomDumpItem-Struktur](customdumpitem-structure.md) Struktur.  
  
 [EHostApplicationPolicy-Enumeration](ehostapplicationpolicy-enumeration.md)  
 Gibt an, wie ein [IHostAssemblyManager-Schnittstellen](ihostassemblymanager-interface.md) Schnittstellen Objekt geändert wird. Diese Enumeration ist veraltet.  
  
 [EHostBindingPolicyModifyFlags-Enumeration](ehostbindingpolicymodifyflags-enumeration.md)  
 Ermöglicht dem Host, den Umleitungstyp anzugeben, der von der CLR beim Anwenden von Richtlinien Änderungen von einer Quellassembly auf eine Zielassembly durchgeführt werden soll.  
  
 [EInitializeNewDomainFlags-Enumeration](einitializenewdomainflags-enumeration.md)  
 Ermöglicht dem Host, der Laufzeit Informationen zur Initialisierung einer Anwendungsdomäne bereitzustellen.  
  
 [EMemoryAvailable-Enumeration](ememoryavailable-enumeration.md)  
 Enthält Werte, die angeben, wie viel freier physischer Speicher auf dem Computer vorhanden ist.  
  
 [EMemoryCriticalLevel-Enumeration](ememorycriticallevel-enumeration.md)  
 Enthält Werte, die die Auswirkung eines Fehlers angeben, wenn eine bestimmte Speicher Belegung angefordert wurde, jedoch nicht erfüllt werden kann.  
  
 [EPolicyAction-Enumeration](epolicyaction-enumeration.md)  
 Beschreibt die Richtlinien Aktionen, die der Host für durch die [EClrOperation-Enumeration](eclroperation-enumeration.md) beschriebene Vorgänge und durch die [EClrFailure-Enumeration](eclrfailure-enumeration.md)beschriebene Fehler festlegen kann.  
  
 [ESymbolReadingPolicy-Enumeration](esymbolreadingpolicy-enumeration.md)  
 Enthält Werte, mit denen die Richtlinie zum Lesen von Programm Datenbankdateien (PDB) festgelegt wird.  
  
 [ETaskType-Enumeration](etasktype-enumeration.md)  
 Enthält Werte, die die Art der Aufgabe angeben, die durch eine [ICLRTask-Schnittstelle](iclrtask-interface.md) oder eine [IHostTask-Schnitt](ihosttask-interface.md) Stelle dargestellt wird.  
  
 [HOST_TYPE-Enumeration](host-type-enumeration.md)  
 Enthält Werte, die den Typ des Hosts angeben, von dem eine Anwendung gestartet wird.  
  
 [MALLOC_TYPE-Enumeration](malloc-type-enumeration.md)  
 Enthält Werte, die die Merkmale des zugeordneten Arbeitsspeichers angeben.  
  
 [METAHOST_CONFIG_FLAGS-Enumeration](metahost-config-flags-enumeration.md)  
 Beschreibt die möglichen Flags, die im- `pdwConfigFlags` Parameter der [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) -Methode zurückgegeben werden.  
  
 [METAHOST_POLICY_FLAGS-Enumeration](metahost-policy-flags-enumeration.md)  
 Stellt Bindungs Richtlinien bereit, die den meisten Lauf Zeit Hosts gemeinsam sind.  
  
 [RUNTIME_INFO_FLAGS-Enumeration](runtime-info-flags-enumeration.md)  
 Enthält Werte, die angeben, welche Informationen über die CLR zurückgegeben werden sollen.  
  
 [StackOverflowType-Enumeration](stackoverflowtype-enumeration.md)  
 Enthält Werte, die die zugrunde liegende Ursache eines Stapelüberlauf Ereignisses angeben.  
  
 [STARTUP_FLAGS-Enumeration](startup-flags-enumeration.md)  
 Enthält Werte, die das Startverhalten der CLR angeben.  
  
 [ValidatorFlags-Enumeration](validatorflags-enumeration.md)  
 Enthält Werte, die den Validierungstyp angeben, der in einem Befehl zur [Validate-Methode](iclrvalidator-validate-method.md)ausgeführt werden soll.  
  
 [WAIT_OPTION-Enumeration](wait-option-enumeration.md)  
 Gibt die Aktion an, die ein Host bei einem von den CLR-Blöcken angeforderten Vorgang ausführen soll.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Hosten von Co-Klassen](hosting-coclasses.md)  
  
 [Hosten von Schnittstellen](hosting-interfaces.md)  
  
 [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)  
  
 [Hosten von Strukturen](hosting-structures.md)
