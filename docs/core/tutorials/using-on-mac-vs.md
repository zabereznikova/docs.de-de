---
title: "Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac | Microsoft-Dokumentation"
description: "Dieses Thema führt Sie durch die Erstellung einer einfachen Konsolenanwendung mit Visual Studio für Mac und .NET Core."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 03/16/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8902e849-dd17-42c0-8264-cc7ae3927a0c
translationtype: Human Translation
ms.sourcegitcommit: ff143583ba62fc1d82561e739a75107e50ebee88
ms.openlocfilehash: ed8787d72647f18544bde8ed721cf37f31fbb5fe
ms.lasthandoff: 03/20/2017

---

# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a>Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac

Visual Studio für Mac bietet eine umfassende integrierte Entwicklungsumgebung (IDE) für die Entwicklung von .NET Core-Anwendungen. Dieses Thema führt Sie durch die Erstellung einer einfachen Konsolenanwendung mit Visual Studio für Mac und .NET Core.

> [!NOTE]
> Visual Studio Tools für Mac ist eine Preview-Software. Wie mit allen Preview-Versionen von Microsoft-Produkten, wird Ihr Feedback sehr geschätzt. Es gibt zwei Möglichkeiten, wie Sie Feedback für das Entwicklungsteam von Visual Studio für Mac bereitstellen können:
> * Wählen Sie in Visual Studio für Mac **Hilfe > Ein Problem melden** aus dem Menü oder **Ein Problem melden** von der Willkommensseite aus, sodass ein Fenster für das Ablegen eines Fehlerberichts geöffnet wird.
> * Um einen Vorschlag zu machen, wählen Sie **Hilfe > Vorschlag senden** aus dem Menü oder **Vorschlag senden** von der Willkommensseite aus, sodass Sie zur [Visual Studio for Mac UserVoice webpage (UserVoice-Webseite von Visual Studio für Mac)](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac) gelangen.

## <a name="prerequisites"></a>Erforderliche Komponenten

[.NET Core und OpenSSL](https://www.microsoft.com/net/core#macos)

Weitere Informationen über erforderliche Komponenten finden Sie unter [Prerequisites for .NET Core on Mac (Erforderliche Komponenten für .NET Core unter Mac)](../../core/macos-prerequisites.md).

## <a name="getting-started"></a>Erste Schritte

Wenn Sie bereits die erforderlichen Komponenten und Visual Studio für Mac installiert haben, überspringen Sie diesen Abschnitt, und fahren Sie mit [Erstellen eines Projekts](#creating-a-project) fort. Um die erforderlichen Komponenten und Visual Studio für Mac zu installieren, gehen Sie wie folgt vor:

1. Laden Sie [.NET Core und OpenSSL](https://www.microsoft.com/net/core#macos) herunter und installieren Sie es.

1. Laden Sie den [Visual Studio für Mac-Installer](https://www.visualstudio.com/vs/visual-studio-mac/) herunter. Führen Sie den Installer aus. Lesen und akzeptieren Sie die Lizenzbedingungen. Während der Installation haben Sie die Möglichkeit zum Installieren von Xamarin, eine plattformübergreifende mobile App-Entwicklungstechnologie. Das Installieren von Xamarin und den zugehörigen Komponenten ist für die Entwicklung mit .NET Core optional. Eine exemplarische Vorgehensweise für den Visual Studio für Mac-Installationsvorgang finden Sie unter [Introducing Visual Studio for Mac (Einführung in Visual Studio für Mac)](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/). Wenn die Installation abgeschlossen ist, starten Sie Visual Studio für Mac-IDE.

## <a name="creating-a-project"></a>Erstellen eines Projekts

1. Wählen Sie **Neues Projekt** auf der Willkommensseite aus.

   ![Schaltfläche für „Neues Projekt“ auf der Willkommensseite von Visual Studio für Mac](./media/using-on-mac-vs/vsmac1.png)

1. Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **.NET Core** **App** aus. Wählen Sie die **Konsolenanwendung**-Vorlage und anschließend **Weiter** aus.

   ![Liste neuer Projektvorlagen](./media/using-on-mac-vs/vsmac2.png)

1. Geben Sie „HelloWorld“ als **Projektname** ein. Wählen Sie **Erstellen** aus.

   ![Dialogfeld „Konfigurieren Sie Ihre neue Konsolenanwendung“](./media/using-on-mac-vs/vsmac3.png)

1. Warten Sie, während die Abhängigkeiten des Projekts wiederhergestellt werden. Das Projekt enthält eine einzelne C#-Datei, *Program.cs*, mit einer `Program`-Klasse mit einer `Main`-Methode. Die `Console.WriteLine`-Anweisung wird „Hello World!“ in der Konsole ausgeben, wenn die App ausgeführt wird.

   ![Hauptfenster mit der geöffneten Datei „Program.cs“](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a>Ausführen der Anwendung

Führen Sie diese Anwendung durch Drücken von <kbd>F5</kbd> im Debugmodus oder durch Drücken von <kbd>STRG</kbd>+<kbd>F5</kbd> im Releasemodus aus.

![Der Ausgabebereich der Anwendung zeigt „Hello World!“ an](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a>Nächster Schritt

Das Thema [Building a complete .NET Core solution on macOS using Visual Studio for Mac (Erstellen einer vollständigen .NET Core-Projektmappe unter macOS mit Visual Studio für Mac)](using-on-mac-vs-full-solution.md) veranschaulicht Ihnen, wie Sie eine vollständige .NET Core-Projektmappe erstellen, die eine wiederverwendbare Bibliothek und Komponententests enthält.

