---
title: Aktivieren oder Deaktivieren von automatisch generierten bindungsumleitungen
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: f646445d5fa4556646700bb5daf8ac859631da2c
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083660"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a>Vorgehensweise: Aktivieren und Deaktivieren der Bindungsumleitung

Beim Kompilieren von apps in Visual Studio, die auf die [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] und höhere Versionen werden bindungsumleitungen werden automatisch hinzugefügt, um die app-Konfigurationsdatei für die Assemblyvereinheitlichung zu überschreiben. Bindungsumleitungen werden hinzugefügt, wenn die App oder ihre Komponenten auf mehr als eine Version der gleichen Assembly verweisen, auch wenn Sie manuell Bindungsumleitungen in der Konfigurationsdatei für Ihre App angeben. Die automatische bindungsumleitung wirkt sich auf desktop-apps und Web-apps, die auf die [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] oder eine höhere Version, obwohl das Verhalten für eine Web-app etwas anders ist. Sie können die automatische bindungsumleitung aktivieren, wenn Sie vorhandene apps, die frühere Versionen von .NET Framework abzielen, oder Sie diese Funktion deaktivieren können, wenn Sie manuell bindungsumleitungen erstellen möchten.

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a>Deaktivieren Sie automatische bindungsumleitungen in desktop-apps

Automatische bindungsumleitungen sind standardmäßig aktiviert, für Windows desktop-apps, die als Ziel der [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] und höhere Versionen. Die bindungsumleitungen werden hinzugefügt, um die Ausgabekonfigurationsdatei (**"App.config"**)-Datei, wenn die app kompiliert wurde, und überschreiben Sie die Assemblyvereinheitlichung, die sonst erfolgen würde. Die Quelle **"App.config"** Datei wird nicht geändert. Sie können dieses Feature deaktivieren, indem die Projektdatei für die app ändern oder deaktivieren ein Kontrollkästchen in den Eigenschaften des Projekts in Visual Studio.

### <a name="disable-through-project-properties"></a>Deaktivieren Sie über Projekteigenschaften

Wenn Sie Visual Studio 2017 Version 15.7 oder höher verfügen, können Sie ganz einfach automatisch generierten bindungsumleitungen in den Eigenschaftenseiten des Projekts deaktivieren.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** aus.

2. Auf der **Anwendung** Seite aus, deaktivieren Sie die **Automatisches Generieren von bindungsumleitungen** Option.

3. Drücken Sie **STRG**+**S** um die Änderung zu speichern.

### <a name="disable-manually-in-the-project-file"></a>Deaktivieren Sie manuell in der Projektdatei

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

Bei Web-Apps werden automatische Bindungsumleitungen auf andere Weise implementiert. Da der Quellkonfiguration (**"Web.config"**) Datei muss geändert werden, für die Web-apps, bindungsumleitungen werden nicht automatisch hinzugefügt, die Konfigurationsdatei. Allerdings benachrichtigt Visual Studio Sie bei Bindungskonflikten, und Sie können Bindungsumleitungen hinzufügen, um die Konflikte zu lösen. Da Sie immer zum Hinzufügen bindungsumleitungen aufgefordert werden, müssen Sie nicht explizit deaktivieren Sie dieses Feature für eine Web-app.

Zum Hinzufügen bindungsumleitungen zu einer **"Web.config"** Datei:

1. Kompilieren Sie die Anwendung in Visual Studio, und prüfen Sie, ob Buildwarnungen vorliegen.

   ![Buildwarnung für assemblyverweiskonflikte](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")

2. Wenn Konflikte für eine Assemblybindung bestehen, wird eine Warnung angezeigt. Doppelklicken Sie auf die Warnung aus, oder wählen Sie den Warnhinweis, und drücken Sie **EINGABETASTE**.

   Ein Dialogfeld, das Ihnen ermöglicht, automatisch die erforderlichen Bindung hinzuzufügen leitet an die Quelle **"Web.config"** -Datei angezeigt wird.

   ![Dialogfeld "portbindung umleitungs-Berechtigung"](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")

## <a name="see-also"></a>Siehe auch

- [\<BindingRedirect >-Element](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [Umleiten von Assemblyversionen](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
