---
title: "Gewusst wie: Erkennen einer Installation des WPF-Plug-Ins f&#252;r Firefox | Microsoft Docs"
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
  - "Suchen nach dem Firefox-Plug-In [WPF]"
  - "Erkennen einer Firefox-Installation [WPF]"
  - "Erkennen einer Installation des WPF-Plug-Ins für Firefox [WPF]"
  - "Firefox [WPF], Erkennen einer Installation"
  - "Plug-In für Firefox [WPF]"
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erkennen einer Installation des WPF-Plug-Ins f&#252;r Firefox
Das [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Plug\-In für Firefox ermöglicht die Ausführung von [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] und Loose XAML\-Dateien im Browser Mozilla Firefox.  In diesem Thema wird ein in HTML und JavaScript geschriebenes Skript bereitgestellt, mit dem Administratoren ermitteln können, ob das WPF\-Plug\-In für Firefox installiert ist.  
  
> [!NOTE]
>  Weitere Informationen zum Installieren, Bereitstellen und Erkennen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] finden Sie unter [Installieren von .NET Framework](../../../../docs/framework/install/guide-for-developers.md).  
  
## Beispiel  
 Wenn [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] installiert ist, wird der Clientcomputer mit einem WPF\-Plug\-In für Firefox konfiguriert.  Das folgende Beispielskript sucht das WPF\-Plug\-In für Firefox und zeigt dann eine entsprechende Statusmeldung an.  
  
```  
<HTML>  
  
  <HEAD>  
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT type="text/javascript">  
    <!--  
    function OnLoad()  
    {  
  
       // Check for the WPF plug-in for Firefox and report  
       var msg = "The WPF plug-in for Firefox is ";  
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];  
       if( wpfPlugin != null ) {  
          document.writeln(msg + " installed.");  
       }  
       else {  
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");  
       }  
    }  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY onload="OnLoad()" />  
  
</HTML>  
```  
  
 Bei erfolgreicher Suche nach dem WPF\-Plug\-In für Firefox wird die folgende Statusmeldung angezeigt:  
  
 `The WPF plug-in for Firefox is installed.`  
  
 Andernfalls wird die folgende Statusmeldung angezeigt:  
  
 `The WPF plug-in for Firefox is not installed.  Please install or reinstall the .NET Framework 3.5.`  
  
## Siehe auch  
 [Erkennen einer .NET Framework 3.0\-Installation](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)   
 [Erkennen einer .NET Framework 3.5\-Installation](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)   
 [Übersicht über WPF\-XAML\-Browseranwendungen](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)