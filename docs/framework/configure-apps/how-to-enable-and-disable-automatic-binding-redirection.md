---
title: 'Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung'
ms.date: 09/12/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: cf38bd753127e40c61512411c7aa2ebbbd7687db
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45618665"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a>Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung

Beim Kompilieren von apps in Visual Studio, die auf die [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] und höhere Versionen werden bindungsumleitungen werden automatisch hinzugefügt, um die app-Konfigurationsdatei für die Assemblyvereinheitlichung zu überschreiben. Bindungsumleitungen werden hinzugefügt, wenn die App oder ihre Komponenten auf mehr als eine Version der gleichen Assembly verweisen, auch wenn Sie manuell Bindungsumleitungen in der Konfigurationsdatei für Ihre App angeben. Die automatische bindungsumleitung wirkt sich auf herkömmliche desktop-apps und Web-apps, die auf die [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] oder eine höhere Version, obwohl das Verhalten für eine Web-app etwas anders ist. Sie können die automatische Bindungsumleitung aktivieren, wenn Sie über Apps verfügen, die auf frühere Versionen von .NET Framework abzielen, oder Sie können diese Funktion deaktivieren, wenn Sie manuell erstellte Bindungsumleitungen beibehalten möchten.

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a>Deaktivieren Sie automatische bindungsumleitungen in desktop-apps

Automatische Bindungsumleitungen sind bei herkömmlichen Desktop-Apps, die auf [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] und spätere Versionen abzielen, standardmäßig aktiviert. Die Bindungsumleitungen werden der Ausgabekonfigurationsdatei (app.config) beim Kompilieren der App hinzugefügt, und die Assemblyvereinheitlichung wird überschrieben, die sonst erfolgen würde. Die app.config-Quelldatei wird nicht geändert. Sie können diese Funktion deaktivieren, indem Sie die Projektdatei für Ihre App ändern.

1. Öffnen Sie die Projektdatei für die Bearbeitung mit einem der folgenden Methoden:

   - Wählen Sie in Visual Studio das Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Ordner in Datei-Explorer öffnen** aus dem Kontextmenü. Klicken Sie im Datei-Explorer finden Sie die Projektdatei (CSPROJ oder VBPROJ), und öffnen sie im Editor.
   - In Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Projekt entladen**. Mit der rechten Maustaste erneut auf des entladen Projekts, und wählen Sie dann **bearbeiten [Projektname.csproj]**.

2. Suchen Sie in der Projektdatei den folgende Eigenschafteneintrag:

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. Ändern Sie `true` in `false`:

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a>Aktivieren Sie automatische bindungsumleitungen manuell

Sie können automatische bindungsumleitungen in vorhandenen apps ermöglichen dieses Ziel in älteren Versionen von .NET Framework oder in Fällen, in denen Sie nicht automatisch aufgefordert werden, Hinzufügen einer Umleitung. Wenn Sie eine neuere Version des Frameworks abzielen, jedoch werden nicht automatisch zum Hinzufügen einer Umleitung aufgefordert, erhalten Sie wahrscheinlich Buildausgabe, die schlägt vor, dass Sie die Assemblys neu zuordnen.

1. Öffnen Sie die Projektdatei für die Bearbeitung mit einem der folgenden Methoden:

   - Wählen Sie in Visual Studio das Projekt im **Projektmappen-Explorer**, und wählen Sie dann **Ordner in Datei-Explorer öffnen** aus dem Kontextmenü. Klicken Sie im Datei-Explorer finden Sie die Projektdatei (CSPROJ oder VBPROJ), und öffnen sie im Editor.
   - In Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Projekt entladen**. Mit der rechten Maustaste erneut auf des entladen Projekts, und wählen Sie dann **bearbeiten [Projektname.csproj]**.

2. Das folgende Element hinzufügen, um den ersten konfigurationseigenschaftengruppe (unter der \<PropertyGroup > Tag):

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   Das folgende Beispiel zeigt eine beispielhafte Projektdatei mit dem eingefügten Element:

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

3. Kompilieren Sie Ihre App.

## <a name="enable-automatic-binding-redirects-in-web-apps"></a>Aktivieren Sie automatische bindungsumleitungen in Web-apps

Bei Web-Apps werden automatische Bindungsumleitungen auf andere Weise implementiert. Da bei Web-Apps die Quellkonfigurationsdatei (web.config) geändert werden muss, werden Bindungsumleitungen nicht automatisch zur Konfigurationsdatei hinzugefügt. Allerdings benachrichtigt Visual Studio Sie bei Bindungskonflikten, und Sie können Bindungsumleitungen hinzufügen, um die Konflikte zu lösen. Da Sie immer zum Hinzufügen bindungsumleitungen aufgefordert werden, müssen Sie nicht explizit deaktivieren Sie dieses Feature für eine Web-app.

So fügen Sie bindungsumleitungen in eine Datei "Web.config" hinzu:

1. Kompilieren Sie die Anwendung in Visual Studio, und prüfen Sie, ob Buildwarnungen vorliegen.

   ![Buildwarnung für assemblyverweiskonflikte](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")

2. Wenn Konflikte für eine Assemblybindung bestehen, wird eine Warnung angezeigt. Doppelklicken Sie auf die Warnung aus, oder wählen Sie den Warnhinweis, und drücken Sie **EINGABETASTE**.

   Ein Dialogfeld, in dem Sie die erforderlichen Bindungsumleitungen automatisch zur „web.config“-Quelldatei hinzufügen können, wird angezeigt.

   ![Dialogfeld "portbindung umleitungs-Berechtigung"](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")

## <a name="see-also"></a>Siehe auch

- [\<BindingRedirect >-Element](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [Umleiten von Assemblyversionen](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
