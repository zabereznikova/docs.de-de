---
title: "Sicherheit in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Zugriffssteuerung, Windows Forms"
  - "Zugriffssicherheit für Designer"
  - "Berechtigungen, Windows Forms"
  - "Sicherheit [Windows Forms]"
  - "Sicherheitsrichtlinie, Windows Forms"
  - "Windows Forms, Sicherheit"
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Sicherheit in Windows&#160;Forms
Windows Forms bieten ein codebasiertes Sicherheitsmodell \(es werden Sicherheitsebenen für den Code festgelegt, unabhängig vom Benutzer, der den Code ausführt\).  Dies ergänzt die Sicherheitsschemas, die bereits im Computersystem wirksam sind.  Dazu können die Sicherheitsschemas des Browsers \(z. B. die auf Zonen beruhende Sicherheit in Internet Explorer\) oder diejenigen des Betriebssystems \(z. B. die auf Anmeldeinformationen beruhende Sicherheit unter Windows NT\) gehören.  
  
## In diesem Abschnitt  
 [Übersicht über die Sicherheit in Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 Erläutert kurz das .NET Framework\-Sicherheitsmodell sowie die grundlegenden Schritte, die für die Sicherheit der Windows Forms in der Anwendung erforderlich sind.  
  
 [Mehr Sicherheit beim Datei\- und Datenzugriff in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 Beschreibt, wie in einer halb vertrauenswürdigen Umgebung auf Dateien und Daten zugegriffen wird.  
  
 [Mehr Sicherheit beim Drucken in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 Beschreibt, wie in einer halb vertrauenswürdigen Umgebung auf Druckfunktionen zugegriffen wird.  
  
 [Weitere Überlegungen zur Sicherheit in Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 Beschreibt das Bearbeiten von Fenstern mit der Zwischenablage und das Aufrufen von nicht verwaltetem Code in einer halb vertrauenswürdigen Umgebung.  
  
## Verwandte Abschnitte  
 [NIB: Default Security Policy](http://msdn.microsoft.com/de-de/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 Listet die Standardberechtigungen auf, die in den Berechtigungssätzen Voll vertrauenswürdig, Lokales Intranet und Internet gewährt werden.  
  
 [NIB: General Security Policy Administration](http://msdn.microsoft.com/de-de/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 Enthält Informationen über die Verwaltung der .NET Framework\-Sicherheitsrichtlinie und das Erhöhen von Berechtigungen.  
  
 [Dangerous Permissions and Policy Administration](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 Erläutert einige .NET Framework\-Berechtigungen, die eine Umgehung des Sicherheitssystems zulassen.  
  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)  
 Stellt Links zu Themen bereit, die optimale Vorgehensweisen zum sicheren Schreiben von Code für NET. Framework erläutern.  
  
 [NIB: Requesting Permissions](http://msdn.microsoft.com/de-de/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 Erläutert die Verwendung von Attributen, um der Laufzeit zu übermitteln, welche Berechtigungen für das Ausführen des Codes erforderlich sind.  
  
 [Key Security Concepts](../../../docs/standard/security/key-security-concepts.md)  
 Stellt Links zu Themen bereit, die grundlegende Aspekte der Codesicherheit behandeln.  
  
 [Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md)  
 Erläutert die Grundlagen für das Arbeiten mit der .NET Framework\-Laufzeitsicherheitsrichtlinie.  
  
 [NIB: Determining When to Modify Security Policy](http://msdn.microsoft.com/de-de/af749b17-e461-409d-84b9-a3d44789db16)  
 Beschreibt die Vorgehensweise, um zu bestimmen, wann die Anwendungen von den standardmäßig vorgegebenen Sicherheitsrichtlinien abweichen müssen.  
  
 [NIB: Deploying Security Policy](http://msdn.microsoft.com/de-de/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 Erläutert die beste Methode für die Bereitstellung von Änderungen in den Sicherheitsrichtlinien.