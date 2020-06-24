---
title: Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio für Mac
description: Bei der Veröffentlichung werden die Dateien erstellt, die zum Ausführen Ihrer .NET Core-Anwendung benötigt werden.
ms.date: 06/08/2020
ms.openlocfilehash: 67762481d3a56b8473e643f71b8df909b6e54fc6
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713352"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio-for-mac"></a>Tutorial: Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio für Mac

In diesem Tutorial wird gezeigt, wie eine Konsolen-App veröffentlicht wird, damit sie von anderen Benutzern ausgeführt werden kann. Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer Anwendung benötigt werden. Zum Bereitstellen der Dateien kopieren Sie diese auf den Zielcomputer.

## <a name="prerequisites"></a>Voraussetzungen

- Dieses Tutorial funktioniert mit der Konsolen-App, die Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio für Mac](with-visual-studio-mac.md) erstellen.

## <a name="publish-the-app"></a>Veröffentlichen der App

1. Starten Sie Visual Studio für Mac.

1. Öffnen Sie das Projekt HelloWorld, das Sie in [Erstellen einer .NET Core-Konsolenanwendung in Visual Studio für Mac](with-visual-studio-mac.md) erstellt haben.

1. Stellen Sie sicher, dass Visual Studio die endgültige Produktversion der Anwendung erstellt. Ändern Sie ggf. die Einstellung der Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**.

   :::image type="content" source="media/publishing-with-visual-studio-mac/toolbar-release.png" alt-text="Visual Studio-Symbolleiste mit ausgewähltem Releasebuild":::

1. Wählen Sie im Hauptmenü **Build** > **In Ordner veröffentlichen...** aus.

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-context-menu.png" alt-text="Visual Studio-Kontextmenü „Veröffentlichen“":::

1. Wählen Sie im Dialogfeld **In Ordner veröffentlichen** den Befehl **Veröffentlichen** aus.

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-to-folder-dialog.png" alt-text="Visual Studio-Dialogfeld „In Ordner veröffentlichen“":::

   Der Ordner „publish“ wird mit den erstellten Dateien geöffnet.

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-folder.png" alt-text="Ordner „publish“":::

1. Wählen Sie das Zahnradsymbol und dann im Kontextmenü **„publish“ als Pfadname kopieren**.

   :::image type="content" source="media/publishing-with-visual-studio-mac/copy-path.png" alt-text="Kopieren des Pfads zum Ordner „publish“":::

## <a name="inspect-the-files"></a>Untersuchen der Dateien

Der Veröffentlichungsprozess erstellt eine frameworkabhängige Bereitstellung. Dies ist ein Bereitstellungstyp, bei dem die veröffentlichte Anwendung auf einem Computer ausgeführt werden kann, auf dem die .NET Core Runtime installiert ist. Benutzer können die veröffentlichte App ausführen, indem sie an einer Eingabeaufforderung den Befehl `dotnet HelloWorld.dll` aufrufen.

Wie in der vorherigen Abbildung gezeigt, enthält die veröffentlichte Ausgabe die folgenden Dateien:

* *HelloWorld.deps.json*

  Dies ist Datei für Runtimeabhängigkeiten der Anwendung. In dieser werden die Komponenten und Bibliotheken (einschließlich der Dynamic Link Library, die Ihre Anwendung enthält) von .NET Core definiert, die zum Ausführen der App erforderlich sind. Weitere Informationen finden Sie unter [Konfigurationsdateien der Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

* *HelloWorld.dll*

   Dies ist die [frameworkabhängige Bereitstellungsversion](../deploying/deploy-with-cli.md#framework-dependent-deployment) der Anwendung. Um diese Dynamic Link Library (DLL) auszuführen, geben Sie an einer Eingabeaufforderung `dotnet HelloWorld.dll` ein. Diese Methode zum Ausführen der App funktioniert auf allen Plattformen, auf denen die .NET Core-Runtime installiert ist.

* *HelloWorld.pdb* (optional für die Bereitstellung)

   Dies ist die Debugsymboldatei. Sie müssen die Datei nicht zusammen mit der Anwendung bereitstellen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.

* *HelloWorld.runtimeconfig.json*

   Dies ist die Runtimekonfigurationsdatei der Anwendung. Diese Datei identifiziert die Version von .NET Core, für die Ihre Anwendung erstellt wurde. Außerdem können Sie Konfigurationsoptionen hinzufügen. Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Ausführen der veröffentlichten App

1. Öffnen Sie ein Terminal, und navigieren Sie zum Ordner *publish*. Geben Sie dazu `cd` ein, und fügen Sie dann den zuvor kopierten Pfad ein. Zum Beispiel:

   ```
   cd ~/Projects/HelloWorld/HelloWorld/bin/Release/netcoreapp3.1/publish/
   ```

1. Führen Sie die App mit dem Befehl `dotnet` aus:

   1. Geben Sie `dotnet HelloWorld.dll` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.

   1. Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [.NET Core-Anwendungsbereitstellung](../deploying/index.md)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine Konsolen-App veröffentlicht. Im nächsten Tutorial erstellen Sie eine Klassenbibliothek.

> [!div class="nextstepaction"]
> [Erstellen einer .NET Standard-Bibliothek in Visual Studio für Mac](library-with-visual-studio-mac.md)
