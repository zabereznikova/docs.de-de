---
title: CLR-Hostingschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: e6913e18a4ff6e616f357a4ef43fb8b892264943
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616839"
---
# <a name="clr-hosting-interfaces"></a>CLR-Hostingschnittstellen
In diesem Abschnitt werden die Schnittstellen beschrieben, mit denen nicht verwaltete Hosts die Common Language Runtime (CLR) in Ihre Anwendungen integrieren können. Die Informationen beziehen sich auf den .NET Framework Version 2,0 und höhere Versionen. Diese Schnittstellen ermöglichen es dem Host, viele weitere Aspekte der Laufzeit zu steuern, als dies in den Versionen 1,0 und 1,1 möglich war, und eine weitaus engere Integration zwischen der CLR und dem Ausführungs Modell des Hosts bereitzustellen.  
  
 In den .NET Framework, Version 1,0 und 1,1, ermöglichte das Hostingmodell einen nicht verwalteten Host, die CLR in einen Prozess zu laden, bestimmte Einstellungen zu konfigurieren und Ereignis Benachrichtigungen zu empfangen. Im allgemeinen wurden der Host und die CLR in diesem Prozess jedoch unabhängig ausgeführt. In der .NET Framework Version 2,0 und höheren Versionen ermöglichen neue Abstraktions Ebenen dem Host die Bereitstellung zahlreicher Ressourcen, die derzeit von den Typen in der Win32-Assembly bereitgestellt werden, und erweitern den Satz von Funktionen, die der Host konfigurieren kann.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [IActionOnCLREvent-Schnittstelle](iactiononclrevent-interface.md)  
 Stellt eine Methode bereit, die einen Rückruf für ein registriertes Ereignis ausführt.  
  
 [IApartmentCallback-Schnittstelle](iapartmentcallback-interface.md)  
 Stellt Methoden bereit, um Rückrufe in einem Apartment zu erstellen.  
  
 [IAppDomainBinding-Schnittstelle](iappdomainbinding-interface.md)  
 Stellt Methoden zum Festlegen der Laufzeitkonfiguration bereit.  
  
 [ICatalogServices-Schnittstelle](icatalogservices-interface.md)  
 Stellt Methoden für das Katalogisieren von Diensten bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)  
  
 [ICLRAssemblyIdentityManager-Schnittstelle](iclrassemblyidentitymanager-interface.md)  
 Stellt Methoden bereit, die die Kommunikation zwischen dem Host und der CLR über Assemblys unterstützen.  
  
 [ICLRAssemblyReferenceList-Schnittstelle](iclrassemblyreferencelist-interface.md)  
 Verwaltet eine Liste von Assemblys, die von der CLR und nicht vom Host geladen werden.  
  
 [ICLRControl-Schnittstelle](iclrcontrol-interface.md)  
 Stellt Methoden bereit, mit denen der Host auf die CLR zugreifen und verschiedene Aspekte konfigurieren kann.  
  
 [ICLRDebugManager-Schnittstelle](iclrdebugmanager-interface.md)  
 Stellt Methoden bereit, mit deren Hilfe einem Host eine Reihe von Tasks mit einem Bezeichner und einem anzeigen Amen verknüpft werden können.  
  
 [ICLRErrorReportingManager-Schnittstelle](iclrerrorreportingmanager-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, benutzerdefinierte Heap-Abbilder für die Fehlerberichterstattung zu konfigurieren.  
  
 [ICLRGCManager-Schnittstelle](iclrgcmanager-interface.md)  
 Stellt Methoden bereit, mit denen ein Host mit dem Garbage Collection System der CLR interagieren kann.  
  
 [ICLRHostBindingPolicyManager-Schnittstelle](iclrhostbindingpolicymanager-interface.md)  
 Stellt Methoden bereit, mit denen der Host Änderungen an Richtlinien Informationen für Assemblys auswerten und übermitteln können.  
  
 [ICLRHostProtectionManager-Schnittstelle](iclrhostprotectionmanager-interface.md)  
 Ermöglicht es dem Host, bestimmte verwaltete Klassen, Methoden, Eigenschaften und Felder von der Ausführung in teilweise vertrauenswürdigem Code zu blockieren.  
  
 [ICLRIoCompletionManager-Schnittstelle](iclriocompletionmanager-interface.md)  
 Implementiert eine Rückruf Methode, die es dem Host ermöglicht, die CLR über den Status der angegebenen e/a-Anforderungen zu benachrichtigen.  
  
 [ICLRMemoryNotificationCallback-Schnittstelle](iclrmemorynotificationcallback-interface.md)  
 Ermöglicht es dem Host, Speicher Auslastungs Bedingungen mithilfe eines ähnlichen Ansatzes wie der Win32-Funktion zu melden `CreateMemoryResourceNotification` .  
  
 [ICLROnEventManager-Schnittstelle](iclroneventmanager-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, Rückrufe für CLR-Ereignisse zu registrieren und die Registrierung aufzuheben.  
  
 [ICLRPolicyManager-Schnittstelle](iclrpolicymanager-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, Richtlinien Aktionen anzugeben, die im Fall von Fehlern und Timeouts durchgeführt werden sollen.  
  
 [ICLRProbingAssemblyEnum-Schnittstelle](iclrprobingassemblyenum-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, die in der CLR internen Identitätsinformationen der Assembly zu ermitteln, ohne diese Identität erstellen oder verstehen zu müssen.  
  
 [ICLRReferenceAssemblyEnum-Schnittstelle](iclrreferenceassemblyenum-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, den Satz von Assemblys, auf die von einer Datei oder einem Stream verwiesen wird, mithilfe von Assemblyidentitätsdaten zu bearbeiten, die für die CLR intern sind, ohne dass diese Identitäten  
  
 [ICLRRuntimeHost-Schnittstelle](iclrruntimehost-interface.md)  
 Bietet ähnliche Funktionen wie [ICorRuntimeHost](icorruntimehost-interface.md)mit einer zusätzlichen Methode zum Festlegen der Host Steuerungs Schnittstelle.  
  
 [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)  
 Stellt Methoden bereit, mit denen der Hostinformationen zu angeforderten Tasks und Deadlocks in der Synchronisierungs Implementierung erhält.  
  
 [ICLRTask-Schnittstelle](iclrtask-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, Anforderungen an die CLR zu senden oder die CLR über die zugeordnete Aufgabe benachrichtigt zu werden.  
  
 [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, explizit anzufordern, dass die CLR einen neuen Task erstellt, die aktuell ausgeführte Aufgabe erhält und die geografische Sprache und Kultur für den Task festgelegt.  
  
 [ICLRValidator-Schnittstelle](iclrvalidator-interface.md)  
 Stellt Methoden zum Überprüfen von PE-Images (portable ausführbare Dateien) und zum Melden von Validierungs Fehlern bereit.  
  
 [ICorConfiguration-Schnittstelle](icorconfiguration-interface.md)  
 Stellt Methoden zum Konfigurieren der CLR bereit.  
  
 [ICorThreadpool-Schnittstelle](icorthreadpool-interface.md)  
 Stellt Methoden für den Zugriff auf den Thread Pool bereit.  
  
 [IDebuggerInfo-Schnittstelle](idebuggerinfo-interface.md)  
 Stellt Methoden zum Abrufen von Informationen über den Zustand der Debugdienste bereit.  
  
 [IDebuggerThreadControl-Schnittstelle](idebuggerthreadcontrol-interface.md)  
 Stellt Methoden bereit, mit denen der Host über die Blockierung und Aufhebung der Blockierung von Threads durch die Debugdienste benachrichtigt wird.  
  
 [IGCHost-Schnittstelle](igchost-interface.md)  
 Bietet Methoden zum Abrufen von Informationen über das Garbage Collection System und zum Steuern einiger Aspekte von Garbage Collection.  
  
 [IGCHost2-Schnittstelle](igchost2-interface.md)  
 Stellt die [setgcstartuplimitsex](igchost2-setgcstartuplimitsex-method.md) -Methode bereit, die es einem Host ermöglicht, die Größe des Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems auf Werte größer als festzulegen `DWORD` .  
  
 [IGCHostControl-Schnittstelle](igchostcontrol-interface.md)  
 Stellt eine Methode bereit, die es dem Garbage Collector ermöglicht, den Host zum Ändern der Grenzwerte für den virtuellen Arbeitsspeicher anzufordern.  
  
 [IGCThreadControl-Schnittstelle](igcthreadcontrol-interface.md)  
 Stellt Methoden für die Teilnahme an der Planung von Threads bereit, die andernfalls für Garbage Collection blockiert werden.  
  
 [IHostAssemblyManager-Schnittstelle](ihostassemblymanager-interface.md)  
 Stellt Methoden bereit, mit denen ein Host Assemblys angeben kann, die von der CLR oder vom Host geladen werden sollen.  
  
 [IHostAssemblyStore-Schnittstelle](ihostassemblystore-interface.md)  
 Stellt Methoden bereit, mit denen ein Host Assemblys und Module unabhängig von der CLR laden kann.  
  
 [IHostAutoEvent-Schnittstelle](ihostautoevent-interface.md)  
 Stellt eine Darstellung eines vom Host implementierten automatischen Zurücksetzungs Ereignisses bereit.  
  
 [IHostControl-Schnittstelle](ihostcontrol-interface.md)  
 Bietet Methoden zum Konfigurieren des Ladens von Assemblys und zum bestimmen, welche Hostingschnittstellen der Host unterstützt.  
  
 [IHostCrst-Schnittstelle](ihostcrst-interface.md)  
 Dient als Host Darstellung eines kritischen Abschnitts zum Threading.  
  
 [IHostGCManager-Schnittstelle](ihostgcmanager-interface.md)  
 Stellt Methoden bereit, die den Host von Ereignissen in der von der CLR implementierten Garbage Collection Mechanismus benachrichtigen.  
  
 [IHostIoCompletionManager-Schnittstelle](ihostiocompletionmanager-interface.md)  
 Stellt Methoden bereit, mit denen die CLR mit e/a-Abschlussports interagieren kann, die vom Host bereitgestellt werden.  
  
 [IHostMalloc-Schnittstelle](ihostmalloc-interface.md)  
 Stellt Methoden für die CLR bereit, um differenzierte Zuordnungen vom Heap über den Host anzufordern.  
  
 [IHostManualEvent-Schnittstelle](ihostmanualevent-interface.md)  
 Stellt die Implementierung eines Hosts für ein manuelles Zurücksetzungs Ereignis bereit.  
  
 [IHostMemoryManager-Schnittstelle](ihostmemorymanager-interface.md)  
 Stellt Methoden für die CLR bereit, um virtuelle Speicheranforderungen über den Host zu erstellen, statt die standardmäßigen Win32-Funktionen für den virtuellen Arbeitsspeicher zu verwenden.  
  
 [IHostPolicyManager-Schnittstelle](ihostpolicymanager-interface.md)  
 Stellt Methoden bereit, die den Host über die Aktionen Benachrichtigen, die die CLR im Falle von Abbrüche, Timeouts oder Fehlern ausführt.  
  
 [IHostSecurityContext-Schnittstelle](ihostsecuritycontext-interface.md)  
 Ermöglicht der CLR die Verwaltung von Sicherheitskontext Informationen, die vom Host implementiert werden.  
  
 [IHostSecurityManager-Schnittstelle](ihostsecuritymanager-interface.md)  
 Stellt Methoden bereit, die den Zugriff auf den Sicherheitskontext des aktuell ausgeführten Threads ermöglichen und dessen Steuerung ermöglichen.  
  
 [IHostSemaphore-Schnittstelle](ihostsemaphore-interface.md)  
 Stellt eine Darstellung eines Semaphors bereit, der vom Host implementiert wird.  
  
 [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)  
 Stellt Methoden für die CLR bereit, um Synchronisierungs primitive durch Aufrufen des Hosts zu erstellen, statt die Win32-Synchronisierungs Funktionen zu verwenden.  
  
 [IHostTask-Schnittstelle](ihosttask-interface.md)  
 Stellt Methoden bereit, mit denen die CLR mit dem Host kommunizieren kann, um Aufgaben zu verwalten.  
  
 [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)  
 Stellt Methoden bereit, mit denen die CLR mit Aufgaben über den Host arbeiten kann, anstatt die Threading-oder Fiber-Funktionen des Standard Betriebssystems zu verwenden.  
  
 [IHostThreadPoolManager-Schnittstelle](ihostthreadpoolmanager-interface.md)  
 Stellt Methoden für die CLR bereit, um den Thread Pool zu konfigurieren und Arbeitselemente in die Warteschlange des Thread Pools zu übermitteln.  
  
 [IManagedObject-Schnittstelle](imanagedobject-interface.md)  
 Stellt Methoden zum Steuern eines verwalteten Objekts bereit.  
  
 IObjectHandle  
 Stellt eine Methode zum Entpacken von Marshal-by-Value-Objekten aus der Dereferenzierung bereit.  
  
 [ITypeName-Schnittstelle](itypename-interface.md)  
 Stellt Methoden zum Abrufen von Informationen zum Typnamen bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)  
  
 [ITypeNameBuilder-Schnittstelle](itypenamebuilder-interface.md)  
 Stellt Methoden zum Entwickeln eines Typnamens bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)  
  
 [ITypeNameFactory-Schnittstelle](itypenamefactory-interface.md)  
 Stellt Methoden zum dekonstruieren eines Typnamens bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)  
  
 IValidator  
 Stellt Methoden zum Überprüfen von PE-Images (portable ausführbare Dateien) und zum Melden von Validierungs Fehlern bereit.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Veraltete CLR-Hostingschnittstellen und Co-Klassen](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Enthält Themen, in denen die Hostingschnittstellen in den .NET Framework Version 1,0 und 1,1 beschrieben werden.  
  
 [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 Enthält Themen, in denen die Hostingschnittstellen in den .NET Framework 4 beschrieben werden.
