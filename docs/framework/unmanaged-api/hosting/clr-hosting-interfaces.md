---
title: CLR-Hostingschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: 66fdd97d101f5ea53a96b996a2a60e5ed65a2701
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131966"
---
# <a name="clr-hosting-interfaces"></a>CLR-Hostingschnittstellen
In diesem Abschnitt werden die Schnittstellen beschrieben, mit denen nicht verwaltete Hosts die Common Language Runtime (CLR) in Ihre Anwendungen integrieren können. Die Informationen beziehen sich auf den .NET Framework Version 2,0 und höhere Versionen. Diese Schnittstellen ermöglichen es dem Host, viele weitere Aspekte der Laufzeit zu steuern, als dies in den Versionen 1,0 und 1,1 möglich war, und eine weitaus engere Integration zwischen der CLR und dem Ausführungs Modell des Hosts bereitzustellen.  
  
 In den .NET Framework, Version 1,0 und 1,1, ermöglichte das Hostingmodell einen nicht verwalteten Host, die CLR in einen Prozess zu laden, bestimmte Einstellungen zu konfigurieren und Ereignis Benachrichtigungen zu empfangen. Im allgemeinen wurden der Host und die CLR in diesem Prozess jedoch unabhängig ausgeführt. In der .NET Framework Version 2,0 und höheren Versionen ermöglichen neue Abstraktions Ebenen dem Host die Bereitstellung zahlreicher Ressourcen, die derzeit von den Typen in der Win32-Assembly bereitgestellt werden, und erweitern den Satz von Funktionen, die der Host konfigurieren kann.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [IActionOnCLREvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 Stellt eine Methode bereit, die einen Rückruf für ein registriertes Ereignis ausführt.  
  
 [IApartmentCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 Stellt Methoden bereit, um Rückrufe in einem Apartment zu erstellen.  
  
 [IAppDomainBinding-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 Stellt Methoden zum Festlegen der Laufzeitkonfiguration bereit.  
  
 [ICatalogServices-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 Stellt Methoden für das Katalogisieren von Diensten bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)  
  
 [ICLRAssemblyIdentityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 Stellt Methoden bereit, die die Kommunikation zwischen dem Host und der CLR über Assemblys unterstützen.  
  
 [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 Verwaltet eine Liste von Assemblys, die von der CLR und nicht vom Host geladen werden.  
  
 [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 Stellt Methoden bereit, mit denen der Host auf die CLR zugreifen und verschiedene Aspekte konfigurieren kann.  
  
 [ICLRDebugManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 Stellt Methoden bereit, mit deren Hilfe einem Host eine Reihe von Tasks mit einem Bezeichner und einem anzeigen Amen verknüpft werden können.  
  
 [ICLRErrorReportingManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, benutzerdefinierte Heap-Abbilder für die Fehlerberichterstattung zu konfigurieren.  
  
 [ICLRGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 Stellt Methoden bereit, mit denen ein Host mit dem Garbage Collection System der CLR interagieren kann.  
  
 [ICLRHostBindingPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 Stellt Methoden bereit, mit denen der Host Änderungen an Richtlinien Informationen für Assemblys auswerten und übermitteln können.  
  
 [ICLRHostProtectionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 Ermöglicht es dem Host, bestimmte verwaltete Klassen, Methoden, Eigenschaften und Felder von der Ausführung in teilweise vertrauenswürdigem Code zu blockieren.  
  
 [ICLRIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 Implementiert eine Rückruf Methode, die es dem Host ermöglicht, die CLR über den Status der angegebenen e/a-Anforderungen zu benachrichtigen.  
  
 [ICLRMemoryNotificationCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 Ermöglicht es dem Host, Speicher Auslastungs Bedingungen mithilfe eines ähnlichen Ansatzes wie der Win32-`CreateMemoryResourceNotification` Funktion zu melden.  
  
 [ICLROnEventManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, Rückrufe für CLR-Ereignisse zu registrieren und die Registrierung aufzuheben.  
  
 [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, Richtlinien Aktionen anzugeben, die im Fall von Fehlern und Timeouts durchgeführt werden sollen.  
  
 [ICLRProbingAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, die in der CLR internen Identitätsinformationen der Assembly zu ermitteln, ohne diese Identität erstellen oder verstehen zu müssen.  
  
 [ICLRReferenceAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, den Satz von Assemblys, auf die von einer Datei oder einem Stream verwiesen wird, mithilfe von Assemblyidentitätsdaten zu bearbeiten, die für die CLR intern sind, ohne dass diese Identitäten  
  
 [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 Bietet ähnliche Funktionen wie [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)mit einer zusätzlichen Methode zum Festlegen der Host Steuerungs Schnittstelle.  
  
 [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 Stellt Methoden bereit, mit denen der Hostinformationen zu angeforderten Tasks und Deadlocks in der Synchronisierungs Implementierung erhält.  
  
 [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, Anforderungen an die CLR zu senden oder die CLR über die zugeordnete Aufgabe benachrichtigt zu werden.  
  
 [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 Stellt Methoden bereit, die es dem Host ermöglichen, explizit anzufordern, dass die CLR einen neuen Task erstellt, die aktuell ausgeführte Aufgabe erhält und die geografische Sprache und Kultur für den Task festgelegt.  
  
 [ICLRValidator-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 Stellt Methoden zum Überprüfen von PE-Images (portable ausführbare Dateien) und zum Melden von Validierungs Fehlern bereit.  
  
 [ICorConfiguration-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 Stellt Methoden zum Konfigurieren der CLR bereit.  
  
 [ICorThreadpool-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 Stellt Methoden für den Zugriff auf den Thread Pool bereit.  
  
 [IDebuggerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 Stellt Methoden zum Abrufen von Informationen über den Zustand der Debugdienste bereit.  
  
 [IDebuggerThreadControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 Stellt Methoden bereit, mit denen der Host über die Blockierung und Aufhebung der Blockierung von Threads durch die Debugdienste benachrichtigt wird.  
  
 [IGCHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 Bietet Methoden zum Abrufen von Informationen über das Garbage Collection System und zum Steuern einiger Aspekte von Garbage Collection.  
  
 [IGCHost2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 Stellt die [setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) -Methode bereit, mit der ein Host die Größe des Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems auf Werte festlegen kann, die größer als `DWORD`sind.  
  
 [IGCHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 Stellt eine Methode bereit, die es dem Garbage Collector ermöglicht, den Host zum Ändern der Grenzwerte für den virtuellen Arbeitsspeicher anzufordern.  
  
 [IGCThreadControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 Stellt Methoden für die Teilnahme an der Planung von Threads bereit, die andernfalls für Garbage Collection blockiert werden.  
  
 [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 Stellt Methoden bereit, mit denen ein Host Assemblys angeben kann, die von der CLR oder vom Host geladen werden sollen.  
  
 [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 Stellt Methoden bereit, mit denen ein Host Assemblys und Module unabhängig von der CLR laden kann.  
  
 [IHostAutoEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 Stellt eine Darstellung eines vom Host implementierten automatischen Zurücksetzungs Ereignisses bereit.  
  
 [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 Bietet Methoden zum Konfigurieren des Ladens von Assemblys und zum bestimmen, welche Hostingschnittstellen der Host unterstützt.  
  
 [IHostCrst-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 Dient als Host Darstellung eines kritischen Abschnitts zum Threading.  
  
 [IHostGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 Stellt Methoden bereit, die den Host von Ereignissen in der von der CLR implementierten Garbage Collection Mechanismus benachrichtigen.  
  
 [IHostIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 Stellt Methoden bereit, mit denen die CLR mit e/a-Abschlussports interagieren kann, die vom Host bereitgestellt werden.  
  
 [IHostMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 Stellt Methoden für die CLR bereit, um differenzierte Zuordnungen vom Heap über den Host anzufordern.  
  
 [IHostManualEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 Stellt die Implementierung eines Hosts für ein manuelles Zurücksetzungs Ereignis bereit.  
  
 [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 Stellt Methoden für die CLR bereit, um virtuelle Speicheranforderungen über den Host zu erstellen, statt die standardmäßigen Win32-Funktionen für den virtuellen Arbeitsspeicher zu verwenden.  
  
 [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 Stellt Methoden bereit, die den Host über die Aktionen Benachrichtigen, die die CLR im Falle von Abbrüche, Timeouts oder Fehlern ausführt.  
  
 [IHostSecurityContext-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 Ermöglicht der CLR die Verwaltung von Sicherheitskontext Informationen, die vom Host implementiert werden.  
  
 [IHostSecurityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 Stellt Methoden bereit, die den Zugriff auf den Sicherheitskontext des aktuell ausgeführten Threads ermöglichen und dessen Steuerung ermöglichen.  
  
 [IHostSemaphore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 Stellt eine Darstellung eines Semaphors bereit, der vom Host implementiert wird.  
  
 [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 Stellt Methoden für die CLR bereit, um Synchronisierungs primitive durch Aufrufen des Hosts zu erstellen, statt die Win32-Synchronisierungs Funktionen zu verwenden.  
  
 [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 Stellt Methoden bereit, mit denen die CLR mit dem Host kommunizieren kann, um Aufgaben zu verwalten.  
  
 [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 Stellt Methoden bereit, mit denen die CLR mit Aufgaben über den Host arbeiten kann, anstatt die Threading-oder Fiber-Funktionen des Standard Betriebssystems zu verwenden.  
  
 [IHostThreadPoolManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 Stellt Methoden für die CLR bereit, um den Thread Pool zu konfigurieren und Arbeitselemente in die Warteschlange des Thread Pools zu übermitteln.  
  
 [IManagedObject-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 Stellt Methoden zum Steuern eines verwalteten Objekts bereit.  
  
 IObjectHandle  
 Stellt eine Methode zum Entpacken von Marshal-by-Value-Objekten aus der Dereferenzierung bereit.  
  
 [ITypeName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 Stellt Methoden zum Abrufen von Informationen zum Typnamen bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)  
  
 [ITypeNameBuilder-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 Stellt Methoden zum Entwickeln eines Typnamens bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)  
  
 [ITypeNameFactory-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 Stellt Methoden zum dekonstruieren eines Typnamens bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.)  
  
 IValidator  
 Stellt Methoden zum Überprüfen von PE-Images (portable ausführbare Dateien) und zum Melden von Validierungs Fehlern bereit.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Veraltete CLR-Hostingschnittstellen und Co-Klassen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Enthält Themen, in denen die Hostingschnittstellen in den .NET Framework Version 1,0 und 1,1 beschrieben werden.  
  
 [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 Enthält Themen, in denen die Hostingschnittstellen in den .NET Framework 4 beschrieben werden.
