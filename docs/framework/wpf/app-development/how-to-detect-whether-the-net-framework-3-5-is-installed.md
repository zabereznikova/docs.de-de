---
title: 'Vorgehensweise: erkennen, ob .NET Framework 3.5 installiert ist'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- verifying whether.NET Framework 3.5 is installed [WPF]
- detecting .NET Framework 3.5 installation [WPF]
- detecting whether.NET Framework 3.5 is installed [WPF]
- determining whether.NET Framework 3.5 is installed [WPF]
ms.assetid: 8556a9d2-1eb8-48ef-919c-5baf22a2a9a2
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b603bbd86bb5eb12782ff8aff7797b73444b8518
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-detect-whether-the-net-framework-35-is-installed"></a>Vorgehensweise: erkennen, ob .NET Framework 3.5 installiert ist
Bevor Administratoren bereitstellen, können [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Anwendungen auf einem System, das als Ziel verwendet die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], müssen sie zunächst bestätigen, dass die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] Common Language Runtime vorhanden ist. Dieses Thema enthält ein Skript geschrieben in HTML/JavaScript, die Administratoren verwenden können, um zu bestimmen, ob die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] auf einem System vorhanden ist.  
  
> [!NOTE]
>  Ausführlichere Informationen zum Installieren, bereitstellen und Erkennen von der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], finden Sie unter [installieren Sie .NET Framework für Entwickler](../../../../docs/framework/install/guide-for-developers.md).  
  
## <a name="example"></a>Beispiel  
 Wenn die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] ist installiert, die MSI-Datei ".NET CLR" und die Versionsnummer der UserAgent Zeichenfolge hinzugefügt. Das folgende Beispiel zeigt ein Skript in einen einfachen HTML-Seite eingebettet. Das Skript durchsucht die UserAgent-Zeichenfolge, um zu bestimmen, ob die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] installiert ist, und zeigt eine Statusmeldung an, auf dem die Ergebnisse der Suche.  
  
> [!NOTE]
>  Dieses Skript dient für Internet Explorer. Andere Browser können .NET CLR-Informationen nicht in der UserAgent-Zeichenfolge enthalten.  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.5</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.5.0.0";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.5."  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.5." +  
          " The required version is v" + dotNETRuntimeVersion + ".";  
      }  
      result.innerText += "\n\nThis machine's userAgent string is: " +   
        navigator.userAgent + ".";  
    }  
  
    //  
    // Retrieve the version from the user agent string and   
    // compare with the specified version.  
    //  
    function HasRuntimeVersion(versionToCheck)  
    {  
      var userAgentString =   
        navigator.userAgent.match(/.NET CLR [0-9.]+/g);  
  
      if (userAgentString != null)  
      {  
        var i;  
  
        for (i = 0; i < userAgentString.length; ++i)  
        {  
          if (CompareVersions(GetVersion(versionToCheck),   
            GetVersion(userAgentString[i])) <= 0)  
            return true;  
        }  
      }  
  
      return false;  
    }  
  
    //  
    // Extract the numeric part of the version string.  
    //  
    function GetVersion(versionString)  
    {  
      var numericString =   
        versionString.match(/([0-9]+)\.([0-9]+)\.([0-9]+)/i);  
      return numericString.slice(1);  
    }  
  
    //  
    // Compare the 2 version strings by converting them to numeric format.  
    //  
    function CompareVersions(version1, version2)  
    {  
      for (i = 0; i < version1.length; ++i)  
      {  
        var number1 = new Number(version1[i]);  
        var number2 = new Number(version2[i]);  
  
        if (number1 < number2)  
          return -1;  
  
        if (number1 > number2)  
          return 1;  
      }  
  
      return 0;  
    }  
  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY>  
    <div id="result" />  
  </BODY>  
</HTML>  
```  
  
 Wenn die Suche nach der Version ".NET CLR" erfolgreich ist, wird die folgende Art von Meldung mit dem Status angezeigt:  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 Andernfalls wird folgende Art von Meldung mit dem Status angezeigt:  
  
 `This machine does not have the correct version of the .NET Framework 3.5. The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## <a name="see-also"></a>Siehe auch  
 [Erkennen einer .NET Framework 3.0-Installation](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)
