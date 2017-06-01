---
title: "Firefox-Add-Ons zur Unterst&#252;tzung der .NET-Anwendungsbereitstellung | Microsoft Docs"
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
  - ".NET-Anwendungsbereitstellung, Bereitstellen mit Firefox-Add-Ons"
  - ".NET Framework-Assistent für Firefox"
  - "Firefox-Add-Ons für .NET-Anwendungsbereitstellung"
  - "WPF-Plug-In für Firefox"
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Firefox-Add-Ons zur Unterst&#252;tzung der .NET-Anwendungsbereitstellung
Das [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Plug\-In für Firefox und der .NET Framework\-Assistent für Firefox ermöglichen die Verwendung von [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und ClickOnce\-Anwendungen mit dem Mozilla Firefox\-Browser.  
  
## WPF\-Plug\-In für Firefox  
 Das WPF\-Plug\-In für Firefox ermöglicht die Navigation in [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] und Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Dateien und deren Ausführung auf der obersten Ebene oder in einem HTML\-IFRAME im Firefox\-Browser.  Eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ist eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendung, die auf einem Webserver veröffentlicht und in unterstützten Browsern gestartet werden kann.  Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist eine reine XAML\-Datei, zu der in unterstützten Browsern navigiert werden kann und die ähnlich wie eine XML\-Datei in diesen Browsern angezeigt werden kann.  
  
 Das [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Plug\-In für Firefox wird mit [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] installiert.  Windows 7 enthält [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], aber nicht das [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Plug\-In für Firefox. Das [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Plug\-In für Firefox kann unter Windows 7 nicht installiert werden.  
  
 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] enthält das [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Plug\-In für Firefox nicht. Wenn jedoch [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] und [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] installiert sind, wird das WPF\-Plug\-In für Firefox mit [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] installiert.  Da der WPF\-Host die richtige Frameworkversion lädt, können [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]\-Anwendungen daher weiterhin ausgeführt werden.  Weitere Informationen finden Sie unter [WPF\-Host \(PresentationHost.exe\)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md).  
  
## .NET Framework\-Assistent für Firefox  
 Der .NET Framework\-Assistent für Firefox ermöglicht die Ausführung eigenständiger ClickOnce\-Anwendungen im Firefox\-Browser.  Die Funktion des .NET Framework\-Assistenten für Firefox ist unabhängig davon, ob er vor und nach dem Firefox\-Browser installiert wird, immer gleich.  Wenn der Firefox\-Browser gestartet wird und [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] installiert ist, sucht Firefox nach dem .NET Framework\-Assistenten für Firefox und installiert ihn.  Benutzer können die folgenden Funktionen des .NET Framework\-Assistenten für Firefox konfigurieren:  
  
-   Eingabeaufforderung vor dem Ausführen der ClickOnce\-Anwendung  
  
-   Anzeige aller installierten Versionen von .NET Framework oder nur der aktuellen Version  
  
 Der .NET Framework\-Assistent für Firefox ist in [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] enthalten.  Informationen zum Entfernen des .NET Framework\-Assistenten für Firefox finden Sie im Thema zum [Entfernen des .NET Framework\-Assistenten für Firefox](http://go.microsoft.com/fwlink/?LinkId=177944) \(möglicherweise in englischer Sprache\).  
  
## Siehe auch  
 [Bereitstellen von WPF\-Anwendungen](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)   
 [Übersicht über WPF\-XAML\-Browseranwendungen](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)   
 [Erkennen einer Installation des WPF\-Plug\-Ins für Firefox](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)