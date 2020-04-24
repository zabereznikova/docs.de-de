---
title: Zuschneiden eigenständiger Anwendungen
description: Erfahren Sie, wie Sie eigenständige Apps zuschneiden, um ihre Größe zu verringern. .NET Core bündelt die Laufzeit mit einer App, die eigenständig veröffentlicht wird und deren Laufzeit in der Regel umfangreicher als erforderlich ist.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bb8ac88c5e16b7fd20a7670e4ad76dbe4b44da1b
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242908"
---
# <a name="trim-self-contained-deployments-and-executables"></a>Kürzen eigenständiger Bereitstellungen und ausführbarer Dateien

Beim Veröffentlichen einer eigenständigen Anwendung wird die .NET Core-Laufzeit mit der Anwendung gebündelt. Durch diese Bündelung wird die Menge des Inhalts der gepackten Anwendung beträchtlich erhöht. Wenn Sie Ihre Anwendung bereitstellen, ist die Größe häufig ein wichtiger Faktor. Anwendungsentwickler versuchen in der Regel, die Größe des Anwendungspakets so gering wie möglich zu halten.

Abhängig von der Komplexität der Anwendung ist für ihre Ausführung nur eine Teilmenge der Laufzeit erforderlich. Diese nicht verwendeten Teile der Laufzeit sind unnötig und können aus der gepackten Anwendung abgeschnitten werden.

Zum Kürzen der Anwendung werden ihre Binärdateien untersucht, um die erforderlichen Laufzeitassemblys zu ermitteln und einen entsprechenden Graphen zu erstellen. Die verbleibenden Runtimeassemblys, auf die nicht verwiesen wird, werden ausgeschlossen.

> [!NOTE]
> Das Kürzen ist ein experimentelles Feature in .NET Core 3.1 und _nur_ für Anwendungen verfügbar, die eigenständig veröffentlicht werden.

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
- Veröffentlichung von Einzeldateien deaktivieren: `-p:PublishSingleFile=false`
- Zuschneiden aktivieren: `p:PublishTrimmed=true`

Das folgende Beispiel veröffentlicht eine App für Windows 10 als eigenständige App und schneidet die Ausgabe zu.

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true -p:PublishSingleFile=false -p:PublishTrimmed=true
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
