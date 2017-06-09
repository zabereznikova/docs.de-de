---
title: "Gewusst wie: Konfigurieren von Visual Studio 2005 zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Konfigurieren von Visual Studio zum Debuggen von XAML-Browseranwendungen [WPF]"
  - "Konfigurieren von Visual Studio zum Debuggen von XBAPs [WPF]"
  - "Debuggen von Sicherheitsausnahmen für XBAPs [WPF]"
  - "Debuggen von XBAPs, die einen Webdienst aufrufen [WPF]"
  - "Sicherheitsausnahme für XBAPs [WPF], Debuggen"
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Konfigurieren von Visual Studio 2005 zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] werden innerhalb eines teilweise vertrauenswürdigen Sicherheitsbereichs \(Sandbox\) ausgeführt, der auf den Berechtigungssatz der Internetzone beschränkt ist.  Mit diesem Berechtigungssatz werden Webdienstaufrufe nur auf Webdienste beschränkt, die sich an der Ursprungssite der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]\-Anwendung befinden.  Wenn eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] von [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] gedebuggt wird, wird jedoch davon ausgegangen, dass sie nicht die gleiche Ursprungssite hat wie der Webdienst, auf den sie verweist.  Dies bewirkt, dass Sicherheitsausnahmen ausgelöst werden, wenn die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] versucht, den Webdienst aufzurufen.  Ein [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)]\-Projekt kann jedoch auch so konfiguriert werden, dass es während des Debugging anscheinend die gleiche Ursprungssite wie der aufzurufende Webdienst hat.  Dies ermöglicht es der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], den Webdienst ohne Sicherheitsausnahmen sicher aufzurufen.  
  
## Konfigurieren von Visual Studio  
 So konfigurieren Sie [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] zum Debuggen einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], die einen Webdienst aufruft  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus, und klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2.  Klicken Sie im **Projekt\-Designer** auf die Registerkarte **Debuggen**.  
  
3.  Wählen Sie im Abschnitt **Startaktion** die Option **Externes Programm starten** aus, und geben Sie Folgendes ein:  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  Geben Sie im Abschnitt **Startoptionen** Folgendes in das Textfeld **Befehlszeilenargumente** ein:  
  
     `-debug`  *filename*  
  
     Der *Dateiname*\-Wert für den **\-debug**\-Parameter ist der XBAP\-Dateiname, z. B.:  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  Dies ist die Standardkonfiguration für Projektmappen, die mit der [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)]\-Projektvorlage von [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] erstellt werden.  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus, und klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2.  Klicken Sie im **Projekt\-Designer** auf die Registerkarte **Debuggen**.  
  
3.  Fügen Sie im Abschnitt **Startoptionen** den folgenden Befehlszeilenparameter dem Textfeld **Befehlszeilenargumente** hinzu:  
  
     `-debugSecurityZoneURL`  *URL*  
  
     Der *URL*\-Wert für den **\-debugSecurityZoneURL**\-Parameter ist die [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] für die zu simulierende Ursprungssite Ihrer Anwendung.  
  
 Betrachten Sie als Beispiel eine [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)], die einen Webdienst mit folgender [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] verwendet:  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 Die Ursprungssite\-[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] für diesen Webdienst ist:  
  
 `http://services.msdn.microsoft.com`  
  
 Infolgedessen ist der vollständige **\-debugSecurityZoneURL**\-Befehlszeilenparameter und \-Wert:  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## Siehe auch  
 [WPF\-Host \(PresentationHost.exe\)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)