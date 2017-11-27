---
title: 'Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 83b004934c303c95bdc4e6edb6031a86e2b1a6ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a>Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung
Ab [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] werden beim Kompilieren von Apps, die auf [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] abzielen, Bindungsumleitungen automatisch zur App-Konfigurationsdatei hinzugefügt, um die Assemblyvereinheitlichung zu überschreiben. Bindungsumleitungen werden hinzugefügt, wenn die App oder ihre Komponenten auf mehr als eine Version der gleichen Assembly verweisen, auch wenn Sie manuell Bindungsumleitungen in der Konfigurationsdatei für Ihre App angeben. Die automatische Bindungsumleitung wirkt sich auf herkömmliche Desktop-Apps und Web-Apps aus, die auf [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] abzielen, obwohl das Verhalten für eine Web-App etwas anders ist. Sie können die automatische Bindungsumleitung aktivieren, wenn Sie über Apps verfügen, die auf frühere Versionen von .NET Framework abzielen, oder Sie können diese Funktion deaktivieren, wenn Sie manuell erstellte Bindungsumleitungen beibehalten möchten.  
  
## <a name="disabling-automatic-binding-redirects-in-desktop-apps"></a>Deaktivieren der automatischen Bindungsumleitungen in Desktop-Apps  
 Automatische Bindungsumleitungen sind bei herkömmlichen Desktop-Apps, die auf [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] und spätere Versionen abzielen, standardmäßig aktiviert. Die Bindungsumleitungen werden der Ausgabekonfigurationsdatei (app.config) beim Kompilieren der App hinzugefügt, und die Assemblyvereinheitlichung wird überschrieben, die sonst erfolgen würde. Die app.config-Quelldatei wird nicht geändert. Sie können diese Funktion deaktivieren, indem Sie die Projektdatei für Ihre App ändern.  
  
#### <a name="to-disable-automatic-binding-redirects"></a>So deaktivieren Sie automatische Bindungsumleitungen  
  
1.  Wählen Sie in Visual Studio das Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Ordner in Datei-Explorer öffnen** aus dem Kontextmenü.  
  
2.  Suchen Sie im Datei-Explorer die Projektdatei (CSPROJ oder VBPROJ), und öffnen Sie sie im Editor.  
  
3.  Suchen Sie in der Projektdatei den folgende Eigenschafteneintrag:  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
4.  Ändern Sie `true` in `false`:  
  
     `<AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>`  
  
## <a name="enabling-automatic-binding-redirects-manually"></a>Manuelles Aktivieren von automatischen Bindungsumleitungen  
 Sie können automatische Bindungsumleitungen in vorhandenen Apps aktivieren, die auf frühere Versionen von .NET Framework abzielen, oder in Fällen, in denen Sie nicht automatisch zum Hinzufügen einer Umleitung aufgefordert werden. Wenn Sie auf eine neuere Version des Frameworks abzielen, aber nicht automatisch zum Hinzufügen einer Umleitung aufgefordert werden, erhalten Sie wahrscheinlich eine Buildausgabe, die das Zuordnen der Assemblys vorschlägt.  
  
#### <a name="to-manually-add-an-automatic-binding-redirect-property"></a>So fügen Sie eine Eigenschaft für manuelle Bindungsumleitungen hinzu  
  
1.  Wählen Sie in Visual Studio das Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Ordner in Datei-Explorer öffnen** aus dem Kontextmenü.  
  
2.  Suchen Sie im Datei-Explorer die Projektdatei (CSPROJ oder VBPROJ), und öffnen Sie sie im Editor.  
  
3.  Fügen Sie das folgende Element zur ersten konfigurationseigenschaftengruppe hinzu (unter der \<PropertyGroup >-Tag):  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
     Im Folgenden sehen Sie eine beispielhafte Projektdatei mit dem eingefügten Element.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == ''     ">Debug</Configuration>  
        <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>  
        <ProjectGuid>{123334}</ProjectGuid>  
        ...  
        <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>  
      </PropertyGroup>  
    ...  
    </Project>  
    ```  
  
4.  Kompilieren Sie Ihre App.  
  
## <a name="enabling-automatic-binding-redirects-in-web-apps"></a>Aktivieren von automatischen Bindungsumleitungen in Web-Apps  
 Bei Web-Apps werden automatische Bindungsumleitungen auf andere Weise implementiert. Da bei Web-Apps die Quellkonfigurationsdatei (web.config) geändert werden muss, werden Bindungsumleitungen nicht automatisch zur Konfigurationsdatei hinzugefügt. Allerdings benachrichtigt Visual Studio Sie bei Bindungskonflikten, und Sie können Bindungsumleitungen hinzufügen, um die Konflikte zu lösen. Da Sie immer zum Hinzufügen Bindungsumleitungen aufgefordert werden, müssen Sie diese Funktion bei einer Web-App nicht explizit deaktivieren.  
  
#### <a name="to-add-binding-redirects-to-a-webconfig-file"></a>So fügen Sie Bindungsumleitungen zu einer web.config-Datei hinzu  
  
1.  Kompilieren Sie die Anwendung in Visual Studio, und prüfen Sie, ob Buildwarnungen vorliegen.  
  
     ![Buildwarnung für assemblyverweiskonflikte](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")  
  
2.  Wenn Konflikte für eine Assemblybindung bestehen, wird eine Warnung angezeigt. Doppelklicken Sie auf die Warnung. (Tastatur: Wählen Sie den Warnhinweis, und drücken Sie **EINGABETASTE**.)  
  
     Ein Dialogfeld, in dem Sie die erforderlichen Bindungsumleitungen automatisch zur „web.config“-Quelldatei hinzufügen können, wird angezeigt.  
  
     ![Dialogfeld für die bindungsumleitung Berechtigung](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")  
  
## <a name="see-also"></a>Siehe auch  
 [\<BindingRedirect >-Element](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
 [Umleiten von Assemblyversionen](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
