---
title: Erkennen, ob das WPF-Plug-in für Firefox installiert ist
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: 91680859c1742e5d5443d626c81273a80504f4a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740395"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Gewusst wie: Erkennen einer Installation des WPF-Plug-Ins für Firefox

Das Windows Presentation Foundation (WPF)-Plug-in für Firefox ermöglicht, dass XAML-Browser Anwendungen (XBAPs) und lose XAML-Dateien im Mozilla Firefox-Browser ausgeführt werden. Dieses Thema enthält ein in HTML und JavaScript geschriebenes Skript, mit dem Administratoren ermitteln können, ob das WPF-Plug-in für Firefox installiert ist.

> [!NOTE]
> Weitere Informationen zum Installieren, bereitstellen und ermitteln der .NET Framework finden Sie unter [Installieren des .NET Framework für Entwickler](../../install/guide-for-developers.md).

## <a name="example"></a>Beispiel

Wenn die .NET Framework 3,5 installiert ist, wird der Client Computer mit einem WPF-Plug-in für Firefox konfiguriert. Das folgende Beispielskript überprüft das WPF-Plug-in für Firefox und zeigt dann eine entsprechende Statusmeldung an.

```html
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

Wenn die Überprüfung auf das WPF-Plug-in für Firefox erfolgreich ist, wird die folgende Statusmeldung angezeigt:

`The WPF plug-in for Firefox is installed.`

Andernfalls wird die folgende Statusmeldung angezeigt:

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a>Weitere Informationen

- [Erkennen einer .NET Framework 3.0-Installation](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [Erkennen einer .NET Framework 3.5-Installation](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [Übersicht über WPF-XAML-Browseranwendungen](wpf-xaml-browser-applications-overview.md)
