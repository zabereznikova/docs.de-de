---
title: "Ausf&#252;hren von Intranetanwendungen mit voller Vertrauensw&#252;rdigkeit | Microsoft Docs"
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
  - "Volle Vertrauenswürdigkeit, Ausführen von Intranetanwendungen mit"
  - "Intranetanwendungen, Ausführen mit voller Vertrauenswürdigkeit"
  - "Ausführen von Intranetanwendungen mit voller Vertrauenswürdigkeit"
ms.assetid: ee13c0a8-ab02-49f7-b8fb-9eab16c6c4f0
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# Ausf&#252;hren von Intranetanwendungen mit voller Vertrauensw&#252;rdigkeit
Ab .NET Framework 3.5 Service Pack 1 \(SP1\) können Anwendungen und ihre Bibliotheksassemblys als vollständig vertrauenswürdige Assemblys von einer Netzwerkfreigabe ausgeführt werden.  Der <xref:System.Security.SecurityZone>\-Zonenbeweis wird automatisch Assemblys hinzugefügt, die von einer Freigabe im Intranet geladen werden.  Dieser Beweis gibt solchen Assemblys denselben Berechtigungssatz \(üblicherweise vollständig vertrauenswürdig\) wie den Assemblys, die sich auf dem Computer befinden.  Diese Funktionalität gilt nicht für ClickOnce\-Anwendungen oder für Anwendungen, die darauf ausgerichtet sind, auf einem Host ausgeführt zu werden.  
  
## Regeln für Bibliotheksassemblys  
 Die folgenden Regeln gelten für Assemblys, die von einer ausführbaren Datei in einer Netzwerkfreigabe geladen werden:  
  
-   Bibliotheksassemblys müssen sich im gleichen Ordner wie die ausführbare Assembly befinden.  Assemblys, die sich in einem Unterordner befinden oder auf die von einem anderen Pfad verwiesen wird, erhalten nicht den voll vertrauenswürdigen Berechtigungssatz.  
  
-   Wenn die ausführbare Datei eine Assembly verzögert lädt, muss sie denselben Pfad verwenden, mit dem auch die ausführbare Datei gestartet wurde.  Wenn Freigaben\\ \\*network\-computer*\\*share* einem Laufwerkbuchstaben zugeordnet ist und die ausführbare Datei von diesem Pfad ausgeführt wird, werden die Assemblys, die durch die ausführbare Datei geladen werden, indem der nicht verwendet, Netzwerkpfad volle Vertrauenswürdigkeit gewährt.  Um eine Assembly in der <xref:System.Security.SecurityZone>\-Zone verzögert zu laden, muss die ausführbare Datei den Pfad mit dem Laufwerkbuchstaben verwenden.  
  
## Wiederherstellen der früheren Intranetrichtlinie  
 In früheren Versionen von .NET Framework wurde freigegebenen Assemblys der <xref:System.Security.SecurityZone>\-Zonenbeweis gewährt.  Sie mussten Sicherheitsrichtlinien für den Codezugriff festlegen, um einer Assembly auf einer Freigabe volle Vertrauenswürdigkeit zu gewähren.  
  
 Dieses neue Verhalten ist das Standardverhalten für Intranetassemblys.  Sie können zum früheren Verhalten der Bereitstellung des <xref:System.Security.SecurityZone>\-Beweises zurückkehren, indem Sie einen Registrierungsschlüssel festlegen, der für alle Anwendungen auf dem Computer gilt.  Dieser Prozess ist für 32\-Bit\- und 64\-Bit\-Computer unterschiedlich:  
  
-   Erstellen Sie auf 32\-Bit\-Computern in der Systemregistrierung einen Unterschlüssel unter dem Schlüssel HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework.  Verwenden Sie den Schlüsselnamen "LegacyMyComputerZone" mit dem DWORD\-Wert 1.  
  
-   Erstellen Sie auf 64\-Bit\-Computern in der Systemregistrierung einen Unterschlüssel unter dem Schlüssel HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework.  Verwenden Sie den Schlüsselnamen "LegacyMyComputerZone" mit dem DWORD\-Wert 1.  Erstellen Sie den gleichen Unterschlüssel unter dem Schlüssel "HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework".  
  
## Siehe auch  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)