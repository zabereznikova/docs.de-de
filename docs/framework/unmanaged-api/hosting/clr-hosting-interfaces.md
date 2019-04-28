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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789661"
---
# <a name="clr-hosting-interfaces"></a>CLR-Hostingschnittstellen
In diesem Abschnitt wird beschrieben, die Schnittstellen, die nicht verwaltete Hosts können die common Language Runtime (CLR) in ihre Anwendungen integrieren. Die Informationen bezieht sich auf die Version von .NET Framework 2.0 und höheren Versionen. Diese Schnittstellen aktivieren Sie den Host zu steuern, zahlreiche weitere Aspekte der Laufzeit als in den Versionen 1.0 und 1.1 möglich war, und geben eine engere Integration zwischen der CLR und Ausführungsmodell des Hosts.  
  
 In .NET Framework, Version 1.0 und 1.1 aktiviert das hosting-Modell einen nicht verwalteten Host zum Laden der CLR in einen Prozess, um bestimmte Einstellungen zu konfigurieren und ereignisbenachrichtigungen empfangen. Allerdings wurde ausgeführt im Allgemeinen dem Host und die CLR unabhängig voneinander in diesem Prozess. In der .NET Framework, Version 2.0 und höheren Versionen können neue Ebenen der Abstraktion den Host bieten viele der Ressourcen, die derzeit von den Typen in der Win32-Assembly bereitgestellt werden soll, und erweitern Sie den Satz von Funktionen, die der Host konfigurieren können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [IActionOnCLREvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 Stellt eine Methode, die einen Rückruf für ein registriertes Ereignis durchführt.  
  
 [IApartmentCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 Stellt Methoden für Rückrufe innerhalb einer Apartment.  
  
 [IAppDomainBinding-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 Stellt Methoden zum Festlegen der Runtime-Konfiguration bereit.  
  
 [ICatalogServices-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 Stellt Methoden zum Katalogisieren von Diensten bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)  
  
 [ICLRAssemblyIdentityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 Enthält Methoden, die Kommunikation zwischen dem Host und der CLR Informationen zu Assemblys zu unterstützen.  
  
 [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 Verwaltet eine Liste der Assemblys, die von der CLR und nicht vom Host geladen werden.  
  
 [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 Stellt Methoden für den Zugriff auf, und konfigurieren verschiedene Aspekte der CLR-Host bereit.  
  
 [ICLRDebugManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 Bietet Methoden, mit die einen Host eine Reihe von Aufgaben mit einem Bezeichner sowie einen Anzeigenamen zuordnen können.  
  
 [ICLRErrorReportingManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 Bietet Methoden, mit die den Host benutzerdefinierte Heap-Sicherungen für die Fehlerberichterstattung konfigurieren zu können.  
  
 [ICLRGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 Enthält Methoden, die einen Host für die Interaktion mit der CLR Garbage Collection-System zu ermöglichen.  
  
 [ICLRHostBindingPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 Stellt Methoden für den Host zum Auswerten und Übermitteln von Änderungen in Richtlinieninformationen für Assemblys.  
  
 [ICLRHostProtectionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 Ermöglicht es dem Host zum Blockieren von bestimmten verwaltete Klassen, Methoden, Eigenschaften und Felder aus, die in teilweise vertrauenswürdigen Code ausgeführt werden soll.  
  
 [ICLRIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 Implementiert eine Rückrufmethode, die den Host zu benachrichtigen, die CLR über den Status der angegebenen e/a-Anforderungen ermöglicht.  
  
 [ICLRMemoryNotificationCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 Ermöglicht dem Host, den Berichts-speicherauslastung, die mit einem Ansatz ähnelt der von der Win32 `CreateMemoryResourceNotification` Funktion.  
  
 [ICLROnEventManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 Bietet Methoden, mit denen den Host zu registrieren und Aufheben der Registrierung von Rückrufen für CLR-Ereignisse.  
  
 [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 Enthält Methoden, die den Host Geben Sie die, die bei Fehlern oder Timeouts auszuführenden Richtlinienaktionen zu ermöglichen.  
  
 [ICLRProbingAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 Bietet Methoden, mit denen der Host zum Abrufen der gesuchten Identitäten einer Assembly mit Informationen zur Identität der Assembly, die zum Erstellen oder zu verstehen, die diese Identität ohne intern für die CLR ist.  
  
 [ICLRReferenceAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 Bietet Methoden, mit die den Host den Satz von Assemblys, die auf die verwiesen wird von einer Datei oder den Stream unter Verwendung von Assembly-Identitätsdaten, die intern für die CLR ist, ohne diese Identitäten erstellen oder verstehen bearbeiten können.  
  
 [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 Bietet Funktionen, die ähnlich wie [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), mit der eine weitere Methode zum Festlegen der Schnittstelle des Steuerelements.  
  
 [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 Stellt Methoden für den Host zum Abrufen von Informationen zu den angeforderten Aufgaben und zum Erkennen von Deadlocks in die Synchronisierung-Implementierung bereit.  
  
 [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 Bietet Methoden, mit denen den Host aus, um die Anforderungen der CLR zu erstellen oder eine Benachrichtigung an die CLR über die zugewiesene Aufgabe bereitzustellen.  
  
 [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 Bietet Methoden, mit denen der Host explizit anfordern, dass die CLR erstellen eine neue Aufgabe, die aktuell ausgeführte Aufgabe zu erhalten und legen Sie die geografische Sprache und Kultur für den Task.  
  
 [ICLRValidator-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 Stellt Methoden zum Überprüfen der übertragbaren ausführbaren Datei (PE)-Abbildern, und Melden von Validierungsfehlern.  
  
 [ICorConfiguration-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 Stellt Methoden zum Konfigurieren der CLR.  
  
 [ICorThreadpool-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 Stellt Methoden für den Zugriff auf den Threadpool.  
  
 [IDebuggerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 Stellt Methoden zum Abrufen von Informationen über den Status der Debugdienste bereit.  
  
 [IDebuggerThreadControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 Stellt Methoden zum Benachrichtigen des Hosts über das Blockieren und Entsperren von Threads von den Debugdiensten.  
  
 [IGCHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern einige Aspekte der Garbagecollection.  
  
 [IGCHost2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 Stellt die [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) Methode, die einen Host, die Größe der Garbage Collection-Segment und die maximale Größe der Garbage Collection-Systems die Generation 0 (null) auf Werte größer als festzulegen ermöglicht `DWORD`.  
  
 [IGCHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 Stellt eine Methode, die der Garbage Collector, den Host zum Ändern der Grenzen des virtuellen Speichers ermöglicht.  
  
 [IGCThreadControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 Stellt Methoden für die Teilnahme an der Planung von Threads, die für die Garbagecollection andernfalls blockiert würden.  
  
 [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 Bietet Methoden, mit denen einen Host aus, um Assemblys anzugeben, die von der CLR oder vom Host geladen werden sollen.  
  
 [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 Enthält Methoden, die einen Host zum Laden von Assemblys und Modulen unabhängig von der CLR zu aktivieren.  
  
 [IHostAutoEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 Bietet eine Darstellung der ein automatisches Zurücksetzungsereignis vom Host implementiert.  
  
 [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 Stellt Methoden für das Laden von Assemblys zu konfigurieren und um zu bestimmen, welche hosting vom Host unterstützten Schnittstellen bereit.  
  
 [IHostCrst-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 Dient als Darstellung des Hosts in einem kritischen Abschnitt für das Threading teilweise.  
  
 [IHostGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 Enthält Methoden, die den Host der Ereignisse in die Garbage Collection-Mechanismus implementiert, die von der CLR zu benachrichtigen.  
  
 [IHostIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 Enthält Methoden, die die CLR für die Interaktion mit e/a-Abschlussports, die vom Host zu ermöglichen.  
  
 [IHostMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 Stellt Methoden für die CLR eine differenzierte Zuordnungen aus dem Heap über den Host anfordern.  
  
 [IHostManualEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 Stellt eine Darstellung der ein Ereignis mit manueller Rücksetzung Implementierung des Hosts.  
  
 [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 Stellt Methoden für die CLR um virtueller Arbeitsspeicher-Anforderungen über den Host, anstatt die standard Win32-Funktionen für virtuellen Arbeitsspeicher zu erstellen.  
  
 [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 Enthält Methoden, die der Host der CLR im Fall von durchgeführten Aktionen abgebrochen wird, Timeouts oder Fehlern zu benachrichtigen.  
  
 [IHostSecurityContext-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 Aktiviert die CLR vom Host implementierte Sicherheitskontextinformationen zu verwalten.  
  
 [IHostSecurityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 Bietet Methoden, mit denen Zugriff auf und Kontrolle über den Sicherheitskontext des gerade ausgeführten Threads.  
  
 [IHostSemaphore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 Bietet eine Darstellung eines Semaphors vom Host implementiert.  
  
 [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 Stellt Methoden für die CLR die Synchronisierungsprimitiven zu erstellen, indem Sie den Host, anstatt die Win32-Synchronisierung-Funktionen aufruft.  
  
 [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 Bietet Methoden, mit denen die CLR für die Kommunikation mit dem Host, um Aufgaben zu verwalten.  
  
 [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 Enthält Methoden, die die CLR arbeiten mit Aufgaben, die über den Host aus, anstatt die Standardbetriebssystem threading oder Fiber-Funktionen zu aktivieren.  
  
 [IHostThreadPoolManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 Stellt Methoden für die CLR, die zum Konfigurieren der Threadpool der Warteschleife hinzu und zum Arbeitsaufgaben an den Threadpool-Warteschlange.  
  
 [IManagedObject-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 Stellt Methoden zum Steuern eines verwalteten Objekts.  
  
 "IObjectHandle"  
 Stellt eine Methode für das Entpacken Marshal-by-Value-Objekte aus der Dereferenzierung.  
  
 [ITypeName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 Stellt Methoden zum Abrufen von Typinformationen für Namen bereit. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)  
  
 [ITypeNameBuilder-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 Stellt Methoden zum Erstellen eines Typnamens. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)  
  
 [ITypeNameFactory-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 Stellt Methoden zum dekonstruieren von einem Typnamen. (Diese Schnittstelle unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.)  
  
 "IValidator"  
 Stellt Methoden zum Überprüfen der übertragbaren ausführbaren Datei (PE)-Abbildern, und Melden von Validierungsfehlern.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Veraltete CLR-Hostingschnittstellen und Co-Klassen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Enthält Themen, die in .NET Framework, Version 1.0 und 1.1 bereitgestellten Hostingschnittstellen beschrieben.  
  
 [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 Enthält Themen, die beschreiben, die im bereitgestellten Hostingschnittstellen der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].
