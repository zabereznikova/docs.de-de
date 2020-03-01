---
title: Veröffentlichen Ihrer .NET Core-Anwendung „Hello World“ mit Visual Studio
description: Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer .NET Core-Anwendung benötigt werden.
author: BillWagner
ms.author: wiwagn
ms.date: 12/10/2019
ms.custom: vs-dotnet
ms.openlocfilehash: bdd6e28713bdece2bd144e6763bd84d719e91449
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156633"
---
# <a name="publish-your-net-core-hello-world-application-with-visual-studio"></a>Veröffentlichen Ihrer .NET Core-Anwendung „Hello World“ mit Visual Studio

Unter [Erstellen einer Hello World-Anwendung mit .NET Core in Visual Studio](with-visual-studio.md) haben Sie eine Hello World-Konsolenanwendung erstellt. Unter [Debuggen Ihrer Hello World-Anwendung mit Visual Studio](debugging-with-visual-studio.md) haben Sie diese mithilfe des Visual Studio-Debuggers getestet. Nun, da Sie sicher sind, dass sie erwartungsgemäß funktioniert, können Sie sie veröffentlichen, damit andere Benutzer sie ausführen können. Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer Anwendung benötigt werden. Zum Bereitstellen der Dateien kopieren Sie diese auf den Zielcomputer.

## <a name="publish-the-app"></a>Veröffentlichen der App

1. Stellen Sie sicher, dass Visual Studio die endgültige Produktversion der Anwendung erstellt. Ändern Sie ggf. die Einstellung der Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**.

   ![Visual Studio-Symbolleiste mit ausgewähltem Releasebuild](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. Klicken Sie mit der rechten Maustaste auf das **HelloWorld**-Projekt (nicht die HelloWorld-Projektmappe), und wählen Sie **Veröffentlichen** im Menü. (Sie können auch **HelloWorld veröffentlichen** im Hauptmenü **Erstellen** von Visual Studio auswählen.)

   ![Visual Studio-Kontextmenü zum Veröffentlichen](media/publishing-with-visual-studio/publish-context-menu.png)

1. Wählen Sie auf der Seite **Veröffentlichungsziel auswählen** die Option **Ordner**aus, und wählen Sie dann **Profil erstellen** aus.

   ![Auswählen eines Veröffentlichungsziels in Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)

1. Wählen Sie auf der Seite **Veröffentlichen** die Option **Veröffentlichen** aus.

   ![Visual Studio-Veröffentlichungsfenster](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a>Untersuchen der Dateien

Der Veröffentlichungsprozess erstellt eine frameworkabhängige Bereitstellung. Dies ist ein Bereitstellungstyp, bei dem die veröffentlichte Anwendung auf jeder Plattform ausgeführt werden kann, die von .NET Core unterstützt wird, wenn .NET Core auf dem System installiert ist. Benutzer können die veröffentlichte App ausführen, indem Sie auf die ausführbare Datei doppelklicken oder den Befehl `dotnet HelloWorld.dll` an einer Eingabeaufforderung ausgeben.

In den folgenden Schritten sehen Sie sich die durch den Veröffentlichungsvorgang erstellten Dateien an.

1. Öffnen Sie eine Eingabeaufforderung.

   Eine Möglichkeit, eine Eingabeaufforderung zu öffnen, ist die Eingabe von **Eingabeaufforderung** (oder kurz **cmd**) in das Suchfeld auf der Windows-Taskleiste. Wählen Sie die Desktop-App **Eingabeaufforderung** aus, oder drücken Sie die **EINGABETASTE**, wenn sie in den Suchergebnissen bereits ausgewählt ist.

1. Navigieren Sie zu der veröffentlichen Anwendung im Unterverzeichnis *bin\Release\netcoreapp3.1\publish* des Projektverzeichnisses der Anwendung.

   ![Konsolenfenster, das veröffentlichte Dateien zeigt](media/publishing-with-visual-studio/published-files-output.png)

   Wie in der folgenden Abbildung gezeigt, enthält die veröffentlichte Ausgabe die folgenden Dateien:

      * *HelloWorld.deps.json*

         Dies ist Datei für Runtimeabhängigkeiten der Anwendung. In dieser werden die Komponenten und Bibliotheken (einschließlich der Dynamic Link Library, die Ihre Anwendung enthält) von .NET Core definiert, die zum Ausführen der App erforderlich sind. Weitere Informationen finden Sie unter [Konfigurationsdateien der Runtime](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

      * *HelloWorld.dll*

         Dies ist die [frameworkabhängige Bereitstellungsversion](../deploying/deploy-with-cli.md#framework-dependent-deployment) der Anwendung. Um diese Dynamic Link Library (DLL) auszuführen, geben Sie an einer Eingabeaufforderung `dotnet HelloWorld.dll` ein.

      * *HelloWorld.exe*

         Dies ist die [frameworkabhängige ausführbare Dateiversion](../deploying/deploy-with-cli.md#framework-dependent-executable) der Anwendung. Geben Sie `HelloWorld.exe` an einer Eingabeaufforderung ein, um sie auszuführen.

      * *HelloWorld.pdb* (optional für die Bereitstellung)

         Dies ist die Debugsymboldatei. Sie müssen die Datei nicht zusammen mit der Anwendung bereitstellen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.

      * *HelloWorld.runtimeconfig.json*

         Dies ist die Runtimekonfigurationsdatei der Anwendung. Diese Datei identifiziert die Version von .NET Core, für die Ihre Anwendung erstellt wurde. Außerdem können Sie Konfigurationsoptionen hinzufügen. Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [.NET Core-Anwendungsbereitstellung](../deploying/index.md)
