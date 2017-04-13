---
title: "IWpfHostSupport | Microsoft Docs"
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
  - "IWpfHostSupport-Schnittstelle"
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# IWpfHostSupport
Anwendungen, die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Inhalte mithilfe von PresentationHost.exe hosten, implementieren diese Schnittstelle, um für den Host und PresentationHost.exe einen Integrationspunkt bereitzustellen.  
  
## Hinweise  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-Anwendungen, z. B. Webbrowser, können [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]\-Inhalt hosten, einschließlich [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] und lose XAML\-Daten.  Zum Hosten von [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]\-Inhalten erstellen [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-Anwendungen eine Instanz des [WebBrowser\-Steuerelements](http://go.microsoft.com/fwlink/?LinkId=97911) \(möglicherweise in englischer Sprache\).  Zum Hosten erstellt [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] eine Instanz von PresentationHost.exe, über die der gehostete [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]\-Inhalt dem Host zur Anzeige im [WebBrowser\-Steuerelement](http://go.microsoft.com/fwlink/?LinkId=97911) bereitgestellt wird.  
  
 Die von `IWpfHostSupport` aktivierte Integration ermöglicht für PresentationHost.exe Folgendes:  
  
-   Erkennen der und Registrieren bei den Geräten für die unformatierte Eingabe \(Human Interface Device\), die für die Hostanwendung von Bedeutung sind  
  
-   Empfangen von Eingabemeldungen von den registrierten Geräten für die unformatierte Eingabe und Weiterleiten von entsprechenden Meldungen an die Hostanwendung  
  
-   Abfragen der Hostanwendung nach benutzerdefinierten Benutzeroberflächen zur Fortschritts\- und Fehleranzeige  
  
> [!NOTE]
>  Diese API ist lediglich zur Verwendung auf dem lokalen Clientcomputer gedacht und wird nur dafür unterstützt.  
  
## Mitglieder  
  
|Member|Beschreibung|  
|------------|------------------|  
|[GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|Ermöglicht PresentationHost.exe die Erkennung der Geräte für die unformatierte Eingabe \(Human Interface Device\), die für die Hostanwendung von Bedeutung sind.|  
|[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|Wird von der Datei PresentationHost.exe aufgerufen, wenn eine Meldung empfangen wird, sofern nicht E\_NOTIMPL zurückgegeben wird.|  
|[GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)|Standardmäßig verfügt PresentationHost.exe über eigene Benutzeroberflächen zur Anzeige von Bereitstellungsfortschritt und \-fehlern, die beim Bereitstellen von WPF\-Inhalten angezeigt werden.|