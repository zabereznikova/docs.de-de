---
title: 'Vorgehensweise: Erkennen einer .NET Framework 3.5-Installation'
ms.date: 03/30/2017
helpviewer_keywords:
- verifying whether.NET Framework 3.5 is installed [WPF]
- detecting .NET Framework 3.5 installation [WPF]
- detecting whether.NET Framework 3.5 is installed [WPF]
- determining whether.NET Framework 3.5 is installed [WPF]
ms.assetid: 8556a9d2-1eb8-48ef-919c-5baf22a2a9a2
ms.openlocfilehash: 18e5c819eb4deb62208280816d11dce0940d134d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053430"
---
# <a name="how-to-detect-whether-the-net-framework-35-is-installed"></a><span data-ttu-id="e6347-102">Vorgehensweise: Erkennen einer .NET Framework 3.5-Installation</span><span class="sxs-lookup"><span data-stu-id="e6347-102">How to: Detect Whether the .NET Framework 3.5 Is Installed</span></span>
<span data-ttu-id="e6347-103">Bevor Administratoren Windows Presentation Foundation (WPF)-Anwendungen auf einem System bereitstellen können, das auf das .NET Framework 3,5 abzielt, müssen Sie zunächst bestätigen, dass die .NET Framework 3,5-Laufzeit vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e6347-103">Before administrators can deploy Windows Presentation Foundation (WPF) applications on a system that targets the .NET Framework 3.5, they must first confirm that the .NET Framework 3.5 runtime is present.</span></span> <span data-ttu-id="e6347-104">Dieses Thema enthält ein in HTML/JavaScript geschriebenes Skript, mit dem Administratoren ermitteln können, ob die .NET Framework 3,5 in einem System vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e6347-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether the .NET Framework 3.5 is present on a system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6347-105">Ausführlichere Informationen zum Installieren, bereitstellen und Ermitteln des .NET Framework finden Sie unter [Installieren des .NET Framework für Entwickler](../../install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="e6347-105">For more detailed information on installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6347-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6347-106">Example</span></span>  
 <span data-ttu-id="e6347-107">Wenn die .NET Framework 3,5 installiert ist, fügt die msi ".NET CLR" und die Versionsnummer der UserAgent-Zeichenfolge hinzu.</span><span class="sxs-lookup"><span data-stu-id="e6347-107">When the .NET Framework 3.5 is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="e6347-108">Das folgende Beispiel zeigt ein Skript, das in eine einfache HTML-Seite eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="e6347-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="e6347-109">Das Skript durchsucht die UserAgent-Zeichenfolge, um zu bestimmen, ob die .NET Framework 3,5 installiert ist, und zeigt eine Statusmeldung für die Ergebnisse der Suche an.</span><span class="sxs-lookup"><span data-stu-id="e6347-109">The script searches the UserAgent string to determine whether the .NET Framework 3.5 is installed, and displays a status message on the results of the search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6347-110">Dieses Skript ist für Internet Explorer konzipiert.</span><span class="sxs-lookup"><span data-stu-id="e6347-110">This script is designed for Internet Explorer.</span></span> <span data-ttu-id="e6347-111">Andere Browser enthalten möglicherweise keine .NET CLR-Informationen in der UserAgent-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e6347-111">Other browsers may not include .NET CLR information in the UserAgent string.</span></span>  
  
```html  
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
  
 <span data-ttu-id="e6347-112">Wenn die Suche nach der ".NET CLR"-Version erfolgreich ist, wird der folgende Typ der Statusmeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e6347-112">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 <span data-ttu-id="e6347-113">Andernfalls wird der folgende Typ der Statusmeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e6347-113">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have the correct version of the .NET Framework 3.5. The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## <a name="see-also"></a><span data-ttu-id="e6347-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6347-114">See also</span></span>

- [<span data-ttu-id="e6347-115">Erkennen einer .NET Framework 3.0-Installation</span><span class="sxs-lookup"><span data-stu-id="e6347-115">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
