---
title: 'Gewusst wie: Erkennen einer Installation des WPF-Plug-Ins für Firefox'
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: ba411d662a8e5b0c4727e23c8d507e8924b6e9e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Gewusst wie: Erkennen einer Installation des WPF-Plug-Ins für Firefox
Der Windows Presentation Foundation-Plug-In für Firefox (WPF) können [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] und loose XAML-Dateien in den Mozilla Firefox-Browser ausgeführt werden. Dieses Thema enthält ein Skript geschrieben in HTML und JavaScript, die Administratoren verwenden können, um zu bestimmen, ob das WPF-Plug-In für Firefox installiert ist.  
  
> [!NOTE]
>  Weitere Informationen zum Installieren und Bereitstellen von erkennen die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], finden Sie unter [installieren Sie .NET Framework für Entwickler](../../../../docs/framework/install/guide-for-developers.md).  
  
## <a name="example"></a>Beispiel  
 Wenn die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] ist installiert, der Clientcomputer mit einem WPF-Plug-In für Firefox konfiguriert ist. Das folgende Beispielskript überprüft das WPF-Plug-In für Firefox und zeigt dann eine Nachricht des entsprechenden Status.  
  
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
  
 Wenn das Kontrollkästchen für die WPF-Plug-In für Firefox erfolgreich ist, wird die folgende Statusmeldung angezeigt:  
  
 `The WPF plug-in for Firefox is installed.`  
  
 Andernfalls wird die folgende Statusmeldung angezeigt:  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a>Siehe auch  
 [Erkennen einer .NET Framework 3.0-Installation](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [Erkennen einer .NET Framework 3.5-Installation](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [Übersicht über WPF-XAML-Browseranwendungen](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
