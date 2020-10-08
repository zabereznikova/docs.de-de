---
title: Einzeldatei-App
description: Hier erfahren Sie, was eine Einzeldatei-App ist und warum Sie dieses Anwendungsbereitstellungsmodell wählen sollten.
author: lakshanf
ms.author: lakshanf
ms.date: 08/28/2020
ms.openlocfilehash: 0167e62ea46e1c23c3d4ef6ea505ee051ffaf264
ms.sourcegitcommit: d66641bc7c14ad7d02300316e9e7e84a875a0a72
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2020
ms.locfileid: "91712636"
---
# <a name="single-file-deployment-and-executable"></a>Einzeldateibereitstellung und ausführbare Datei

Wenn Sie alle Abhängigkeiten der Anwendung in eine einzelne Binärdatei packen, kann ein Anwendungsentwickler die Anwendung in einer Datei bereitstellen und verteilen. Dieses Bereitstellungsmodell wurde mit .NET 3.0 eingeführt und in .NET 5.0 erweitert. Wenn ein Benutzer zuvor in .NET Core 3.0 eine Einzeldatei-App ausgeführt hat, hat der .NET Core-Host zuerst alle Dateien in ein temporäres Verzeichnis extrahiert, bevor die Anwendung ausgeführt wurde. In .NET 5.0 wurde der Ablauf verbessert, indem der Code direkt ausgeführt wird, ohne die Dateien aus der App zu extrahieren.

