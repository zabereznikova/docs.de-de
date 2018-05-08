---
title: CLR-Hostingschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03839a2c6e52f9d2dcdd2e0941ff4fdbeb8a3a17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="clr-hosting-interfaces"></a>CLR-Hostingschnittstellen
Dieser Abschnitt beschreibt die Schnittstellen, die nicht verwaltete Hosts können Sie die common Language Runtime (CLR) in ihre Anwendungen integrieren. Die Informationen bezieht sich auf die Version von .NET Framework 2.0 und höheren Versionen. Diese Schnittstellen aktivieren Sie den Host zu steuern, zahlreiche weitere Aspekte der Laufzeit, als dies in den Versionen 1.0 und 1.1 möglich war, und geben eine engere Integration zwischen der CLR und Ausführungsmodell des Hosts.  
  
 In .NET Framework, Version 1.0 und 1.1 aktiviert die Host-Modell einen nicht verwalteten Host zum Laden der CLR in einen Prozess, um bestimmte Einstellungen konfigurieren und ereignisbenachrichtigungen zu empfangen. Allerdings ausgeführt hat, im Allgemeinen dem Host und der CLR unabhängig im jeweiligen Prozess. In der .NET Framework Version 2.0 und höheren Versionen können neue Ebenen Abstraktionsebene Hosts bereitzustellen Großteil der Ressourcen, die derzeit von den Typen in der Win32-Assembly bereitgestellt, und erweitern Sie den Satz von Funktionen, die der Host konfigurieren können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [IActionOnCLREvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 Stellt eine Methode, die einen Rückruf für ein registriertes Ereignis ausführt.  
  
 [IApartmentCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 Stellt Methoden für Rückrufe innerhalb eines Apartments bereit.  
  
 [IAppDomainBinding-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 Stellt Methoden zum Festlegen der Konfiguration zur Laufzeit bereit.  
  
 [ICatalogServices-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 Stellt Methoden zum Katalogisieren von Diensten bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)  
  
 [ICLRAssemblyIdentityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 Enthält Methoden, die Kommunikation zwischen dem Host und der CLR zu Assemblys zu unterstützen.  
  
 [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 Verwaltet eine Liste der Assemblys, die von der CLR und nicht vom Host geladen werden.  
  
 [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 Stellt Methoden für den Zugriff auf, und konfigurieren verschiedene Aspekte der CLR-Host bereit.  
  
 [ICLRDebugManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 Enthält Methoden, mit die einen Host eine Reihe von Aufgaben mit einem Bezeichner und einen Anzeigenamen zuordnen können.  
  
 [ICLRErrorReportingManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 Enthält Methoden, die den Host so konfigurieren Sie benutzerdefinierte Heapdumps für die Fehlerberichterstattung zu aktivieren.  
  
 [ICLRGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 Enthält Methoden, die einen Host für die Interaktion mit der CLR Garbage Collection-System zu aktivieren.  
  
 [ICLRHostBindingPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 Stellt Methoden für den Host zum Auswerten und kommunizieren von Änderungen in Richtlinieninformationen für Assemblys bereit.  
  
 [ICLRHostProtectionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 Ermöglicht es dem Host zum Blockieren von bestimmten verwaltete Klassen, Methoden, Eigenschaften und Felder in teilweise vertrauenswürdigem Code ausgeführt wird.  
  
 [ICLRIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 Implementiert eine Rückrufmethode, die den Host zu benachrichtigen, die CLR über den Status der angegebenen e/a-Anfragen ermöglicht.  
  
 [ICLRMemoryNotificationCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 Ermöglicht es dem Host mit einem Ansatz ähnelt der des Win32-speicherauslastung des Berichts `CreateMemoryResourceNotification` Funktion.  
  
 [ICLROnEventManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 Enthält Methoden, die den Host zu registrieren und Aufheben der Rückrufe für CLR-Ereignisse zu aktivieren.  
  
 [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 Enthält Methoden, mit die den Host Geben Sie die für Richtlinienaktionen, die im Falle von Fehlern und Timeouts ausgeführt werden können.  
  
 [ICLRProbingAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 Enthält Methoden, mit denen der Host zum Abrufen der gesuchten Identitäten einer Assembly mit der Assembly aneinander gehängt Identitätsinformationen, die ohne erstellen oder zu verstehen, die Identität für die CLR intern ist.  
  
 [ICLRReferenceAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 Enthält Methoden, mit die den Host den Satz von Assemblys, auf eine Datei oder einen Stream mit der Assemblyidentitätsdaten, die für die CLR intern ist, ohne diese Identitäten erstellen oder verstehen verweist bearbeiten können.  
  
 [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 Bietet Funktionen, die ähnlich wie [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), mit der eine weitere Methode zum Festlegen der Schnittstelle des Steuerelements.  
  
 [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 Stellt Methoden für den Host zum Abrufen von Informationen zur angeforderten Aufgaben und zum Erkennen von Deadlocks in seiner Implementierung Synchronisierung bereit.  
  
 [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 Enthält Methoden, mit denen den Host aus, um die Anforderungen der CLR auszuführen oder um eine Benachrichtigung an die CLR über die zugewiesene Aufgabe bereitzustellen.  
  
 [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 Enthält Methoden, die den Host explizit anfordern, dass CLR Erstellen eines neuen Tasks, die aktuell ausgeführte Aufgabe abrufen und festlegen, die geografische Sprache und Kultur für den Task zu aktivieren.  
  
 [ICLRValidator-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 Stellt Methoden zum Überprüfen von portablen ausführbaren Datei (PE) Bilder aus, und Melden von Validierungsfehlern.  
  
 [ICorConfiguration-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 Stellt Methoden zum Konfigurieren der CLR.  
  
 [ICorThreadpool-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 Stellt Methoden für den Zugriff auf den Threadpool bereit.  
  
 [IDebuggerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 Stellt Methoden zum Abrufen von Informationen über den Zustand der Debugdienste bereit.  
  
 [IDebuggerThreadControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 Stellt Methoden zum Benachrichtigen des Hosts über die Blockierung und zum Aufheben der Blockierung von Threads von den Debugdiensten bereit.  
  
 [IGCHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern des einige Aspekte der Garbagecollection.  
  
 [IGCHost2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 Stellt die [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) Methode, die einen Host für die Größe der Garbage Collection-Segment und die maximale Größe der Generation 0 (null), die Garbage Collection-System Werte größer als festzulegen ermöglicht `DWORD`.  
  
 [IGCHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 Stellt eine Methode, die der Garbage Collector, den Host zum Ändern der Grenzen des virtuellen Speichers ermöglicht.  
  
 [IGCThreadControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 Stellt Methoden für die Einbeziehung in die Planung von Threads, die andernfalls für die Garbagecollection blockiert werden würde.  
  
 [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 Enthält Methoden, mit denen einen Host Sätze von Assemblys angeben, die von der CLR oder vom Host geladen werden soll.  
  
 [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 Enthält Methoden, die einen Host zum Laden von Assemblys und Modulen unabhängig von der CLR zu aktivieren.  
  
 [IHostAutoEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 Bietet eine Darstellung eines vom Host implementierte AutoReset-Ereignisses.  
  
 [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 Stellt Methoden für das Laden von Assemblys zu konfigurieren und um zu bestimmen, welche hosting vom Host unterstützten Schnittstellen bereit.  
  
 [IHostCrst-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 Dient als Host Darstellung eines kritischen Abschnitts für threading.  
  
 [IHostGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 Enthält Methoden, die den Host der Ereignisse in die Garbage Collection-Mechanismus implementiert, die von der CLR zu benachrichtigen.  
  
 [IHostIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 Enthält Methoden, die die CLR für die Interaktion mit e/a-Abschlussports vom Host zu ermöglichen.  
  
 [IHostMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 Stellt Methoden für die CLR eine präzisere Zuordnungen aus dem Heap über den Host anfordern.  
  
 [IHostManualEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 Stellt den Host-Implementierung der eine Repräsentation ein Ereignis für manuelles Zurücksetzen.  
  
 [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 Stellt Methoden für die CLR über den Host, anstelle der standardmäßigen Win32 virtueller Arbeitsspeicher Funktionen virtueller Arbeitsspeicher anzufordern.  
  
 [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 Enthält Methoden, mit die benachrichtigt der Host über die Aktionen, die im Fall von die CLR führt abbricht, Timeouts oder Fehlern.  
  
 [IHostSecurityContext-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 Aktiviert die CLR vom Host implementiert wurde Sicherheitskontextinformationen zu verwalten.  
  
 [IHostSecurityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 Stellt Methoden, die zum Aktivieren des Zugriffs auf und die Kontrolle über den Sicherheitskontext des aktuell ausgeführten Threads.  
  
 [IHostSemaphore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 Bietet eine Darstellung einer vom Host implementierte Semaphore.  
  
 [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 Stellt Methoden für die CLR Synchronisierungsprimitive durch Aufrufen des Hosts, anstatt die Win32-Synchronisierungsfunktionen zu erstellen.  
  
 [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 Enthält Methoden, die die CLR für die Kommunikation mit dem Host zum Verwalten von Aufgaben ermöglichen.  
  
 [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 Enthält Methoden, die die CLR arbeiten mit Aufgaben, die über den Host anstatt das standard-Betriebssystems threading oder Fiber-Funktionen zu aktivieren.  
  
 [IHostThreadPoolManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 Stellt Methoden für die CLR den Threadpool konfigurieren und Arbeitsaufgaben für den Threadpool in die Warteschlange bereit.  
  
 [IManagedObject-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 Stellt Methoden zum Steuern von eines verwalteten Objekts.  
  
 "IObjectHandle"  
 Stellt eine Methode zum Entpacken Marshal-by-Value-Objekten aus Dereferenzierung.  
  
 [ITypeName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 Stellt Methoden zum Abrufen von Name-Typinformationen. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)  
  
 [ITypeNameBuilder-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 Stellt Methoden zum Erstellen eines Typnamens bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)  
  
 [ITypeNameFactory-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 Stellt Methoden zum Zerlegen eines Typnamens bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)  
  
 "IValidator"  
 Stellt Methoden zum Überprüfen von portablen ausführbaren Datei (PE) Bilder aus, und Melden von Validierungsfehlern.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Veraltete CLR-Hostingschnittstellen und Co-Klassen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Enthält Themen, die in .NET Framework, Version 1.0 und 1.1 bereitgestellten Hostingschnittstellen beschrieben.  
  
 [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 Enthält Themen, die bereitgestellten Hostingschnittstellen beschreiben, die [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].
