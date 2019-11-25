---
title: 'Vorgehensweise: Hosten eines WCF-Diensts, der mit .NET Framework 3.5 unter IIS geschrieben wurde und unter .NET Framework 4 ausgeführt wird'
ms.date: 03/30/2017
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
ms.openlocfilehash: d827fe82e8b355c8818d96645b463c1840910a9c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283267"
---
# <a name="how-to-host-a-wcf-service-written-with-net-framework-35-in-iis-running-under-net-framework-4"></a><span data-ttu-id="84e11-102">Vorgehensweise: Hosten eines WCF-Diensts, der mit .NET Framework 3.5 unter IIS geschrieben wurde und unter .NET Framework 4 ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="84e11-102">How to: Host a WCF Service Written with .NET Framework 3.5 in IIS Running Under .NET Framework 4</span></span>

<span data-ttu-id="84e11-103">Beim Hosting eines Windows Communication Foundation (WCF)-Diensts, der mit .NET Framework 3,5 auf einem Computer mit .NET Framework 4 geschrieben wurde, erhalten Sie möglicherweise eine <xref:System.ServiceModel.ProtocolException> mit folgendem Text.</span><span class="sxs-lookup"><span data-stu-id="84e11-103">When hosting a Windows Communication Foundation (WCF) service written with .NET Framework 3.5 on a machine running .NET Framework 4, you may get a <xref:System.ServiceModel.ProtocolException> with the following text.</span></span>
  
```output  
Unhandled Exception: System.ServiceModel.ProtocolException: The content type text/html; charset=utf-8 of the response message does not match the content type of the binding (application/soap+xml; charset=utf-8). If using a custom encoder, be sure that the IsContentTypeSupported method is implemented properly. The first 1024 bytes of the response were: '<html>    <head>        <title>The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.</title>...  
```  
  
 <span data-ttu-id="84e11-104">Oder wenn Sie versuchen, auf die SVC-Datei des Diensts zuzugreifen, wird ggf. eine Fehlerseite mit dem folgenden Text angezeigt.</span><span class="sxs-lookup"><span data-stu-id="84e11-104">Or if you try to browse to the service's .svc file you may see an error page with the following text.</span></span>  
  
```output  
The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.  
```  
  
 <span data-ttu-id="84e11-105">Diese Fehler treten auf, weil die Anwendungsdomäne, in der IIS ausgeführt wird, .NET Framework 4 ausgeführt wird und der WCF-Dienst unter .NET Framework 3,5 ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="84e11-105">These errors occur because the application domain IIS is running within is running .NET Framework 4 and the WCF service is expecting to run under .NET Framework 3.5.</span></span> <span data-ttu-id="84e11-106">In diesem Thema werden die Änderungen erläutert, die für die Ausführung des Diensts erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="84e11-106">This topic explains the modifications required to get the service to run.</span></span>
  
 <span data-ttu-id="84e11-107">Suchen Sie als nächstes die <`compilers`>-Element, und ändern Sie die Option für den Compilerversion-Anbieter, sodass der Wert 4,0 lautet.</span><span class="sxs-lookup"><span data-stu-id="84e11-107">Next find the <`compilers`> element and change the CompilerVersion provider option to have a value of 4.0.</span></span> <span data-ttu-id="84e11-108">Standardmäßig sind zwei <`compiler`> Elemente unter dem <`compilers`> Element vorhanden.</span><span class="sxs-lookup"><span data-stu-id="84e11-108">By default, there are two <`compiler`> elements under the <`compilers`> element.</span></span> <span data-ttu-id="84e11-109">Sie müssen die Option für den CompilerVersion-Anbieter für beide Elemente aktualisieren. Dies wird im folgenden Beispiel veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="84e11-109">You must update the CompilerVersion provider option for both as shown in the following example.</span></span>  
  
```xml  
<system.codedom>  
      <compilers>  
        <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                  type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
        <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                  type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="OptionInfer" value="true"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
      </compilers>  
    </system.codedom>  
```  
  
### <a name="add-the-required-targetframework-attribute"></a><span data-ttu-id="84e11-110">Hinzufügen des erforderlichen targetFramework-Attributs</span><span class="sxs-lookup"><span data-stu-id="84e11-110">Add the required targetFramework attribute</span></span>  
  
1. <span data-ttu-id="84e11-111">Öffnen Sie die Datei Web. config des Diensts, und suchen Sie nach dem <`compilation`>-Element.</span><span class="sxs-lookup"><span data-stu-id="84e11-111">Open the service's Web.config file and look for the <`compilation`> element.</span></span>  
  
2. <span data-ttu-id="84e11-112">Fügen Sie das `targetFramework`-Attribut der <`compilation`>-Element hinzu, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="84e11-112">Add the `targetFramework` attribute to the <`compilation`> element as shown in the following example.</span></span>  
  
    ```xml  
    <compilation debug="false"  
            targetFramework="4.0">  
  
            <assemblies>  
              <add assembly="System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Xml.Linq, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35"/>  
              <add assembly="System.Data.DataSetExtensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
            </assemblies>  
  
          </compilation>  
    ```  
  
3. <span data-ttu-id="84e11-113">Suchen Sie das <`compilers`>-Element, und ändern Sie die Option für den Compilerversion-Anbieter so, dass der Wert 4,0 lautet.</span><span class="sxs-lookup"><span data-stu-id="84e11-113">Find the <`compilers`> element and change the CompilerVersion provider option to have a value of 4.0.</span></span> <span data-ttu-id="84e11-114">Standardmäßig sind zwei <`compiler`> Elemente unter dem <`compilers`> Element vorhanden.</span><span class="sxs-lookup"><span data-stu-id="84e11-114">By default, there are two <`compiler`> elements under the <`compilers`> element.</span></span> <span data-ttu-id="84e11-115">Sie müssen die Option für den CompilerVersion-Anbieter für beide Elemente aktualisieren. Dies wird im folgenden Beispiel veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="84e11-115">You must update the CompilerVersion provider option for both as shown in the following example.</span></span>  
  
    ```xml  
    <system.codedom>  
          <compilers>  
            <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                      type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
            <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                      type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="OptionInfer" value="true"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
          </compilers>  
        </system.codedom>  
    ```
