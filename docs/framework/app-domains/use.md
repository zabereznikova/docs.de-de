---
title: "Verwenden von Anwendungsdom&#228;nen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwendungsdomänen, Informationen"
  - "Common Language Runtime, Anwendungsdomänen"
  - "Laufzeit, Anwendungsdomänen"
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Verwenden von Anwendungsdom&#228;nen
Anwendungsdomänen stellen eine Isolationseinheit für die Common Language Runtime bereit.  Sie werden innerhalb eines Prozesses erstellt und ausgeführt.  Anwendungsdomänen werden in der Regel von einem Common Language Runtime\-Host erstellt, d. h. einer Anwendung, die für das Laden der Common Language Runtime in einen Prozess und das Ausführen von Benutzercode innerhalb einer Anwendungsdomäne zuständig ist.  Ein solcher Host erstellt einen Prozess und eine Standardanwendungsdomäne und führt darin verwalteten Code aus.  Common Language Runtime\-Hosts sind z. B. ASP.NET, Microsoft Internet Explorer und Windows Shell.  
  
 Für die meisten Anwendungen brauchen Sie keine eigene Anwendungsdomäne zu erstellen; der Common Language Runtime\-Host nimmt Ihnen diese Aufgabe ab.  Sie können jedoch zusätzliche Anwendungsdomänen erstellen und konfigurieren, wenn in der Anwendung Code isoliert werden muss oder DLLs verwendet und entladen werden müssen.  
  
## In diesem Abschnitt  
 [Gewusst wie: Erstellen einer Anwendungsdomäne](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 Beschreibt das programmgesteuerte Erstellen einer Anwendungsdomäne.  
  
 [Gewusst wie: Entladen einer Anwendungsdomäne](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 Beschreibt das programmgesteuerte Entladen einer Anwendungsdomäne.  
  
 [Gewusst wie: Konfigurieren einer Anwendungsdomäne](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 Enthält eine Einführung in das Konfigurieren von Anwendungsdomänen.  
  
 [Abrufen von Setupinformationen aus einer Anwendungsdomäne](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 Beschreibt das Abrufen von Setupinformationen aus einer Anwendungsdomäne.  
  
 [Gewusst wie: Laden von Assemblys in eine Anwendungsdomäne](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 Beschreibt das Laden einer Assembly in eine Anwendungsdomäne.  
  
 [Gewusst wie: Abrufen von Typ\- und Memberinformationen aus einer Assembly](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Beschreibt das Abrufen von Informationen zu einer Assembly.  
  
 [Erstellen von Schattenkopien von Assemblys](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 Beschreibt, wie das Erstellen von Schattenkopien Aktualisierungen von Assemblys ermöglicht, während diese verwendet werden, und das Konfigurieren der Erstellung von Schattenkopien.  
  
 [Gewusst wie: Empfangen von Ausnahmebenachrichtigungen \(erste Chance\)](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 Erläutert, wie Sie eine Benachrichtigung erhalten können, dass eine Ausnahme ausgelöst wurde, bevor die Common Language Runtime die Suche nach Ausnahmehandlern begonnen hat.  
  
 [Auflösen beim Laden von Assemblys](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 Enthält Anleitungen zur Verwendung des <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>\-Ereignisses, um Fehler beim Laden von Assemblys zu beheben.  
  
## Referenz  
 <xref:System.AppDomain>  
 Stellt eine Anwendungsdomäne dar.  Stellt Methoden zum Erstellen und Steuern von Anwendungsdomänen bereit.  
  
## Verwandte Abschnitte  
 [Assemblys in der Common Language Runtime \(CLR\)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Bietet eine Übersicht über die von Assemblys ausgeführten Funktionen.  
  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Beschreibt das Erstellen, Signieren und Festlegen von Attributen für Assemblys.  
  
 [Ausgeben von dynamischen Methoden und Assemblys](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Beschreibt das Erstellen dynamischer Assemblys.  
  
 [Anwendungsdomänen](../../../docs/framework/app-domains/application-domains.md)  
 Bietet eine konzeptionelle Übersicht über Anwendungsdomänen.  
  
 [Übersicht über Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Beschreibt das Verwenden der **Reflection**\-Klasse, um Informationen zu einer Assembly zu erhalten.