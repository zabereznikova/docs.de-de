---
title: Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio Code
description: Bei der Veröffentlichung werden die Dateien erstellt, die zum Ausführen Ihrer .NET Core-Anwendung benötigt werden.
ms.date: 07/04/2020
ms.openlocfilehash: 8fd9975e8a88704b9dea45b40127c8dc03f7d09f
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051882"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio-code"></a>Tutorial: Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio Code

In diesem Tutorial wird gezeigt, wie eine Konsolen-App veröffentlicht wird, damit sie von anderen Benutzern ausgeführt werden kann. Bei der Veröffentlichung werden die Dateien erstellt, die zum Ausführen Ihrer Anwendung benötigt werden. Zum Bereitstellen der Dateien kopieren Sie diese auf den Zielcomputer.

Die .NET Core-CLI wird zum Veröffentlichen der App verwendet. Sie können dieses Tutorial also auch mit einem anderen Code-Editor als Visual Studio Code absolvieren.

## <a name="prerequisites"></a>Voraussetzungen

- Dieses Tutorial funktioniert mit der Konsolen-App, die Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio Code](with-visual-studio-code.md) erstellen.

## <a name="publish-the-app"></a>Veröffentlichen der App

1. Starten Sie Visual Studio Code.

1. Öffnen Sie den *HelloWorld*-Projektordner, den Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio Code](with-visual-studio-code.md) erstellt haben.

1. Klicken Sie im Hauptmenü auf **Ansicht** > **Terminal**.

   Das Terminal wird im *HelloWorld*-Ordner geöffnet.

1. Führen Sie den folgenden Befehl aus:

   ```dotnetcli
   dotnet publish --configuration Release
   ```

   Die Standardbuildkonfiguration ist *Debug*. Dieser Befehl gibt also die Buildkonfiguration *Release* an. Die Ausgabe der Releasekonfiguration enthält nur wenige symbolischen Debuginformationen und wird vollständig optimiert.

   Die Befehlsausgabe ähnelt dem folgenden Beispiel:

   ```
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

   Determining projects to restore...
   All projects are up-to-date for restore.
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\HelloWorld.dll
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

## <a name="inspect-the-files"></a>Untersuchen der Dateien

Der Veröffentlichungsprozess erstellt standardmäßig eine frameworkabhängige Bereitstellung. Das ist ein Bereitstellungstyp, bei dem die veröffentlichte Anwendung auf Computern ausgeführt werden kann, auf denen die .NET Core-Runtime installiert ist. Sie können die veröffentlichte App über die ausführbare Datei starten oder indem Sie den Befehl `dotnet HelloWorld.dll` über die Eingabeaufforderung ausführen.

In den folgenden Schritten sehen Sie sich die durch den Veröffentlichungsvorgang erstellten Dateien an.

1. Klicken Sie auf der linken Navigationsleiste auf den **Explorer**.

1. Erweitern Sie *bin/Release/netcoreapp3.1/publish*.

   :::image type="content" source="media/publishing-with-visual-studio-code/published-files-output.png" alt-text="Explorer mit veröffentlichten Dateien":::

   Wie in der folgenden Abbildung gezeigt, enthält die veröffentlichte Ausgabe die folgenden Dateien:

   * *HelloWorld.deps.json*

      Dies ist Datei für Runtimeabhängigkeiten der Anwendung. In dieser werden die Komponenten und Bibliotheken (einschließlich der Dynamic Link Library, die Ihre Anwendung enthält) von .NET Core definiert, die zum Ausführen der App erforderlich sind. Weitere Informationen finden Sie unter [Konfigurationsdateien der Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

   * *HelloWorld.dll*

      Dies ist die [frameworkabhängige Bereitstellungsversion](../deploying/deploy-with-cli.md#framework-dependent-deployment) der Anwendung. Um diese Dynamic Link Library (DLL) auszuführen, geben Sie an einer Eingabeaufforderung `dotnet HelloWorld.dll` ein. Diese Methode zum Ausführen der App funktioniert auf allen Plattformen, auf denen die .NET Core-Runtime installiert ist.

   * *HelloWorld.exe* (*HelloWorld* unter Linux, wird unter macOS nicht erstellt)

      Dies ist die [frameworkabhängige ausführbare Dateiversion](../deploying/deploy-with-cli.md#framework-dependent-executable) der Anwendung. Die Datei ist betriebssystemspezifisch.

   * *HelloWorld.pdb* (optional für die Bereitstellung)

      Dies ist die Debugsymboldatei. Sie müssen die Datei nicht zusammen mit der Anwendung bereitstellen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.

   * *HelloWorld.runtimeconfig.json*

      Dies ist die Runtimekonfigurationsdatei der Anwendung. Diese Datei identifiziert die Version von .NET Core, für die Ihre Anwendung erstellt wurde. Außerdem können Sie Konfigurationsoptionen hinzufügen. Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Ausführen der veröffentlichten App

1. Klicken Sie im **Explorer** mit der rechten Maustaste auf den Ordner *publish* (oder klicken Sie unter macOS bei gedrückter <kbd>CTRL-TASTE</kbd> darauf), und wählen Sie **In Terminal öffnen** aus.

   :::image type="content" source="media/publishing-with-visual-studio-code/open-in-terminal.png" alt-text="Kontextmenü mit „In Terminal öffnen“":::

1. Führen Sie die App unter Windows und Linux mithilfe der ausführbaren Datei aus.

   1. Geben Sie unter Windows `.\HelloWorld.exe` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.

   1. Geben Sie unter Linux `./HelloWorld` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.

   1. Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.

1. Sie können die App auf jeder Plattform über den Befehl [`dotnet`](../tools/dotnet.md) ausführen:

   1. Geben Sie `dotnet HelloWorld.dll` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.

   1. Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [.NET Core-Anwendungsbereitstellung](../deploying/index.md)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine Konsolen-App veröffentlicht. Im nächsten Tutorial erstellen Sie eine Klassenbibliothek.

> [!div class="nextstepaction"]
> [Erstellen einer .NET Standard-Bibliothek in Visual Studio Code](library-with-visual-studio-code.md)
