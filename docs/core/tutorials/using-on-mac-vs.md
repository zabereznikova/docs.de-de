---
title: "Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac"
description: "Dieses Thema führt Sie durch die Erstellung einer einfachen Konsolenanwendung mit Visual Studio für Mac und .NET Core."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: get-started-article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8902e849-dd17-42c0-8264-cc7ae3927a0c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e11515031716a66ead866e52504137cb4e1df137
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a>Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac

Visual Studio für Mac bietet eine umfassende integrierte Entwicklungsumgebung (IDE) für die Entwicklung von .NET Core-Anwendungen. Dieses Thema führt Sie durch die Erstellung einer einfachen Konsolenanwendung mit Visual Studio für Mac und .NET Core.

> [!NOTE]
> Ihr Feedback ist uns sehr wichtig. Es gibt zwei Möglichkeiten, wie Sie Feedback für das Entwicklungsteam von Visual Studio für Mac bereitstellen können:
> * Klicken Sie in Visual Studio für Mac auf **Hilfe** > **Ein Problem melden** im Menü oder auf **Ein Problem melden** auf der Willkommensseite. Dadurch wird ein Fenster für das Ablegen eines Fehlerberichts geöffnet. Sie können Ihr Feedback im Portal der [Entwicklercommunity](https://developercommunity.visualstudio.com/spaces/8/index.html) verfolgen.
> * Um einen Vorschlag zu machen, klicken Sie auf **Hilfe** > **Vorschlag senden** im Menü oder auf **Vorschlag senden** auf der Willkommensseite. Dadurch gelangen Sie zur [Visual Studio for Mac UserVoice webpage (UserVoice-Webseite von Visual Studio für Mac)](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).

## <a name="prerequisites"></a>Erforderliche Komponenten

Weitere Informationen finden Sie unter dem Thema [Voraussetzungen für .NET Core unter Mac](../../core/macos-prerequisites.md).

## <a name="getting-started"></a>Erste Schritte

Wenn Sie bereits die erforderlichen Komponenten und Visual Studio für Mac installiert haben, überspringen Sie diesen Abschnitt, und fahren Sie mit [Erstellen eines Projekts](#creating-a-project) fort. Um die erforderlichen Komponenten und Visual Studio für Mac zu installieren, gehen Sie wie folgt vor:

Laden Sie den [Visual Studio für Mac-Installer](https://www.visualstudio.com/vs/visual-studio-mac/) herunter. Führen Sie den Installer aus. Lesen und akzeptieren Sie die Lizenzbedingungen. Während der Installation haben Sie die Möglichkeit zum Installieren von Xamarin, einer plattformübergreifenden mobilen App-Entwicklungstechnologie. Das Installieren von Xamarin und den zugehörigen Komponenten ist für die Entwicklung mit .NET Core optional. Eine exemplarische Vorgehensweise für den Visual Studio für Mac-Installationsvorgang finden Sie unter [Introducing Visual Studio for Mac (Einführung in Visual Studio für Mac)](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/). Wenn die Installation abgeschlossen ist, starten Sie Visual Studio für Mac-IDE.

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

