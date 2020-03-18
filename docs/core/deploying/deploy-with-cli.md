---
title: Veröffentlichen von Apps mit der .NET Core-CLI
description: Erfahren Sie, wie Sie mit .NET Core-CLI-Befehlen eine .NET Core-App veröffentlichen.
author: thraka
ms.author: adegeo
ms.date: 12/12/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: f4c2a4ccf551c53e4aa4e125cb5720d6f1cc9601
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79397992"
---
# <a name="publish-net-core-apps-with-the-net-core-cli"></a>Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI

In diesem Artikel wird veranschaulicht, wie Sie Ihre .NET Core-Anwendung über die Befehlszeile veröffentlichen. .NET Core bietet drei Möglichkeiten zum Veröffentlichen Ihrer Anwendungen. Die frameworkabhängige Bereitstellung erzeugt eine plattformübergreifende DLL-Datei, die die lokal installierte .NET Core-Runtime verwendet. Die frameworkabhängige ausführbare Datei erzeugt eine plattformspezifische ausführbare Datei, die die lokal installierte .NET Core-Runtime verwendet. Die eigenständige ausführbare Datei erzeugt eine plattformspezifische ausführbare Datei, die eine lokale Kopie der .NET Core-Runtime enthält.

Eine Übersicht über diese Veröffentlichungsmodi finden Sie unter [.NET Core-Anwendungsbereitstellung](index.md).

