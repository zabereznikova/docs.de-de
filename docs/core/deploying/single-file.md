---
title: Einzeldatei-App
description: Hier erfahren Sie, was eine Einzeldatei-App ist und warum Sie dieses Anwendungsbereitstellungsmodell wählen sollten.
author: lakshanf
ms.author: lakshanf
ms.date: 08/28/2020
ms.openlocfilehash: 795ea98a9fd9d672b199eb2d9b24151340ef8246
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495744"
---
# <a name="single-file-deployment-and-executable"></a>Einzeldateibereitstellung und ausführbare Datei

Wenn Sie alle Abhängigkeiten der Anwendung in eine einzelne Binärdatei packen, kann ein Anwendungsentwickler die Anwendung in einer Datei bereitstellen und verteilen. Dieses Bereitstellungsmodell wurde mit .NET 3.0 eingeführt und in .NET 5.0 erweitert. Wenn ein Benutzer zuvor in .NET Core 3.0 eine Einzeldatei-App ausgeführt hat, hat der .NET Core-Host zuerst alle Dateien in ein temporäres Verzeichnis extrahiert, bevor die Anwendung ausgeführt wurde. In .NET 5.0 wurde der Ablauf verbessert, indem der Code direkt ausgeführt wird, ohne die Dateien aus der App zu extrahieren.

Die Einzeldateibereitstellung ist für das [frameworkabhängige Bereitstellungsmodell](index.md#publish-framework-dependent) und [eigenständige Anwendungen](index.md#publish-self-contained) verfügbar. Bei einer eigenständigen Anwendung handelt es sich dabei um eine große Datei, da die Runtime und die Frameworkbibliotheken enthalten sind. Die Einzeldatei-Bereitstellungsoption kann mit den Veröffentlichungsoptionen [ReadyToRun](../tools/dotnet-publish.md) und [Trim](trim-self-contained.md) (ein experimentelles Feature in .NET 5.0) kombiniert werden.

Bei Einzeldateimethode müssen Sie einiges beachten, zum Beispiel müssen die Pfadinformationen für eine Datei relativ zum Speicherort der Anwendung sein. Die API <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> gibt eine leere Zeichenfolge zurück. Das entspricht dem Standardverhalten für Assemblys, die aus dem Arbeitsspeicher geladen werden. Der Compiler gibt während der Buildzeit eine Warnung für diese API aus, um den Entwickler auf ein bestimmtes Verhalten aufmerksam zu machen. Wenn der Pfad zum Anwendungsverzeichnis benötigt wird, gibt die API <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> das Verzeichnis zurück, in dem sich AppHost (das Einzeldateipaket) befindet. Verwaltete C++-Anwendungen eignen sich nicht für die Einzeldateibereitstellung. Es wird empfohlen, Anwendungen in C# zu schreiben, wenn diese mit der Einzeldateibereitstellung kompatibel sein sollen.

Native Bibliotheken werden nicht standardmäßig in die Einzeldatei gepackt. Unter Linux wird die Runtime im Voraus mit dem Paket verknüpft, und nur anwendungsnative Bibliotheken werden im gleichen Verzeichnis wie die Einzeldatei-App bereitgestellt. Unter Windows wird nur der Hostingcode im Voraus verknüpft, und die Runtime und anwendungsnative Bibliotheken werden im gleichen Verzeichnis wie die Einzeldatei-App bereitgestellt. Dadurch werden Probleme beim Debuggen vermieden, denn dafür wird vorausgesetzt, dass native Dateien nicht in der Einzeldatei enthalten sind. Sie können das Flag `IncludeNativeLibrariesForSelfExtract` festlegen, um native Dateien in das Einzeldateipaket einzufügen. Diese Dateien werden jedoch in ein temporäres Verzeichnis auf dem Clientcomputer extrahiert, wenn die Einzeldatei-App ausgeführt wird.

## <a name="exclude-files-from-being-embedded"></a>Ausschließen von Dateien aus der Einbettung

Bestimmte Dateien können explizit aus der Einbettung in die Einzeldatei ausgeschlossen werden, indem Sie die folgenden Metadaten festlegen:

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

So können Sie beispielsweise einige Dateien im Veröffentlichungsverzeichnis speichern, ohne diese in die Einzeldatei zu packen:

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="publish-a-single-file-app---cli"></a>Veröffentlichen einer Einzeldatei-App (CLI)

Sie können Ihre Einzeldatei-App mit dem Befehl [dotnet publish](../tools/dotnet-publish.md) veröffentlichen. Legen Sie die folgenden Eigenschaften fest, wenn Sie Ihre App veröffentlichen:

- Veröffentlichung für eine bestimmte Runtime: `-r win-x64`
- Veröffentlichung als Einzeldatei: `-p:PublishSingleFile=true`

Im folgenden Beispiel wird eine App für Windows als eigenständige Einzeldatei-App veröffentlicht.

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

Im folgenden Beispiel wird eine App für Linux als frameworkabhängige Einzeldatei-App veröffentlicht.

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).

## <a name="publish-a-single-file-app---visual-studio"></a>Veröffentlichen einer Einzeldatei-App (Visual Studio)

Visual Studio erstellt wiederverwendbare Veröffentlichungsprofile, die steuern, wie Ihre App veröffentlicht wird.

01. Klicken Sie im Bereich **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, das Sie veröffentlichen möchten. Klicken Sie auf **Veröffentlichen**.

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="Projektmappen-Explorer mit Kontextmenü und markierter Option zum Veröffentlichen":::

    Wenn Sie noch nicht über ein Veröffentlichungsprofil verfügen, befolgen Sie die Anweisungen zum Erstellen eines solchen Profils, und wählen Sie als Zieltyp **Ordner** aus.

01. Wählen Sie **Bearbeiten** aus.

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Visual Studio-Veröffentlichungsprofil mit Bearbeitungsschaltfläche":::

01. Legen Sie im Dialogfeld **Profileinstellungen** die folgenden Optionen fest:

    - Legen Sie den **Bereitstellungsmodus** auf **Eigenständig** fest.
    - Legen Sie die **Zielrumtime** auf die Plattform fest, auf der Sie die App veröffentlichen möchten.
    - Klicken Sie auf **Einzelne Datei erstellen**.

    Klicken Sie auf **Speichern**, um die Einstellungen zu speichern und zum Dialogfeld **Veröffentlichen** zurückzukehren.

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="Dialogfeld für die Profileinstellungen mit Bereitstellungsmodus, Zielruntime und hervorgehobenen Einzeldateioptionen":::

01. Klicken Sie auf **Veröffentlichen**, um Ihre App als Einzeldatei zu veröffentlichen.

Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md).

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a>Veröffentlichen einer Einzeldatei-App (Visual Studio für Mac)

In Visual Studio für Mac ist es nicht möglich, eine App als Einzeldatei zu veröffentlichen. Sie müssen diese manuell veröffentlichen, indem Sie die Anleitung im Abschnitt [Veröffentlichen einer Einzeldatei-App (CLI)](#publish-a-single-file-app---cli) befolgen. Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).

## <a name="see-also"></a>Siehe auch

- [.NET Core-Anwendungsbereitstellung](index.md)
- [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md)
- [Bereitstellen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md)
- [`dotnet publish`-Befehl](../tools/dotnet-publish.md)
