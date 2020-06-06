---
title: Aktivieren oder Deaktivieren von automatisch generierten Bindungs Umleitungen
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: 178d5070dd7018bbc0fce474cdd0b31ba3d17f77
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69913030"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a>Vorgehensweise: Aktivieren und Deaktivieren der Bindungsumleitung

Wenn Sie apps in Visual Studio kompilieren, die auf .NET Framework 4.5.1 und höhere Versionen ausgerichtet sind, können der APP-Konfigurationsdatei automatisch Bindungs Umleitungen hinzugefügt werden, um die Assemblyvereinheitlichung zu überschreiben. Bindungsumleitungen werden hinzugefügt, wenn die App oder ihre Komponenten auf mehr als eine Version der gleichen Assembly verweisen, auch wenn Sie manuell Bindungsumleitungen in der Konfigurationsdatei für Ihre App angeben. Die Funktion zur automatischen Bindungs Umleitung wirkt sich auf Desktop-Apps und Web-Apps aus, die auf die .NET Framework 4.5.1 oder eine höhere Version abzielen, obwohl das Verhalten für eine Web-App etwas abweicht. Sie können die automatische Bindungs Umleitung aktivieren, wenn Sie über vorhandene apps verfügen, die auf frühere Versionen des .NET Framework abzielen, oder Sie können diese Funktion deaktivieren, wenn Sie Bindungs Umleitungen manuell erstellen möchten.

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a>Deaktivieren von automatischen Bindungs Umleitungen in Desktop-Apps

Automatische Bindungs Umleitungen sind standardmäßig für Windows-Desktop-Apps aktiviert, die auf .NET Framework 4.5.1 und höhere Versionen abzielen. Die Bindungs Umleitungen werden der Ausgabe Konfigurationsdatei (**app. config**) hinzugefügt, wenn die APP kompiliert wird, und überschreiben die Assemblyvereinheitlichung, die andernfalls möglicherweise stattfindet. Die Datei " **app. config** " der Quelldatei wird nicht geändert. Sie können diese Funktion deaktivieren, indem Sie die Projektdatei für die APP ändern oder ein Kontrollkästchen in den Eigenschaften des Projekts in Visual Studio deaktivieren.

### <a name="disable-through-project-properties"></a>Durch Projekteigenschaften deaktivieren

Wenn Sie über Visual Studio 2017 Version 15,7 oder höher verfügen, können Sie automatisch generierte Bindungs Umleitungen auf den Eigenschaften Seiten des Projekts problemlos deaktivieren.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** aus.

2. Deaktivieren Sie auf der Seite **Anwendung** die Option **Bindungs Umleitungen automatisch generieren** .

3. Drücken Sie **STRG** + **S** , um die Änderung zu speichern.

### <a name="disable-manually-in-the-project-file"></a>Manuelles Deaktivieren in der Projektdatei

1. Öffnen Sie die Projektdatei zur Bearbeitung, indem Sie eine der folgenden Methoden verwenden:

   - Wählen Sie in Visual Studio das Projekt in **Projektmappen-Explorer**aus, und wählen Sie dann im Kontextmenü **Ordner in Datei-Explorer öffnen** aus. Suchen Sie im Datei-Explorer die Projektdatei (CSPROJ-oder VBPROJ-Datei), und öffnen Sie Sie im Editor.
   - Klicken Sie in Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Projekt entladen**aus. Klicken Sie erneut mit der rechten Maustaste auf das entladene Projekt, und wählen Sie dann **bearbeiten [ProjectName. csproj]** aus.

2. Suchen Sie in der Projektdatei den folgende Eigenschafteneintrag:

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. Ändern Sie `true` in`false`:

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a>Manuelles Aktivieren automatischer Bindungs Umleitungen

Sie können automatische Bindungs Umleitungen in vorhandenen apps aktivieren, die auf ältere Versionen der .NET Framework abzielen, oder in Fällen, in denen Sie nicht automatisch aufgefordert werden, eine Umleitung hinzuzufügen. Wenn Sie auf eine neuere Version des Frameworks abzielen, aber nicht automatisch aufgefordert werden, eine Umleitung hinzuzufügen, erhalten Sie wahrscheinlich eine Buildausgabe, die eine Neuzuordnung der Assemblys vorschlägt.

1. Öffnen Sie die Projektdatei zur Bearbeitung, indem Sie eine der folgenden Methoden verwenden:

   - Wählen Sie in Visual Studio das Projekt in **Projektmappen-Explorer**aus, und wählen Sie dann im Kontextmenü **Ordner in Datei-Explorer öffnen** aus. Suchen Sie im Datei-Explorer die Projektdatei (CSPROJ-oder VBPROJ-Datei), und öffnen Sie Sie im Editor.
   - Klicken Sie in Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Projekt entladen**aus. Klicken Sie erneut mit der rechten Maustaste auf das entladene Projekt, und wählen Sie dann **bearbeiten [ProjectName. csproj]** aus.

2. Fügen Sie der ersten Konfigurations Eigenschaften Gruppe (unter dem-Tag) das folgende-Element hinzu \<PropertyGroup> :

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   Im folgenden sehen Sie eine Beispiel Projektdatei, in der das Element eingefügt wurde:

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
     <PropertyGroup>
       <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
       <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
       <ProjectGuid>{123334}</ProjectGuid>
       ...
       <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
     </PropertyGroup>
     ...
   </Project>
   ```

3. Kompilieren Sie Ihre App.

## <a name="enable-automatic-binding-redirects-in-web-apps"></a>Aktivieren von automatischen Bindungs Umleitungen in Web-Apps

Bei Web-Apps werden automatische Bindungsumleitungen auf andere Weise implementiert. Da die Quell Konfigurationsdatei (**Web. config**) für Web-Apps geändert werden muss, werden die Bindungs Umleitungen nicht automatisch zur Konfigurationsdatei hinzugefügt. Allerdings benachrichtigt Visual Studio Sie bei Bindungskonflikten, und Sie können Bindungsumleitungen hinzufügen, um die Konflikte zu lösen. Da Sie immer aufgefordert werden, Bindungs Umleitungen hinzuzufügen, müssen Sie diese Funktion für eine Web-App nicht explizit deaktivieren.

So fügen Sie einer **Web. config** -Datei Bindungs Umleitungen hinzu:

1. Kompilieren Sie die Anwendung in Visual Studio, und prüfen Sie, ob Buildwarnungen vorliegen.

   ![Buildwarnung für Assemblyverweiskonflikte](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")

2. Wenn Konflikte für eine Assemblybindung bestehen, wird eine Warnung angezeigt. Doppelklicken Sie auf die Warnung, oder wählen Sie die Warnung, und drücken **Sie die Eingabe**Taste.

   Ein Dialogfeld, in dem Sie die erforderlichen Bindungs Umleitungen automatisch zur **Web. config** -Quelldatei hinzufügen können.

   ![Dialogfeld der Berechtigung für die Bindungsumleitung](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")

## <a name="see-also"></a>Weitere Informationen

- [\<bindingRedirect>Gewisses](./file-schema/runtime/bindingredirect-element.md)
- [Umleiten von Assemblyversionen](redirect-assembly-versions.md)
