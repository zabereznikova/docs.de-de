---
title: "Veröffentlichen Ihrer „Hallo Welt“-Anwendung mit Visual Studio 2017"
description: "Die Veröffentlichung erstellt eine Reihe von Dateien, die zum Ausführen Ihrer Anwendung benötigt werden."
keywords: ".NET, .NET Core, Konsolenanwendung, Veröffentlichung, Bereitstellung"
author: BillWagner
ms.author: wiwagn
ms.date: 10/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
ms.openlocfilehash: a3e5bda5c99144c9ab5bbaf5e2f5566261af4813
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="publish-your-hello-world-application-with-visual-studio-2017"></a>Veröffentlichen Ihrer „Hallo Welt“-Anwendung mit Visual Studio 2017

In [Build a C# Hello World Application with .NET Core in Visual Studio 2017 (Erstellen einer „Hallo Welt“-Anwendung in C# mit .NET Core in Visual Studio 2017](with-visual-studio.md)) oder [Build a Visual Basic Hallo Welt Application with .NET Core in Visual Studio 2017 (Erstellen einer „Hallo Welt“-Anwendung in Visual Basic mit .NET Core in Visual Studio 2017)](vb-with-visual-studio.md) haben Sie eine „Hallo Welt“-Konsolenanwendung erstellt. In [Debug your C# Hello World application with Visual Studio 2017 (Debuggen Ihrer C#-Anwendung „Hallo Welt“ mit Visual Studio 2017)](debugging-with-visual-studio.md) haben Sie diese mithilfe des Visual Studio-Debuggers getestet. Nun, da Sie sicher sind, dass sie erwartungsgemäß funktioniert, können Sie sie veröffentlichen, damit andere Benutzer sie ausführen können. Bei der Veröffentlichung wird der Satz von Dateien erstellt, die zum Ausführen der Anwendung erforderlich sind. Sie können sie durch Kopieren auf einen Zielcomputer bereitstellen.

So veröffentlichen Sie Ihre Anwendung und führen sie aus: 

1. Stellen Sie sicher, dass Visual Studio die endgültige Produktversion der Anwendung erstellt. Ändern Sie ggf. die Einstellung der Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**.

   ![Visual Studio-Symbolleiste](media/publishing-with-visual-studio/toolbar.png)

1. Klicken Sie mit der rechten Maustaste auf das **HelloWorld**-Projekt (nicht die HelloWorld-Projektmappe), und wählen Sie **Veröffentlichen** im Menü. Sie können auch **HelloWorld veröffentlichen** im Hauptmenü **Build** von Visual Studio auswählen.

   ![Visual Studio-Symbolleiste](media/publishing-with-visual-studio/publish1.png)


   ![Visual Studio-Symbolleiste](media/publishing-with-visual-studio/publishwindow.png)

1. Öffnen Sie ein Konsolenfenster. Geben Sie z.B. im Textfeld **Geben Sie hier Text für die Suche ein** in der Windows-Taskleiste `Command Prompt` (oder `cmd` als Abkürzung) ein, und öffnen Sie ein Konsolenfenster, indem Sie entweder die Desktopanwendung **Eingabeaufforderung** auswählen oder die EINGABETASTE drücken, wenn die Anwendung in den Suchergebnissen angezeigt wird.

1. Navigieren Sie zu der veröffentlichen Anwendung im `bin\release\PublishOutput`-Unterverzeichnis des Projektverzeichnisses Ihrer Anwendung. Wie in der folgenden Abbildung gezeigt, enthält die veröffentlichte Ausgabe die folgenden vier Dateien:

      * *HelloWorld.deps.json*

         Abhängigkeiten Laufzeitdatei der Anwendung. Definiert die .NET Core-Komponenten und die Bibliotheken (einschließlich der dynamic Link Library, die die Anwendung enthält), die zum Ausführen der Anwendung erforderlich sind. Weitere Informationen finden Sie unter [Runtime Konfigurationsdateien](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).
 
      * *HelloWorld.dll*

         Die Datei, die die Anwendung enthält. Es ist eine dynamic Link Library, der durch Eingabe ausgeführt werden, kann die `dotnet HelloWorld.dll` Befehl in einem Konsolenfenster. 

      * *HelloWorld.pdb* (optional für die Bereitstellung)

         Eine Datei, die Debugsymbole enthält. Sie müssen die Datei nicht zusammen mit der Anwendung bereitstellen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.

      * *HelloWorld.runtimeconfig.json*

         Common Language Runtime-Konfigurationsdatei der Anwendung. Er identifiziert die Version von .NET Core, die Ihre Anwendung erstellt wurde, führen Sie auf. Weitere Informationen finden Sie unter [Runtime Konfigurationsdateien](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).  

   ![Konsolenfenster, das veröffentlichte Dateien zeigt](media/publishing-with-visual-studio/publishedfiles.png)

Der Veröffentlichungsprozess erstellt eine Framework-abhängige Bereitstellung, was ein Bereitstellungstyp ist, wobei die veröffentlichte Anwendung auf jeder Plattform ausgeführt werden kann, die von .NET Core unterstützt wird, wenn .NET Core auf dem System installiert ist. Benutzer können Ihre Anwendung durch Eingabe des `dotnet HelloWorld.dll`-Befehls in einem Konsolenfenster ausführen.

Weitere Informationen zum Veröffentlichen und Bereitstellen von .NET Core-Anwendungen finden Sie unter [.NET Core Anwendungsbereitstellung](../../core/deploying/index.md).
