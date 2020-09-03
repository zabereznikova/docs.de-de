---
title: Veröffentlichen einer .NET Core-Konsolenanwendung in Visual Studio
description: Bei der Veröffentlichung werden die Dateien erstellt, die zum Ausführen Ihrer .NET Core-Anwendung benötigt werden.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: e0033d52ab54259ce5e4ccf2a25bf4e3d4f244de
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867554"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio"></a>Tutorial: Veröffentlichen einer .NET Core-Konsolenanwendung in Visual Studio

In diesem Tutorial wird gezeigt, wie eine Konsolen-App veröffentlicht wird, damit sie von anderen Benutzern ausgeführt werden kann. Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer Anwendung benötigt werden. Zum Bereitstellen der Dateien kopieren Sie diese auf den Zielcomputer.

## <a name="prerequisites"></a>Voraussetzungen

- Dieses Tutorial kann mit der Konsolen-App durchgeführt werden, die Sie in [Tutorial: Erstellen einer .NET Core-Konsolenanwendung mit Visual Studio](with-visual-studio.md) erstellen.

## <a name="publish-the-app"></a>Veröffentlichen der App

1. Starten Sie Visual Studio.

1. Öffnen Sie das *HelloWorld*-Projekt, das Sie in [Tutorial: Erstellen einer .NET Core-Konsolenanwendung mit Visual Studio](with-visual-studio.md) erstellt haben.

1. Stellen Sie sicher, dass Visual Studio die Releasebuildkonfiguration verwendet. Ändern Sie ggf. die Einstellung der Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Release**.

   ![Visual Studio-Symbolleiste mit ausgewähltem Releasebuild](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. Klicken Sie mit der rechten Maustaste auf das **HelloWorld**-Projekt (nicht die HelloWorld-Projektmappe), und wählen Sie **Veröffentlichen** im Menü.

   ![Visual Studio-Kontextmenü zum Veröffentlichen](media/publishing-with-visual-studio/publish-context-menu.png)

1. Wählen Sie auf der Registerkarte **Ziel** der Seite **Veröffentlichen** die Option **Ordner** aus, und wählen Sie dann **Weiter** aus.

   ![Auswählen eines Veröffentlichungsziels in Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)

1. Wählen Sie auf der Registerkarte **Speicherort** der Seite **Veröffentlichen** die Option **Fertig stellen** aus.

   ![Registerkarte „Speicherort“ der Seite „Veröffentlichen“ von Visual Studio](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. Wählen Sie auf der Registerkarte **Veröffentlichen** des Fensters **Veröffentlichen** die Option **Veröffentlichen** aus.

   ![Visual Studio-Veröffentlichungsfenster](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a>Untersuchen der Dateien

Der Veröffentlichungsprozess erstellt standardmäßig eine frameworkabhängige Bereitstellung. Das ist ein Bereitstellungstyp, bei dem die veröffentlichte Anwendung auf einem Computer ausgeführt werden kann, auf dem die .NET Core-Runtime installiert ist. Benutzer können die veröffentlichte App ausführen, indem Sie auf die ausführbare Datei doppelklicken oder den Befehl `dotnet HelloWorld.dll` an einer Eingabeaufforderung ausgeben.

In den folgenden Schritten sehen Sie sich die durch den Veröffentlichungsvorgang erstellten Dateien an.

1. Wählen Sie im **Projektmappen-Explorer** die Option **Alle Dateien anzeigen** aus.

1. Erweitern Sie im Projektordner *bin/Release/netcoreapp3.1/publish*.

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Projektmappen-Explorer zeigt veröffentlichte Dateien an":::

   Wie in der folgenden Abbildung gezeigt, enthält die veröffentlichte Ausgabe die folgenden Dateien:

   * *HelloWorld.deps.json*

      Dies ist Datei für Runtimeabhängigkeiten der Anwendung. In dieser werden die Komponenten und Bibliotheken (einschließlich der Dynamic Link Library, die Ihre Anwendung enthält) von .NET Core definiert, die zum Ausführen der App erforderlich sind. Weitere Informationen finden Sie unter [Konfigurationsdateien der Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

   * *HelloWorld.dll*

      Dies ist die [frameworkabhängige Bereitstellungsversion](../deploying/deploy-with-cli.md#framework-dependent-deployment) der Anwendung. Um diese Dynamic Link Library (DLL) auszuführen, geben Sie an einer Eingabeaufforderung `dotnet HelloWorld.dll` ein. Diese Methode zum Ausführen der App funktioniert auf allen Plattformen, auf denen die .NET Core-Runtime installiert ist.

   * *HelloWorld.exe*

      Dies ist die [frameworkabhängige ausführbare Dateiversion](../deploying/deploy-with-cli.md#framework-dependent-executable) der Anwendung. Geben Sie `HelloWorld.exe` an einer Eingabeaufforderung ein, um sie auszuführen. Die Datei ist betriebssystemspezifisch.

   * *HelloWorld.pdb* (optional für die Bereitstellung)

      Dies ist die Debugsymboldatei. Sie müssen die Datei nicht zusammen mit der Anwendung bereitstellen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.

   * *HelloWorld.runtimeconfig.json*

      Dies ist die Runtimekonfigurationsdatei der Anwendung. Diese Datei identifiziert die Version von .NET Core, für die Ihre Anwendung erstellt wurde. Außerdem können Sie Konfigurationsoptionen hinzufügen. Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Ausführen der veröffentlichten App

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Ordner *publish*, und wählen Sie anschließend **Vollständigen Pfad kopieren** aus.

1. Öffnen Sie eine Eingabeaufforderung, und navigieren Sie zum Ordner *publish*. Geben Sie dazu `cd` ein, und fügen Sie dann den vollständigen Pfad ein. Zum Beispiel:

   ```console
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. Führen Sie die App mithilfe der ausführbaren Datei aus:

   1. Geben Sie `HelloWorld.exe` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.

   1. Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.

1. Führen Sie die App mit dem Befehl `dotnet` aus:

   1. Geben Sie `dotnet HelloWorld.dll` ein, und drücken Sie die <kbd>EINGABETASTE</kbd>.

   1. Geben Sie als Antwort auf die Eingabeaufforderung einen Namen ein, und drücken Sie zum Beenden eine beliebige Taste.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [.NET Core-Anwendungsbereitstellung](../deploying/index.md)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine Konsolen-App veröffentlicht. Im nächsten Tutorial erstellen Sie eine Klassenbibliothek.

> [!div class="nextstepaction"]
> [Erstellen einer .NET-Standard-Bibliothek in Visual Studio](library-with-visual-studio.md)
