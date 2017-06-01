---
title: "Sicherheitsberechtigung f&#252;r die Umleitung der Assemblybindung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Assemblys [.NET Framework], Bindungsumleitung"
  - "Parallele Ausführung, Umleitung der Assemblybindung"
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Sicherheitsberechtigung f&#252;r die Umleitung der Assemblybindung
Für die explizite Umleitung einer Assemblybindung in einer Anwendungskonfigurationsdatei ist eine Sicherheitsberechtigung erforderlich.  Dies betrifft die Umleitung von .NET Framework\-Assemblys und Assemblys von Drittanbietern.  Die Berechtigung wird erteilt, indem das [BindingRedirects](frlrfSystemSecurityPermissionsSecurityPermissionFlagClassTopic)\-Flag für die [SecurityPermission\-Klasse](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic) festgelegt wird.  Verwaltete Assemblys verfügen standardmäßig über keine Berechtigungen.  
  
 Die Sicherheitsberechtigung wird Anwendungen gewährt, die in der vertrauenswürdigen Zone \(lokaler Computer\) oder in der Intranetzone ausgeführt werden.  Bei Anwendungen, die in der Internetzone ausgeführt werden, darf eine Umleitung der Assemblybindung auf keinen Fall durchgeführt werden.  
  
 Die Berechtigung ist nicht erforderlich, wenn die Assemblyumleitung in einer durch den Komponentenpublisher gesteuerten Herausgeberrichtliniendatei oder in der durch den Administrator gesteuerten Computerkonfigurationsdatei durchgeführt wird.  Die Berechtigung ist jedoch erforderlich, damit eine Anwendung explizit die Herausgeberrichtlinie mithilfe des [\<publisherPolicy apply\= " no"\/\>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)\-Elements in der Anwendungskonfigurationsdatei ignoriert.  
  
 Die folgende Tabelle enthält die Standardsicherheitseinstellungen für das **BindingRedirects**\-Flag.  
  
|Zone|Einstellung für das BindingRedirects\-Flag|  
|----------|------------------------------------------------|  
|Vertrauenswürdige Zone \(lokaler Computer\)|**ON**|  
|Intranetzone|**ON**|  
|Internetzone|**OFF**|  
|Nicht vertrauenswürdige Zonen|**OFF**|  
  
 Administratoren können diese Sicherheitseinstellungen ändern, um bestimmte Szenarien auf einem Computer zu unterstützen oder einzuschränken.  Es sind keine Tools zum Ändern der Standardeinstellung des **BindingRedirects**\-Flags vorhanden. Administratoren müssen die Datei Security.config auf dem Computer eines Benutzers manuell bearbeiten.  
  
## Siehe auch  
 [Publisher Policy Files and Side\-by\-Side Execution](http://msdn.microsoft.com/de-de/97a042be-4d72-40c3-91c0-76fd36bdf133)   
 [Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)   
 [Parallele Ausführung](../../../docs/framework/deployment/side-by-side-execution.md)