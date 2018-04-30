---
title: 'Gewusst wie: Erkennen einer Installation des WPF-Plug-Ins für Firefox'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2b58abda33aa48372e4642dca48599867f389045
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="bdf2e-102">Gewusst wie: Erkennen einer Installation des WPF-Plug-Ins für Firefox</span><span class="sxs-lookup"><span data-stu-id="bdf2e-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>
<span data-ttu-id="bdf2e-103">Der Windows Presentation Foundation-Plug-In für Firefox (WPF) können [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] und loose XAML-Dateien in den Mozilla Firefox-Browser ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bdf2e-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="bdf2e-104">Dieses Thema enthält ein Skript geschrieben in HTML und JavaScript, die Administratoren verwenden können, um zu bestimmen, ob das WPF-Plug-In für Firefox installiert ist.</span><span class="sxs-lookup"><span data-stu-id="bdf2e-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdf2e-105">Weitere Informationen zum Installieren und Bereitstellen von erkennen die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], finden Sie unter [installieren Sie .NET Framework für Entwickler](../../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="bdf2e-105">For more information about installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdf2e-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bdf2e-106">Example</span></span>  
 <span data-ttu-id="bdf2e-107">Wenn die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] ist installiert, der Clientcomputer mit einem WPF-Plug-In für Firefox konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="bdf2e-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="bdf2e-108">Das folgende Beispielskript überprüft das WPF-Plug-In für Firefox und zeigt dann eine Nachricht des entsprechenden Status.</span><span class="sxs-lookup"><span data-stu-id="bdf2e-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>  
  
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
  
 <span data-ttu-id="bdf2e-109">Wenn das Kontrollkästchen für die WPF-Plug-In für Firefox erfolgreich ist, wird die folgende Statusmeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bdf2e-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is installed.`  
  
 <span data-ttu-id="bdf2e-110">Andernfalls wird die folgende Statusmeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bdf2e-110">Otherwise, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a><span data-ttu-id="bdf2e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdf2e-111">See Also</span></span>  
 [<span data-ttu-id="bdf2e-112">Erkennen einer .NET Framework 3.0-Installation</span><span class="sxs-lookup"><span data-stu-id="bdf2e-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [<span data-ttu-id="bdf2e-113">Erkennen einer .NET Framework 3.5-Installation</span><span class="sxs-lookup"><span data-stu-id="bdf2e-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [<span data-ttu-id="bdf2e-114">Übersicht über WPF-XAML-Browseranwendungen</span><span class="sxs-lookup"><span data-stu-id="bdf2e-114">WPF XAML Browser Applications Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
