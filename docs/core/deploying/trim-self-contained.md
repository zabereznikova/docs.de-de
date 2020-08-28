---
title: Zuschneiden eigenständiger Anwendungen
description: Erfahren Sie, wie Sie eigenständige Apps zuschneiden, um ihre Größe zu verringern. .NET Core bündelt die Laufzeit mit einer App, die eigenständig veröffentlicht wird und deren Laufzeit in der Regel umfangreicher als erforderlich ist.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: 0fde409e9e5911213855ab206368d302b73eebb3
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720123"
---
# <a name="trim-self-contained-deployments-and-executables"></a>Kürzen eigenständiger Bereitstellungen und ausführbarer Dateien

Das [frameworkabhängige Bereitstellungsmodell](index.md#publish-framework-dependent) ist seit der Einführung von .NET das erfolgreichste Bereitstellungsmodell. In diesem Szenario bündelt der Anwendungsentwickler nur die Anwendung und Drittanbieterassemblys mit der Annahme, dass die .NET-Runtime und Frameworkbibliotheken auf dem Clientcomputer verfügbar sind. Dieses Bereitstellungsmodell ist in .NET Core auch weiterhin das wichtigste Bereitstellungsmodell, allerdings gibt es einige Szenarios, in denen das frameworkabhängige Modell nicht optimal ist. Die Alternative besteht darin, eine [unabhängige Anwendung](index.md#publish-self-contained) zu veröffentlichen, bei der die .NET Core-Runtime und das Framework zusammen mit der Anwendung und den Drittanbieterassemblys gebündelt werden.

Das unabhängige Bereitstellungsmodell zum Kürzen ist eine spezialisierte Version des eigenständigen Bereitstellungsmodells, das für die Minimierung der Bereitstellungsgröße optimiert ist. Das Minimieren der Bereitstellungsgröße ist für einige clientseitige Szenarios wie Blazor-Anwendungen eine wichtige Anforderung. Abhängig von der Komplexität der Anwendung ist für ihre Ausführung nur eine Teilmenge der Frameworkassemblys erforderlich. Diese nicht verwendeten Teile der Bibliothek sind unnötig und können aus der gepackten Anwendung entfernt werden. Es besteht jedoch das Risiko, dass die Buildzeitanalyse der Anwendung zur Laufzeit Fehler verursachen kann, da verschiedene problematische Codemuster nicht zuverlässig analysiert werden können (hauptsächlich bei Reflexion). Da die Zuverlässigkeit nicht garantiert werden kann, wird dieses Bereitstellungsmodell als Previewfunktion angeboten. Die Engine für die Buildzeitanalyse liefert Warnungen für den Entwickler von Codemustern, die problematisch sind und daher korrigiert werden müssen. Nach Möglichkeit empfiehlt es sich, alle Runtimereflexionsabhängigkeiten in der Anwendung zu erstellen, indem Sie Code verwenden, der die gleichen Anforderungen erfüllt.

Der Kürzungsmodus für die Anwendungen kann über die TrimMode-Option konfiguriert werden und wird standardmäßig (`copyused`) verwendet, um in der Anwendung verwendete Assemblys zu bündeln. Blazor WebAssembly-Anwendungen verwenden einen aggressiveren Modus (`link`), der ungenutzten Code in den Assemblys abschneidet. Kürzungsanalysewarnungen bieten Informationen zu Codemustern, bei denen keine vollständige Abhängigkeitsanalyse möglich war. Diese Warnungen werden standardmäßig unterdrückt und können aktiviert werden, indem das Flag `SuppressTrimAnalysisWarnings` auf „false“ festgelegt wird. Weitere Informationen zu den verfügbaren Kürzungsoptionen finden Sie auf der [ILLinker-Seite](https://github.com/mono/linker/blob/master/docs/illink-options.md).

> [!NOTE]
> Das Kürzen ist ein experimentelles Feature in .NET Core 3.1 und 5.0 und _nur_ für Anwendungen verfügbar, die eigenständig veröffentlicht werden.

## <a name="prevent-assemblies-from-being-trimmed"></a>Verhindern, dass Assemblys zugeschnitten werden

In manchen Szenarien schlägt das Ermitteln von Verweisen durch die Kürzungsfunktion fehl. Wenn beispielsweise durch Ihre Anwendung oder eine Bibliothek, auf die Ihre Anwendung verweist, eine Reflexion in einer Runtimeassembly ausgeführt wird, erfolgt dieser Verweis auf die Assembly nicht direkt. Beim Zuschneiden sind diese indirekten Verweise nicht bekannt, daher wird die Bibliothek aus dem veröffentlichten Ordner ausgeschlossen.

Wenn der Code per Reflexion indirekt auf eine Assembly verweist, können Sie mit der Einstellung `<TrimmerRootAssembly>` verhindern, dass die Assembly zugeschnitten wird. Das folgende Beispiel zeigt, wie das Kürzen einer Assembly mit dem Namen `System.Security` verhindert wird:

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a>Zuschneiden der App: CLI

Sie können Ihre Anwendung mit dem Befehl [dotnet publish](../tools/dotnet-publish.md) zuschneiden. Beim Veröffentlichen Ihrer App legen Sie die folgenden drei Einstellungen fest:

- Als eigenständige App veröffentlichen: `--self-contained true`
- Zuschneiden aktivieren: `p:PublishTrimmed=true`

Das folgende Beispiel veröffentlicht eine App für Windows als eigenständige App und schneidet die Ausgabe zu.

```xml
<ItemGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <SelfContained>true</SelfContained>
    <PublishTrimmed>true</PublishTrimmed>
</ItemGroup>
```

Im folgenden Beispiel wird eine App mithilfe des aggressiven Kürzungsmodus veröffentlicht, bei dem nicht verwendeter Code in Assemblys abgeschnitten und Kürzungswarnungen aktiviert werden.

```xml
<ItemGroup>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</ItemGroup>
```

Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).

## <a name="trim-your-app---visual-studio"></a>Zuschneiden der App: Visual Studio

Visual Studio erstellt wiederverwendbare Veröffentlichungsprofile, die steuern, wie Ihre App veröffentlicht wird.

01. Klicken Sie im Bereich **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, das Sie veröffentlichen möchten. Wählen Sie **Veröffentlichen...** aus.

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Projektmappen-Explorer mit Kontextmenü und markierter Option zum Veröffentlichen":::

    Wenn Sie noch nicht über ein Veröffentlichungsprofil verfügen, befolgen Sie die Anweisungen zum Erstellen eines solchen Profils, und wählen Sie als Zieltyp **Ordner** aus.

01. Wählen Sie **Bearbeiten** aus.

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Visual Studio-Veröffentlichungsprofil mit Bearbeitungsschaltfläche":::

01. Legen Sie im Dialogfeld **Profileinstellungen** die folgenden Optionen fest:

    - Legen Sie den **Bereitstellungsmodus** auf **Eigenständig** fest.
    - Legen Sie die **Zielrumtime** auf die Plattform fest, auf der Sie die App veröffentlichen möchten.
    - Wählen Sie **Nicht verwendete Assemblys kürzen (Vorschau)** aus.

    Klicken Sie auf **Speichern**, um die Einstellungen zu speichern und zum Dialogfeld **Veröffentlichen** zurückzukehren.

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Dialogfeld für die Profileinstellungen mit Bereitstellungsmodus, Zielruntime und Optionen zum Zuschneiden von nicht verwendeten Assemblys":::

01. Klicken Sie auf **Veröffentlichen**, um Ihre App zugeschnitten zu veröffentlichen.

Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md).

## <a name="trim-your-app---visual-studio-for-mac"></a>Zuschneiden der App: Visual Studio für Mac

Visual Studio für Mac bietet keine Optionen zum Zuschneiden Ihrer App während der Veröffentlichung. Sie müssen die Veröffentlichung anhand der Anweisungen im Abschnitt [Zuschneiden der App: CLI](#trim-your-app---cli) manuell ausführen. Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).

## <a name="see-also"></a>Siehe auch

- [.NET Core-Anwendungsbereitstellung](index.md)
- [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md)
- [Bereitstellen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md)
- [Befehl „dotnet publish“](../tools/dotnet-publish.md)