Die Einzeldateibereitstellung ist für das [frameworkabhängige Bereitstellungsmodell](index.md#publish-framework-dependent) und [eigenständige Anwendungen](index.md#publish-self-contained) verfügbar. Bei einer eigenständigen Anwendung handelt es sich dabei um eine große Datei, da die Runtime und die Frameworkbibliotheken enthalten sind. Die Einzeldatei-Bereitstellungsoption kann mit den Veröffentlichungsoptionen [ReadyToRun](../tools/dotnet-publish.md) und [Trim](trim-self-contained.md) (ein experimentelles Feature in .NET 5.0) kombiniert werden.

## <a name="api-incompatibility"></a>API-Inkompatibilität

Einige APIs sind nicht mit einer Einzeldateibereitstellung kompatibel, und Anwendungen müssen möglicherweise geändert werden, wenn sie diese APIs verwenden. Wenn Sie ein Framework oder ein Paket eines Drittanbieters verwenden, verwenden diese möglicherweise auch eine dieser APIs und müssen deshalb geändert werden. Die häufigste Ursache für Probleme ist die Abhängigkeit von Dateipfaden für Dateien oder DLLs, die im Lieferumfang der Anwendung enthalten sind.

Die Tabelle unten enthält die relevanten Details zur API der Laufzeitbibliothek für die Verwendung einer einzelnen Datei.

| API                            | Hinweis                                                                   |
|--------------------------------|------------------------------------------------------------------------|
| `Assembly.Location`            | Gibt eine leere Zeichenfolge zurück.                                               |
| `Module.FullyQualifiedName`    | Diese API gibt eine Zeichenfolge mit dem Wert `<Unknown>` zurück oder löst eine Ausnahme aus. |
| `Module.Name`                  | Diese API gibt eine Zeichenfolge mit dem Wert `<Unknown>`zurück.                        |
| `Assembly.GetFile`             | Löst <xref:System.IO.IOException> aus.                                   |
| `Assembly.GetFiles`            | Löst <xref:System.IO.IOException> aus.                                   |
| `Assembly.CodeBase`            | Löst <xref:System.PlatformNotSupportedException> aus.                    |
| `Assembly.EscapedCodeBase`     | Löst <xref:System.PlatformNotSupportedException> aus.                    |
| `AssemblyName.CodeBase`        | Gibt `null`zurück.                                                        |
| `AssemblyName.EscapedCodeBase` | Gibt `null`zurück.                                                        |

Es gibt einige Empfehlungen zum Behandeln häufiger Szenarios:

* Verwenden Sie <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>, um auf Dateien neben der ausführbaren Datei zuzugreifen.

* Verwenden Sie das erste Element von <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>, um den Dateinamen der ausführbaren Datei zu ermitteln.

* Verwenden Sie die [eingebetteten Ressourcen](../../framework/resources/creating-resource-files-for-desktop-apps.md), um das Versenden loser Dateien zu vermeiden.

## <a name="attaching-a-debugger"></a>Anfügen eines Debuggers

Unter Linux ist [SOS with LLDB](../diagnostics/dotnet-sos.md) der einzige Debugger, der an eigenständige Einzeldateiprozesse angefügt werden kann oder Absturzabbilder debuggen kann.

Unter Windows und Mac können Visual Studio und VS Code zum Debuggen von Absturzabbildern verwendet werden. Das Anfügen an eine eigenständige ausführbare Einzeldatei erfordert eine zusätzliche Datei: _mscordbi.{dll,so}_ .

Ohne diese Datei erzeugt Visual Studio möglicherweise die Fehlermeldung „Anfügen an den Prozess nicht möglich. Eine Debugkomponente ist nicht installiert.“, und VS Code erzeigt möglicherweise den Fehler „Fehler beim Anfügen an Prozess: Unbekannter Fehler: 0x80131c3c.“.

Um diese Fehler zu beheben, muss _mscordbi_ neben die ausführbare Datei kopiert werden. _mscordbi_ wird standardmäßig mit `publish` im Unterverzeichnis mit der Runtime-ID der Anwendung veröffentlicht. Wenn ein Benutzer zum Beispiel eine eigenständige ausführbare Einzeldatei mithilfe der `dotnet`-CLI für Windows und den Parametern `-r win-x64` veröffentlichen würde, würde die ausführbare Datei in _bin/Debug/net5.0/win-x64/publish_ platziert werden. Eine Kopie von _mscordbi.dll_ wäre dann in _in/Debug/net5.0/win-x64_ enthalten.

## <a name="other-considerations"></a>Weitere Überlegungen

Native Bibliotheken werden nicht standardmäßig in die Einzeldatei gepackt. Unter Linux wird die Runtime im Voraus mit dem Paket verknüpft, und nur anwendungsnative Bibliotheken werden im gleichen Verzeichnis wie die Einzeldatei-App bereitgestellt. Unter Windows wird nur der Hostingcode im Voraus verknüpft, und die Runtime und anwendungsnative Bibliotheken werden im gleichen Verzeichnis wie die Einzeldatei-App bereitgestellt. Dadurch werden Probleme beim Debuggen vermieden, denn dafür wird vorausgesetzt, dass native Dateien nicht in der Einzeldatei enthalten sind. Sie können das Flag `IncludeNativeLibrariesForSelfExtract` festlegen, um native Dateien in das Einzeldateipaket einzufügen. Diese Dateien werden jedoch in ein temporäres Verzeichnis auf dem Clientcomputer extrahiert, wenn die Einzeldatei-App ausgeführt wird.

Die Einzeldateianwendung verfügt über alle zugehörigen PDB-Dateien und wird standardmäßig nicht gebündelt. Wenn Sie PDBs in die Assembly für Projekte, die Sie erstellen, einschließen möchten, legen Sie `DebugType` auf `embedded` fest, wie [unten](#include-pdb-files-inside-the-bundle) ausführlich beschrieben.

Verwaltete C++-Komponenten eignen sich nicht für die Einzeldateibereitstellung. Es wird empfohlen, Anwendungen in C# oder einer anderen nicht verwalteten C++-Programmiersprache zu schreiben, wenn diese mit der Einzeldateibereitstellung kompatibel sein sollen.

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

## <a name="include-pdb-files-inside-the-bundle"></a>Einschließen von PDB-Dateien in das Bündel

Die PDB-Datei für eine Assembly kann mithilfe der folgenden Einstellung in die Assembly selbst (`.dll`) eingebettet werden. Da die Symbole Teil der Assembly sind, sind sie auch Teil der Einzeldateianwendung:

```xml
<DebugType>embedded</DebugType>
```

Fügen Sie z. B. die folgende Eigenschaft in die Projektdatei einer Assembly ein, um die PDB-Datei in diese Assembly einzubetten:

```xml
<PropertyGroup>
  <DebugType>embedded</DebugType>
</PropertyGroup>
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

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Projektmappen-Explorer mit Kontextmenü und markierter Option zum Veröffentlichen":::

01. Legen Sie im Dialogfeld **Profileinstellungen** die folgenden Optionen fest:

    - Legen Sie den **Bereitstellungsmodus** auf **Eigenständig** fest.
    - Legen Sie die **Zielrumtime** auf die Plattform fest, auf der Sie die App veröffentlichen möchten.
    - Klicken Sie auf **Einzelne Datei erstellen**.

    Klicken Sie auf **Speichern**, um die Einstellungen zu speichern und zum Dialogfeld **Veröffentlichen** zurückzukehren.

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="Projektmappen-Explorer mit Kontextmenü und markierter Option zum Veröffentlichen":::

01. Klicken Sie auf **Veröffentlichen**, um Ihre App als Einzeldatei zu veröffentlichen.

Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md).

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a>Veröffentlichen einer Einzeldatei-App (Visual Studio für Mac)

In Visual Studio für Mac ist es nicht möglich, eine App als Einzeldatei zu veröffentlichen. Sie müssen diese manuell veröffentlichen, indem Sie die Anleitung im Abschnitt [Veröffentlichen einer Einzeldatei-App (CLI)](#publish-a-single-file-app---cli) befolgen. Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).

## <a name="see-also"></a>Siehe auch

- [.NET Core-Anwendungsbereitstellung](index.md)
- [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md)
- [Bereitstellen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md)
- [`dotnet publish`-Befehl](../tools/dotnet-publish.md)
