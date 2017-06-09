---
title: "Vorgehensweise: Hosten eines WCF-Diensts, der mit .NET Framework 3.5 unter IIS geschrieben wurde und unter .NET Framework 4 ausgef&#252;hrt wird | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Vorgehensweise: Hosten eines WCF-Diensts, der mit .NET Framework 3.5 unter IIS geschrieben wurde und unter .NET Framework 4 ausgef&#252;hrt wird
Wenn Sie einen mit [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)] geschriebenen [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Dienst auf einem Computer hosten, auf dem [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] ausgeführt wird, erhalten Sie ggf. eine <xref:System.ServiceModel.ProtocolException> mit dem folgenden Text.  
  
```Output  
Unhandled Exception: System.ServiceModel.ProtocolException: The content type text/html; charset=utf-8 of the response message does not match the content type of the binding (application/soap+xml; charset=utf-8).If using a custom encoder, be sure that the IsContentTypeSupported method is implemented properly.The first 1024 bytes of the response were: '<html>    <head>        <title>The application domain or application pool is currently running version 4.0 or later of the .NET Framework.This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server.The <compilation> element in the Web.config file for this Web application does not contain the required'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">').Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.</title>...  
```  
  
 Oder wenn Sie versuchen, auf die SVC\-Datei des Diensts zuzugreifen, wird ggf. eine Fehlerseite mit dem folgenden Text angezeigt.  
  
```Output  
The application domain or application pool is currently running version 4.0 or later of the .NET Framework.This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server.The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">').Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.  
```  
  
 Diese Fehler treten auf, weil die Anwendungsdomänen, unter denen IIS ausgeführt wird, [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] ausführen. Der WCF\-Dienst erwartet jedoch die Ausführung unter [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].In diesem Thema werden die Änderungen erläutert, die für die Ausführung des Diensts erforderlich sind.  
  
 Suchen Sie als Nächstes nach dem \<`compilers`\>\-Element, und ändern Sie die Option für den CompilerVersion\-Anbieter so, dass sie den Wert 4.0 aufweist.Standardmäßig sind unter dem \<`compilers`\>\-Element zwei \<`compiler`\>\-Elemente vorhanden.Sie müssen die Option für den CompilerVersion\-Anbieter für beide Elemente aktualisieren. Dies wird im folgenden Beispiel veranschaulichen.  
  
```  
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
  
### Hinzufügen des erforderlichen targetFramework\-Attributs  
  
1.  Öffnen Sie die Web.config\-Datei des Diensts, und suchen Sie nach dem \<`compilation`\>\-Element.  
  
2.  Fügen Sie dem \<`compilation`\>\-Element das `targetFramework`\-Attribut hinzu, wie im folgenden Beispiel gezeigt.  
  
    ```  
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
  
3.  Suchen Sie nach dem \<`compilers`\>\-Element, und ändern Sie die Option für den CompilerVersion\-Anbieter so, dass sie den Wert 4.0 aufweist.Standardmäßig sind unter dem \<`compilers`\>\-Element zwei \<`compiler`\>\-Elemente vorhanden.Sie müssen die Option für den CompilerVersion\-Anbieter für beide Elemente aktualisieren. Dies wird im folgenden Beispiel veranschaulichen.  
  
    ```  
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