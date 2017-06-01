---
title: "WPF-Host (PresentationHost.exe) | Microsoft Docs"
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
  - "PresentationHost.exe"
  - "WPF-Hostanwendung"
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# WPF-Host (PresentationHost.exe)
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Host \("PresentationHost.exe"\) ist die Anwendung, mit der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen in kompatiblen Browsern gehostet werden können \(einschließlich [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] und höher\).  Standardmäßig wird [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Host als Shell und [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]\-Handler für im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Inhalte registriert. Dazu zählen:  
  
-   Loose \(nicht kompilierte\) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Dateien \(.xaml\).  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] \(.xbap\).  
  
 Für diese Dateitypen führt [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Host Folgendes aus:  
  
-   Start des registrierten [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]\-Handlers, um die [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Inhalte zu hosten.  
  
-   Laden der entsprechenden Versionen der erforderlichen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Assembly und der [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Assembly.  
  
-   Überprüfen, ob die entsprechenden Berechtigungsstufen für die Bereitstellungszone aktiv sind.  
  
 In diesem Thema werden die Befehlszeilenparameter beschrieben, die mit PresentationHost.exe verwendet werden können.  
  
## Verwendung  
 `PresentationHost.exe [parameters] uri|filename`  
  
## Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|filename|Der Pfad der zu aktivierenden Datei.  Es kann sich auch um einen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] handeln.|  
|\-debug|Beim Aktivieren einer Anwendung wird diese nicht in den Speicher übernommen oder daraus ausgeführt.  Dies funktioniert nur, wenn eine lokale Datei aktiviert wird.|  
|\-debugSecurityZoneURL \<url\>|Wird mit einem [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]\-Wert verwendet, um für PresentationHost.exe anzugeben, dass eine Anwendung so gedebuggt werden sollte, als ob sie von der angegebenen [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] bereitgestellt werden sollte.  Dadurch werden die Bereitstellungszone und die Ursprungssite bestimmt.|  
|\-embedding|Wird von OLE benötigt.  Wenn der Parameter `-event` oder der Parameter `-debug` angegeben wird, ist es nicht nötig, den `-embedding`\-Parameter anzugeben, da dieser Parameter intern festgelegt wird.|  
|\-event \<Ereignisname\>|Öffnen Sie das Ereignis mit diesem Namen, und signalisieren Sie es, wenn PresentationHost.exe initialisiert wird und bereit ist, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Inhalte zu hosten.  PresentationHost.exe wird beendet, wenn beim Öffnen des Ereignisses ein Fehler auftritt, z. B. wenn es noch nicht erstellt wurde.|  
|\-launchApplication \<url\>|Startet eine eigenständige [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]\-Anwendung unter Verwendung der angegebenen URL.  [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] und WinInet\-Sicherheitsrichtlinie für .NET\-Anwendungen werden angewendet.|  
  
## Szenarien  
  
### Shell\-Handler  
 `PresentationHost.exe example.xbap`  
  
### MIME\-Handler  
 `PresentationHost.exe -embedding example.xbap`  
  
### Debuggen in Visual Studio  
 `PresentationHost.exe -debug example.xbap`  
  
### Visual Studio: Debuggen in einer Zone  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## Siehe auch  
 [Sicherheit](../../../../docs/framework/wpf/security-wpf.md)