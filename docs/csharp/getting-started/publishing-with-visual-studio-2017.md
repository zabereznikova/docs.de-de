---
title: "Veröffentlichen Ihrer „Hello World“-Anwendung mit Visual Studio 2017"
description: "Veröffentlichen Ihrer „Hello World“-Anwendung mit Visual Studio 2017"
keywords: ".NET, .NET Core, .NET Core-Konsolenanwendung, Veröffentlichung (.NET Core), Bereitstellung (.NET Core)"
author: stevehoag
ms.author: shoag
ms.date: 10/24/2016
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f4a30d19e111d395088e38c4543c9dacee6105fd
ms.lasthandoff: 03/13/2017

---

# <a name="publishing-your-hello-world-application-with-visual-studio-2017"></a>Veröffentlichen Ihrer „Hello World“-Anwendung mit Visual Studio 2017

In [Building a C# Hello World application with .NET Core in Visual Studio 2017](with-visual-studio-2017.md) (Erstellen einer C#-„Hello World“-Anwendung mit .NET Core in Visual Studio 2017) haben Sie Ihre „Hello World“-Konsolenanwendung erstellt, und in [Debugging your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio-2017.md) (Debuggen Ihrer C#-„Hello World“-Anwendung mit Visual Studio 2017) haben Sie sie mithilfe des Visual Studio-Debuggers getestet. Nun, da Sie sicher sind, dass sie erwartungsgemäß funktioniert, können Sie sie veröffentlichen, damit andere Benutzer sie ausführen können. Bei der Veröffentlichung wird der Satz von Dateien erstellt, die zum Ausführen der Anwendung erforderlich sind. Sie können sie durch Kopieren auf einen Zielcomputer bereitstellen.

So veröffentlichen Sie Ihre Anwendung und führen sie aus: 

1. Stellen Sie sicher, dass Visual Studio die endgültige Produktversion der Anwendung erstellt. Ändern Sie ggf. die Einstellung der Buildkonfiguration auf der Symbolleiste von **Debuggen** in **Freigabe**, wie in der folgenden Abbildung dargestellt.

   ![Bild](media/release.jpg)

1. Öffnen Sie ein Konsolenfenster. Geben Sie beispielsweise im Textfeld **Frag mich etwas** in der Windows-Taskleiste `Command Prompt` ein, und wählen Sie dann die Desktop-App **Eingabeaufforderung** aus, um das Konsolenfenster zu öffnen.

1. Klicken Sie mit der rechten Maustaste auf das HelloWorld-Projekt (nicht die HelloWorld-Projektmappe), und wählen Sie **Veröffentlichen** im Menü. Sie können auch **HelloWorld veröffentlichen** im Hauptmenü **Build** von Visual Studio auswählen.

1. Wenn das in der folgenden Abbildung dargestellte Dialogfeld **Veröffentlichen** angezeigt wird, erstellen Sie durch Auswahl von **Neues Profil erstellen** ein neues Veröffentlichungsprofil.

1. Wählen Sie im Dialogfeld **Veröffentlichungsziel auswählen**, das in der folgenden Abbildung dargestellt wird, die Schaltfläche **OK**, um Ihre Anwendung in Ihrem lokalen Dateisystem zu veröffentlichen. Sie befindet sich im Unterverzeichnis „bin\release\PublishOutput“ des Projektverzeichnisses Ihrer Anwendung.

1. Da Sie nun ein Veröffentlichungsprofil erstellt haben, wählen Sie die Schaltfläche **Veröffentlichen** im Dialogfeld **Veröffentlichen**, das in der folgenden Abbildung dargestellt ist.

   ![Bild](media/publish-2.jpg)

1. Wie die folgende Abbildung zeigt, umfasst die veröffentlichte Ausgabe die folgenden drei Dateien, die die Anwendung bilden, und die Sie durch Kopieren in ein Zielsystem bereitstellen können:

      - HelloWorld.dll
   
      - HelloWorld.deps.json

      - HelloWorld.runtimeconfig.json

   Eine vierte Datei, „HelloWorld.pdb“, enthält die Debugsymbole. Sie müssen die Datei nicht zusammen mit der Anwendung verteilen, obwohl Sie sie speichern sollten für den Fall, dass Sie die veröffentlichte Version der Anwendung debuggen müssen.

   ![Bild](media/pub-files.jpg)

Der Veröffentlichungsprozess erstellt eine Framework-abhängige Bereitstellung; die veröffentlichte Anwendung kann auf jeder Plattform ausgeführt werden, die von .NET Core unterstützt wird, solange .NET Core auf dem System installiert ist. Benutzer können Ihre Anwendung durch Eingabe des `dotnet.exe HelloWorld.dll`-Befehls in einem Konsolenfenster ausführen.

Weitere Informationen zum Veröffentlichen und Bereitstellen von .NET Core-Anwendungen finden Sie unter [.NET Core Anwendungsbereitstellung](../../core/deploying/index.md).
