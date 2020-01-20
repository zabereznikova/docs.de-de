---
title: Erste Schritte mit .NET Core mit Visual Studio für Mac
description: Dieses Thema führt Sie durch die Erstellung einer einfachen Konsolenanwendung mit Visual Studio für Mac und .NET Core.
ms.date: 12/19/2019
ms.openlocfilehash: 4cd7e311411bce62698e291e763227496877ea39
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740491"
---
# <a name="get-started-with-net-core-on-macos-using-visual-studio-for-mac"></a>Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac

Visual Studio für Mac bietet eine umfassende integrierte Entwicklungsumgebung (IDE) für die Entwicklung von .NET Core-Anwendungen. Dieser Artikel führt Sie durch die Erstellung einer einfachen Konsolenanwendung mit Visual Studio für Mac und .NET Core.

> [!NOTE]
> Ihr Feedback ist uns sehr wichtig. Es gibt zwei Möglichkeiten, wie Sie Feedback für das Entwicklungsteam von Visual Studio für Mac bereitstellen können:
>
> * Klicken Sie in Visual Studio für Mac auf **Hilfe** > **Ein Problem melden** im Menü oder auf **Ein Problem melden** auf der Willkommensseite. Dadurch wird ein Fenster für das Ablegen eines Fehlerberichts geöffnet. Sie können Ihr Feedback im Portal der [Entwicklercommunity](https://developercommunity.visualstudio.com/spaces/8/index.html) verfolgen.
> * Um einen Vorschlag zu machen, wählen Sie **Hilfe** > **Vorschlag senden** im Menü oder **Vorschlag senden** auf der Willkommensseite aus. Dadurch gelangen Sie zur Webseite [Visual Studio für Mac-Entwicklercommunity](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## <a name="prerequisites"></a>Voraussetzungen

Informationen hierzu finden Sie im Artikel [.NET Core-Abhängigkeiten und -Anforderungen](../install/dependencies.md?pivots=os-macos).

Lesen Sie den Artikel [.NET Core-Unterstützung](/visualstudio/mac/net-core-support), um sicherzustellen, dass Sie eine unterstützte Version von .NET Core verwenden.

## <a name="get-started"></a>Erste Schritte

Wenn Sie bereits die erforderlichen Komponenten und Visual Studio für Mac installiert haben, überspringen Sie diesen Abschnitt, und fahren Sie mit [Erstellen eines Projekts](#creating-a-project) fort. Um die erforderlichen Komponenten und Visual Studio für Mac zu installieren, gehen Sie wie folgt vor:

Laden Sie den [Visual Studio für Mac-Installer](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) herunter. Führen Sie den Installer aus. Lesen und akzeptieren Sie die Lizenzbedingungen. Wählen Sie im Rahmen der Installation die Option zum Installieren von .NET Core aus. Sie haben die Möglichkeit, Xamarin zu installieren – eine plattformübergreifende Entwicklungstechnologie für mobile Apps. Das Installieren von Xamarin und den zugehörigen Komponenten ist für die Entwicklung mit .NET Core optional. Eine exemplarische Vorgehensweise für den Visual Studio für Mac-Installationsvorgang finden Sie in der [Dokumentation für Visual Studio für Mac](/visualstudio/mac/). Wenn die Installation abgeschlossen ist, starten Sie Visual Studio für Mac-IDE.

## <a name="creating-a-project"></a>Erstellen eines Projekts

1. Wählen Sie im Startfenster die Option **Neu** aus.

   ![Schaltfläche „Neu“ auf der Startseite von Visual Studio für Mac](./media/using-on-mac-vs/visual-studio-mac-new-project.png)

1. Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **.NET Core** **App** aus. Wählen Sie die **Konsolenanwendung**-Vorlage und anschließend **Weiter** aus.

   ![Liste neuer Projektvorlagen](./media/using-on-mac-vs/visual-studio-mac-new-dialog.png)

1. Sollten mehrere Versionen von .NET Core installiert sein, wählen Sie das Zielframework für Ihr Projekt aus.

1. Geben Sie „HelloWorld“ als **Projektname** ein. Wählen Sie **Erstellen** aus.

   ![Dialogfeld „Konfigurieren Sie Ihre neue Konsolenanwendung“](./media/using-on-mac-vs/visual-studio-mac-new-options.png)

1. Warten Sie, während die Abhängigkeiten des Projekts wiederhergestellt werden. Das Projekt enthält eine einzelne C#-Datei, *Program.cs*, mit einer `Program`-Klasse mit einer `Main`-Methode. Die `Console.WriteLine`-Anweisung wird „Hello World!“ in der Konsole ausgeben, wenn die App ausgeführt wird.

   ![Hauptfenster mit der geöffneten Datei „Program.cs“](./media/using-on-mac-vs/visual-studio-mac-editor.png)

## <a name="run-the-application"></a>Ausführen der Anwendung

Führen Sie die App mit ⌘ ↵ (BEFEHL+EINGABE) im Debugmodus oder mit ⌥ ⌘ ↵ (WAHL+BEFEHL+EINGABE) im Releasemodus aus.

![Der Ausgabebereich der Anwendung zeigt „Hello World!“ an](./media/using-on-mac-vs/visual-studio-mac-output.png)

## <a name="next-step"></a>Nächster Schritt

Das Thema [Building a complete .NET Core solution on macOS using Visual Studio for Mac (Erstellen einer vollständigen .NET Core-Projektmappe unter macOS mit Visual Studio für Mac)](using-on-mac-vs-full-solution.md) veranschaulicht Ihnen, wie Sie eine vollständige .NET Core-Projektmappe erstellen, die eine wiederverwendbare Bibliothek und Komponententests enthält.
