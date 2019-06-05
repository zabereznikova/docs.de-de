---
title: 'Vorgehensweise: Erkennen einer .NET Framework 3.5-Installation'
ms.date: 03/30/2017
helpviewer_keywords:
- verifying whether.NET Framework 3.5 is installed [WPF]
- detecting .NET Framework 3.5 installation [WPF]
- detecting whether.NET Framework 3.5 is installed [WPF]
- determining whether.NET Framework 3.5 is installed [WPF]
ms.assetid: 8556a9d2-1eb8-48ef-919c-5baf22a2a9a2
ms.openlocfilehash: 69dfa0eb8d9ad9b780d258a874d255484f270cfe
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690433"
---
# <a name="how-to-detect-whether-the-net-framework-35-is-installed"></a>Vorgehensweise: Erkennen einer .NET Framework 3.5-Installation
Bevor Administratoren Windows Presentation Foundation (WPF)-Anwendungen auf einem System, die .NET Framework 3.5 ausgerichtet ist bereitstellen können, müssen sie bestätigen, dass die .NET Framework 3.5-Laufzeit vorhanden ist. Dieses Thema enthält ein Skript in HTML/JavaScript geschrieben wurde, dass Administratoren verwenden können, um zu bestimmen, ob .NET Framework 3.5 auf einem System vorhanden ist.  
  
> [!NOTE]
>  Ausführlichere Informationen zum Installieren von bereitstellen und Erkennen von .NET Framework finden Sie unter [Installieren von .NET Framework für Entwickler](../../install/guide-for-developers.md).  
  
## <a name="example"></a>Beispiel  
 Wenn .NET Framework 3.5 installiert ist, fügt die MSI-Datei ".NET CLR" und die Versionsnummer der Zeichenfolge "UserAgent" hinzu. Das folgende Beispiel zeigt ein Skript in einer einfachen HTML-Seite eingebettet. Das Skript sucht die Zeichenfolge "UserAgent", um zu bestimmen, ob .NET Framework 3.5 installiert ist, und zeigt eine Statusmeldung angezeigt wird, auf die Ergebnisse der Suche.  
  
> [!NOTE]
>  Dieses Skript dient für Internet Explorer. Andere Browser können die .NET CLR-Informationen nicht in der Zeichenfolge "UserAgent" enthalten.  
  
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
  
 Wenn die Suche nach der Version ".NET CLR" erfolgreich ist, wird der folgende Typ der Statusmeldung angezeigt:  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 Andernfalls wird der folgende Typ der Statusmeldung angezeigt:  
  
 `This machine does not have the correct version of the .NET Framework 3.5. The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## <a name="see-also"></a>Siehe auch

- [Erkennen einer .NET Framework 3.0-Installation](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