Benötigen Sie schnelle Hilfe zur Verwendung der CLI? In der folgenden Tabelle finden Sie einige Beispiele zum Veröffentlichen Ihrer App. Sie können das Zielframework mit dem `-f <TFM>`-Parameter oder durch Bearbeiten der Projektdatei festlegen. Weitere Informationen finden Sie in den [Grundlagen der Veröffentlichung](#publishing-basics).

| Veröffentlichungsmodus | Version des SDK | Befehl |
| ------------ | ----------- | ------- |
| Framework-abhängige Bereitstellung | 2.x | `dotnet publish -c Release` |
| Frameworkabhängige ausführbare Datei | 2.2 | `dotnet publish -c Release -r <RID> --self-contained false` |
|                                | 3.0 | `dotnet publish -c Release -r <RID> --self-contained false` |
|                                | 3.0* | `dotnet publish -c Release` |
| Eigenständige Bereitstellung      | 2.1 | `dotnet publish -c Release -r <RID> --self-contained true` |
|                                | 2.2 | `dotnet publish -c Release -r <RID> --self-contained true` |
|                                | 3.0 | `dotnet publish -c Release -r <RID> --self-contained true` |

\*Wenn Sie Version 3.0 des SDK verwenden, stellt die frameworkabhängige ausführbare Datei den Standardveröffentlichungsmodus bei der Ausführung des Basisbefehls `dotnet publish` dar. Dies gilt nur, wenn das Projekt entweder auf **.NET Core 2.1** oder **.NET Core 3.0** abzielt.

## <a name="publishing-basics"></a>Grundlagen der Veröffentlichung

Die `<TargetFramework>`-Einstellung der Projektdatei gibt das Standardzielframework an, wenn Sie Ihre App veröffentlichen. Sie können das Zielframework in einen beliebigen, gültigen [Zielframeworkmoniker (TFM)](../../standard/frameworks.md) ändern. Wenn Sie in Ihrem Projekt beispielsweise `<TargetFramework>netcoreapp2.2</TargetFramework>` verwenden, wird eine Binärdatei für .NET Core 2.2 erstellt. Der mit dieser Einstellung festgelegte TFM ist das Standardziel des [`dotnet publish`](../tools/dotnet-publish.md)-Befehls.

Sie können mehrere durch Semikolons getrennte TFM-Werte in der `<TargetFrameworks>`-Einstellung festlegen, wenn Sie mehr als ein Zielframework benötigen. Mit dem `dotnet publish -f <TFM>`-Befehl können Sie eines der Frameworks veröffentlichen. Wenn Sie beispielsweise über `<TargetFrameworks>netcoreapp2.1;netcoreapp2.2</TargetFrameworks>` verfügen und `dotnet publish -f netcoreapp2.1` ausführen, wird eine Binärdatei für .NET Core 2.1 erstellt.

Sofern es nicht anders festgelegt ist, ist [ das Ausgabeverzeichnis des `dotnet publish`](../tools/dotnet-publish.md)`./bin/<BUILD-CONFIGURATION>/<TFM>/publish/`-Befehls. Der **BUILD-CONFIGURATION**-Standardmodus ist **Debug**, sofern er nicht mithilfe des `-c`-Parameters geändert wurde. Zum Beispiel wird mit `dotnet publish -c Release -f netcoreapp2.1` in `myfolder/bin/Release/netcoreapp2.1/publish/` veröffentlicht.

Wenn Sie das .NET Core SDK 3.0 oder höher verwenden, ist die frameworkabhängige ausführbare Datei der Standardveröffentlichungsmodus für Apps für die .NET Core-Versionen 2.1, 2.2, 3.0 oder höher.

Wenn Sie das .NET Core SDK 2.1 verwenden, ist die frameworkabhängige Bereitstellung der Standardveröffentlichungsmodus für Apps für die .NET Core-Versionen 2.1 und 2.2.

### <a name="native-dependencies"></a>Native Abhängigkeiten

Wenn Ihre App über native Abhängigkeiten verfügt, kann sie auf anderen Betriebssystemen möglicherweise nicht ausgeführt werden. Wenn Ihre App beispielsweise die native Windows-API verwendet, kann sie nicht unter macOS oder Linux ausgeführt werden. In diesem Fall müssten Sie plattformspezifischen Code bereitstellen und eine ausführbare Datei für jede Plattform kompilieren.

Beachten Sie außerdem, dass Ihre App möglicherweise nicht auf jeder Plattform ausgeführt werden kann, wenn Sie auf eine Bibliothek verwiesen haben, die eine native Abhängigkeit aufweist. Es ist jedoch möglich, dass ein NuGet-Paket, auf das Sie verweisen, plattformspezifische Versionen enthält, um die erforderlichen nativen Abhängigkeiten für Sie zu verarbeiten.

Beim Verteilen einer App mit nativen Abhängigkeiten müssen Sie möglicherweise den `dotnet publish -r <RID>`-Switch verwenden, um die Zielplattform für Ihre Veröffentlichung anzugeben. Eine Liste der Runtimebezeichner (RID) finden Sie im [RID-Katalog](../rid-catalog.md).

Weitere Informationen zu plattformspezifischen Binärdateien finden Sie in den Abschnitten [Frameworkabhängige ausführbare Datei](#framework-dependent-executable) und [Eigenständige Bereitstellung](#self-contained-deployment).

## <a name="sample-app"></a>Beispiel-App

Sie können die folgende App zum Kennenlernen der Veröffentlichungsbefehle verwenden. Erstellen Sie die App, indem Sie die folgenden Befehle im Terminal ausführen:

```dotnetcli
mkdir apptest1
cd apptest1
dotnet new console
dotnet add package Figgle
```

Sie müssen den Inhalt der von der Konsolenvorlage erstellten `Program.cs`- oder `Program.vb`-Datei in Folgenden ändern:

```csharp
using System;

namespace apptest1
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine(Figgle.FiggleFonts.Standard.Render("Hello, World!"));
        }
    }
}
```

```vb
Module Program
    Sub Main(args As String())
        Console.WriteLine(Figgle.FiggleFonts.Standard.Render("Hello, World!"))
    End Sub
End Module
```

Wenn Sie die App ausführen ([`dotnet run`](../tools/dotnet-run.md)), wird die folgende Ausgabe angezeigt:

```terminal
  _   _      _ _         __        __         _     _ _
 | | | | ___| | | ___    \ \      / /__  _ __| | __| | |
 | |_| |/ _ \ | |/ _ \    \ \ /\ / / _ \| '__| |/ _` | |
 |  _  |  __/ | | (_) |    \ V  V / (_) | |  | | (_| |_|
 |_| |_|\___|_|_|\___( )    \_/\_/ \___/|_|  |_|\__,_(_)
                     |/
```

## <a name="framework-dependent-deployment"></a>Framework-abhängige Bereitstellung

Für die .NET Core SDK 2.x-CLI ist die frameworkabhängige Bereitstellung der Standardmodus des Basisbefehls `dotnet publish`.

Wenn Sie Ihre App als frameworkabhängige Bereitstellung veröffentlichen, wird eine `<PROJECT-NAME>.dll`-Datei im `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/`-Ordner erstellt. Navigieren Sie zum Ausgabeordner, und verwenden Sie den Befehl `dotnet <PROJECT-NAME>.dll`, um Ihre App auszuführen.

Ihre App wird für eine bestimmte Version von .NET Core konfiguriert. Die .NET Core-Zielruntime ist auf jedem Computer erforderlich, auf dem Ihre App ausgeführt wird. Wenn Ihre App beispielsweise auf .NET Core 2.2 ausgerichtet ist, muss die .NET Core 2.2-Runtime auf Computern installiert sein, auf denen Ihre App ausgeführt werden soll. Sie können Ihre Projektdatei wie im Abschnitt [Grundlagen der Veröffentlichung](#publishing-basics) beschrieben bearbeiten, um das Standardzielframework zu ändern oder mehr als ein Zielframework einzurichten.

Beim Veröffentlichen einer frameworkabhängigen Bereitstellung wird eine App erstellt, die automatisch ein Rollforward auf den neuesten .NET Core-Sicherheitspatch ausführt, der auf dem System verfügbar ist. Weitere Informationen über die Versionsbindung zur Kompilierzeit finden Sie unter [.NET Core-Versionsauswahl](../versions/selection.md#framework-dependent-apps-roll-forward).

## <a name="framework-dependent-executable"></a>Frameworkabhängige ausführbare Datei

Für die .NET Core SDK 3.x-CLI ist die frameworkabhängige ausführbare Datei der Standardmodus des Basisbefehls `dotnet publish`. Sie müssen keine weiteren Parameter festlegen, wenn Sie das aktuelle Betriebssystem als Ziel verwenden möchten.

In diesem Modus wird ein Host für die plattformspezifische ausführbare Datei erstellt, der Ihre plattformübergreifende App hostet. Dieser Modus ähnelt der frameworkabhängigen Bereitstellung, da dabei ein Host in Form des `dotnet`-Befehls erforderlich ist. Der Dateiname des ausführbaren Hosts variiert je nach Plattform. Der Name sollte `<PROJECT-FILE>.exe` ähnlich sein. Sie können diese ausführbare Datei direkt ausführen, anstatt `dotnet <PROJECT-FILE>.dll` aufzurufen, was jedoch auch eine akzeptable Möglichkeit zum Ausführen der App darstellt.

Ihre App wird für eine bestimmte Version von .NET Core konfiguriert. Die .NET Core-Zielruntime ist auf jedem Computer erforderlich, auf dem Ihre App ausgeführt wird. Wenn Ihre App beispielsweise auf .NET Core 2.2 ausgerichtet ist, muss die .NET Core 2.2-Runtime auf Computern installiert sein, auf denen Ihre App ausgeführt werden soll. Sie können Ihre Projektdatei wie im Abschnitt [Grundlagen der Veröffentlichung](#publishing-basics) beschrieben bearbeiten, um das Standardzielframework zu ändern oder mehr als ein Zielframework einzurichten.

Beim Veröffentlichen einer frameworkabhängigen ausführbaren Datei wird eine App erstellt, die automatisch ein Rollforward auf den neuesten .NET Core-Sicherheitspatch ausführt, der auf dem System verfügbar ist. Weitere Informationen über die Versionsbindung zur Kompilierzeit finden Sie unter [.NET Core-Versionsauswahl](../versions/selection.md#framework-dependent-apps-roll-forward).

Für :NET Core 2.2 oder früher müssen Sie die folgenden Parameter mit dem `dotnet publish`-Befehl verwenden, um eine frameworkabhängige ausführbare Datei zu veröffentlichen:

- `-r <RID>` Dieser Switch verwendet einen Bezeichner (RID), um die Zielplattform anzugeben. Eine Liste der Runtimebezeichner (RID) finden Sie im [RID-Katalog](../rid-catalog.md).

- `--self-contained false` Dieser Switch weist das .NET Core SDK an, eine ausführbare Datei als frameworkabhängige ausführbare Datei zu erstellen.

Wenn Sie den `-r`-Switch verwenden, wird der Pfad des Ausgabeordner in folgenden geändert: `./bin/<BUILD-CONFIGURATION>/<TFM>/<RID>/publish/`

Führen Sie [ aus, wenn Sie die ](#sample-app)Beispiel-App`dotnet publish -f netcoreapp2.2 -r win10-x64 --self-contained false` verwenden. Mit diesem Befehl wird die folgende ausführbare Datei erstellt: `./bin/Debug/netcoreapp2.2/win10-x64/publish/apptest1.exe`

> [!NOTE]
> Sie können die Gesamtgröße Ihrer Bereitstellung reduzieren, indem Sie den **invarianten Globalisierungsmodus** aktivieren. Dieser Modus eignet sich für Anwendungen, die nicht für den globalen Einsatz ausgelegt sind, und Formatierungskonventionen, Groß-/Kleinschreibungskonventionen, Zeichenfolgenvergleiche und Sortierreihenfolgen der [invarianten Kultur](xref:System.Globalization.CultureInfo.InvariantCulture) verwenden können. Weitere Informationen zum **invarianten Globalisierungsmodus** und seiner Aktivierung finden Sie unter [.NET Core Globalization Invariant Mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md) (Invarianter Globalisierungsmodus von .NET Core).

## <a name="self-contained-deployment"></a>Eigenständige Bereitstellung

Wenn Sie eine eigenständige Bereitstellung veröffentlichen, erstellt das .NET Core SDK eine plattformspezifische ausführbare Datei. Beim Veröffentlichen einer eigenständigen Bereitstellung sind alle zum Ausführen der App erforderlichen .NET Core-Dateien enthalten, jedoch sind die [nativen Abhängigkeiten von .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) nicht enthalten. Diese Abhängigkeiten müssen auf dem System vorhanden sein, bevor die App ausgeführt wird.

Beim Veröffentlichen einer eigenständigen Bereitstellung wird eine App erstellt, für die kein Rollforward auf den neuesten verfügbaren .NET Core-Sicherheitspatch ausgeführt wird. Weitere Informationen über die Versionsbindung zur Kompilierzeit finden Sie unter [.NET Core-Versionsauswahl](../versions/selection.md#self-contained-deployments-include-the-selected-runtime).

Sie müssen die folgenden Parameter mit dem `dotnet publish`-Befehl verwenden, um eine eigenständige Bereitstellung zu veröffentlichen:

- `-r <RID>` Dieser Switch verwendet einen Bezeichner (RID), um die Zielplattform anzugeben. Eine Liste der Runtimebezeichner (RID) finden Sie im [RID-Katalog](../rid-catalog.md).

- `--self-contained true` Dieser Switch weist das .NET Core SDK an, eine ausführbare Datei als eigenständige Bereitstellung zu erstellen.

> [!NOTE]
> Sie können die Gesamtgröße Ihrer Bereitstellung reduzieren, indem Sie den **invarianten Globalisierungsmodus** aktivieren. Dieser Modus eignet sich für Anwendungen, die nicht für den globalen Einsatz ausgelegt sind, und Formatierungskonventionen, Groß-/Kleinschreibungskonventionen, Zeichenfolgenvergleiche und Sortierreihenfolgen der [invarianten Kultur](xref:System.Globalization.CultureInfo.InvariantCulture) verwenden können. Weitere Informationen zum **invarianten Globalisierungsmodus** und seiner Aktivierung finden Sie unter [.NET Core Globalization Invariant Mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md) (Invarianter Globalisierungsmodus von .NET Core).

## <a name="see-also"></a>Weitere Informationen

- [.NET Core Application Deployment Overview (Übersicht über die .NET Core-Anwendungsbereitstellung)](index.md)
- [.NET Core Runtime-ID (RID)-Katalog](../rid-catalog.md)
