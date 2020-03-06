---
title: Neuerungen in .NET Core 3.1
description: Erfahren Sie mehr zu den neuen Features in .NET Core 3.1.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 323a2390f079c17b81db01e4e3787916251943bf
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156555"
---
# <a name="whats-new-in-net-core-31"></a>Neuerungen in .NET Core 3.1

In diesem Artikel werden Neuerungen in .NET Core 3.1 beschrieben. Diese Version enthält kleinere Verbesserungen an .NET Core 3.0, wobei der Schwerpunkt auf kleinen, aber wichtigen Korrekturen liegt. Das wichtigste Merkmal von .NET Core 3.1 ist, dass es sich um eine Version mit [langfristigem Support (Long-Term Support, LTS)](#long-term-support) handelt.

Wenn Sie Visual Studio 2019 einsetzen, müssen Sie ein Update auf [Visual Studio 2019, Version 16.4](https://visualstudio.microsoft.com/downloads/) durchführen, um mit .NET Core 3.1-Projekten arbeiten zu können. Weitere Informationen zu Neuerungen in Visual Studio finden Sie unter [Neuerungen in Visual Studio 2019 Version 16.4](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164).

Visual Studio für Mac unterstützt und umfasst auch .NET Core 3.1, und zwar in Visual Studio für Mac 8.4.

Weitere Informationen zu dieser Version finden Sie unter [Ankündigung von .NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).

- [Laden Sie .NET Core 3.1 herunter](https://dotnet.microsoft.com/download/dotnet-core/3.1), um unter Windows, macOS oder Linux loszulegen.

## <a name="long-term-support"></a>Langfristiger Support

NET Core 3.1 ist eine LTS-Version mit Support von Microsoft für die nächsten drei Jahre. Es wird dringend empfohlen, Ihre Anwendungen auf .NET Core 3.1 umzustellen. Der aktuelle Lebenszyklus anderer Hauptversionen ist wie folgt:

| Freigabe | Hinweis |
| ------- | ---- |
| .NET Core 3.0 | Ende des Lebenszyklus: 03. März 2020     |
| .NET Core 2.2 | Ende des Lebenszyklus: 23. Dezember 2019 |
| .NET Core 2.1 | Ende des Lebenszyklus: 21. August 2021    |

Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

## <a name="macos-apphost-and-notarization"></a>macOS-appHost und -Notarisierung

*nur unter macOS*

Ab dem notarisierten .NET Core SDK 3.1 für macOS, ist die appHost-Einstellung standardmäßig deaktiviert. Weitere Informationen finden Sie unter [macOS Catalina-Notarisierung und die Auswirkungen auf .NET Core-Downloads und -Projekte](../install/macos-notarization-issues.md).

Wenn die appHost-Einstellung aktiviert ist, erzeugt .NET Core eine native ausführbare Mach-O-Datei, wenn Sie einen Build- oder Veröffentlichungsprozess ausführen. Ihre App wird im Kontext von appHost ausgeführt, wenn sie mit dem Befehl `dotnet run` über den Quellcode oder durch direktes Starten der ausführbaren Mach-O-Datei ausgeführt wird.

Ohne die appHost-Datei können Benutzer eine [Runtime-abhängige](../deploying/index.md#publish-runtime-dependent) App nur mit dem Befehl `dotnet <filename.dll>` starten. Es wird immer eine appHost-Datei erstellt, wenn Sie Ihre App [eigenständig](../deploying/index.md#publish-self-contained) veröffentlichen.

Sie können die appHost-Datei entweder auf Projektebene konfigurieren oder für einen spezifischen `dotnet`-Befehl mit dem `-p:UseAppHost`-Parameter aktivieren:

- Projektdatei

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- Befehlszeilenparameter

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

Weitere Informationen über die `UseAppHost`-Einstellung finden Sie unter [MSBuild-Eigenschaften für Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).

## <a name="windows-forms"></a>Windows Forms

*Nur Windows*

> [!WARNING]
> Bei Windows Forms gibt es Breaking Changes.

Windows Forms wurden ältere Steuerelemente hinzugefügt, die in der Visual Studio Designer-Toolbox seit einiger Zeit nicht mehr verfügbar sind. Diese wurden bereits in .NET Framework 2.0 durch neue Steuerelemente ersetzt. Sie wurden aus dem Desktop SDK für .NET Core 3.1 entfernt.

| Entferntes Steuerelement | Empfohlener Ersatz | Zugehörige entfernte APIs |
| --------------- | ----------------------- | ----------------------- |
| DataGrid        | <xref:System.Windows.Forms.DataGridView>      | DataGridCell<br/>DataGridRow<br/>DataGridTableCollection<br/>DataGridColumnCollection<br/>DataGridTableStyle<br/>DataGridColumnStyle<br/>DataGridLineStyle<br/>DataGridParentRowsLabel<br/>DataGridParentRowsLabelStyle<br/>DataGridBoolColumn<br/>DataGridTextBox<br/>GridColumnStylesCollection<br/>GridTableStylesCollection<br/>HitTestType |
| ToolBar         | <xref:System.Windows.Forms.ToolStrip>         | ToolBarAppearance |
| ToolBarButton   | <xref:System.Windows.Forms.ToolStripButton>   | ToolBarButtonClickEventArgs<br/>ToolBarButtonClickEventHandler<br/>ToolBarButtonStyle<br/>ToolBarTextAlign |
| ContextMenu     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | MenuItemCollection |
| MainMenu        | <xref:System.Windows.Forms.MenuStrip>         |  |
| MenuItem        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

Es wird empfohlen, Ihre Anwendungen auf .NET Core 3.1 zu aktualisieren und auf die Ersatzsteuerelemente umzusteigen. Das Ersetzen der Steuerelemente ist ein unkomplizierter Prozess, der im Wesentlichen das Suchen und Ersetzen des jeweiligen Typs vorsieht.

## <a name="ccli"></a>C++/CLI

*Nur Windows*

Es wurde Unterstützung für die Erstellung von C++/CLI-Projekten (auch „verwaltete C++-Projekte“ genannt) hinzugefügt. Die im Rahmen dieser Projekte erstellten Binärdateien sind mit .NET Core 3.0 und höheren Versionen kompatibel.

Installieren Sie die [Workload „Desktopentwicklung mit C++“](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads), um Unterstützung für C++/CLI in Visual Studio 2019 Version 16.4 hinzuzufügen. Diese Workload fügt Visual Studio zwei Vorlagen hinzu:

- CLR-Klassenbibliothek (.NET Core)
- Leeres CLR-Projekt (.NET Core)

## <a name="next-steps"></a>Nächste Schritte

- [Breaking Changes bei der Migration von Version 3.0 zu Version 3.1](../compatibility/3.0-3.1.md)
- [Überprüfen von Breaking Changes in .NET Core 3.1 für Windows Forms-Apps](../compatibility/winforms.md#net-core-31)
