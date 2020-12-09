---
title: Veröffentlichen einer .NET-Konsolenanwendung mit Visual Studio für Mac
description: Hier erfahren Sie, wie Sie mit Visual Studio für Mac die Dateien erstellen, die zum Ausführen einer .NET-Anwendung benötigt werden.
ms.date: 11/30/2020
ms.openlocfilehash: 88f143011b19ca8eda6610803c894e619d06a635
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599184"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio-for-mac"></a>Tutorial: Veröffentlichen einer .NET-Konsolenanwendung mit Visual Studio für Mac

In diesem Tutorial wird gezeigt, wie eine Konsolen-App veröffentlicht wird, damit sie von anderen Benutzern ausgeführt werden kann. Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer Anwendung benötigt werden. Zum Bereitstellen der Dateien kopieren Sie diese auf den Zielcomputer.

## <a name="prerequisites"></a>Voraussetzungen

- Dieses Tutorial kann mit der Konsolen-App durchgeführt werden, die Sie in [Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio für Mac](with-visual-studio-mac.md) erstellen.

## <a name="publish-the-app"></a>Veröffentlichen der App

1. Starten Sie Visual Studio für Mac.

1. Öffnen Sie das HelloWorld-Projekt, das Sie in [Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio für Mac](with-visual-studio-mac.md) erstellt haben.

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

Der Veröffentlichungsprozess erstellt eine frameworkabhängige Bereitstellung. Dies ist ein Bereitstellungstyp, bei dem die veröffentlichte Anwendung auf einem Computer ausgeführt werden kann, auf dem die .NET-Runtime installiert ist. Benutzer können die veröffentlichte App ausführen, indem sie an einer Eingabeaufforderung den Befehl `dotnet HelloWorld.dll` aufrufen.

Wie in der vorherigen Abbildung gezeigt, enthält die veröffentlichte Ausgabe die folgenden Dateien:

* *HelloWorld.deps.json*

  Dies ist Datei für Runtimeabhängigkeiten der Anwendung. In dieser werden die Komponenten und Bibliotheken (einschließlich der Dynamic Link Library, die Ihre Anwendung enthält) von .NET definiert, die zum Ausführen der App erforderlich sind. Weitere Informationen finden Sie unter [Konfigurationsdateien der Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

* *HelloWorld.dll*

   Dies ist die [frameworkabhängige Bereitstellungsversion](../deploying/deploy-with-cli.md#framework-dependent-deployment) der Anwendung. Um diese Dynamic Link Library (DLL) auszuführen, geben Sie an einer Eingabeaufforderung `dotnet HelloWorld.dll` ein. Diese Methode zum Ausführen der App funktioniert auf allen Plattformen, auf denen die .NET-Runtime installiert ist.

* *HelloWorld.pdb* (optional für die Bereitstellung)

   Dies ist die Debugsymboldatei. Sie müssen die Datei nicht zusammen mit der Anwendung bereitstellen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.

* *HelloWorld.runtimeconfig.json*

   Dies ist die Runtimekonfigurationsdatei der Anwendung. Diese Datei identifiziert die Version von .NET, für die Ihre Anwendung erstellt wurde. Außerdem können Sie Konfigurationsoptionen hinzufügen. Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET-Runtime](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Ausführen der veröffentlichten App

1. Öffnen Sie ein Terminal, und navigieren Sie zum Ordner *publish*. Geben Sie dazu `cd` ein, und fügen Sie dann den zuvor kopierten Pfad ein. Zum Beispiel:

   ```console
   cd ~/Projects/HelloWorld/HelloWorld/bin/Release/net5.0/publish/
   ```

1. Führen Sie die App mit dem Befehl `dotnet` aus:

   1. Geben Sie `dotnet HelloWorld.dll` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.

   1. Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [.NET-Anwendungsbereitstellung](../deploying/index.md)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine Konsolen-App veröffentlicht. Im nächsten Tutorial erstellen Sie eine Klassenbibliothek.

> [!div class="nextstepaction"]
> [Erstellen einer .NET-Bibliothek in Visual Studio für Mac](library-with-visual-studio-mac.md)
