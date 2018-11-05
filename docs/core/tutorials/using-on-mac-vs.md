---
title: Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac
description: Dieses Thema führt Sie durch die Erstellung einer einfachen Konsolenanwendung mit Visual Studio für Mac und .NET Core.
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.openlocfilehash: f751e7532e9627de3d3733476f7214654089e468
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50170730"
---
# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="fecb0-103">Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="fecb0-103">Getting started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="fecb0-104">Visual Studio für Mac bietet eine umfassende integrierte Entwicklungsumgebung (IDE) für die Entwicklung von .NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="fecb0-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="fecb0-105">Dieses Thema führt Sie durch die Erstellung einer einfachen Konsolenanwendung mit Visual Studio für Mac und .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fecb0-105">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="fecb0-106">Ihr Feedback ist uns sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="fecb0-106">Your feedback is highly valued.</span></span> <span data-ttu-id="fecb0-107">Es gibt zwei Möglichkeiten, wie Sie Feedback für das Entwicklungsteam von Visual Studio für Mac bereitstellen können:</span><span class="sxs-lookup"><span data-stu-id="fecb0-107">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="fecb0-108">Klicken Sie in Visual Studio für Mac auf **Hilfe** > **Ein Problem melden** im Menü oder auf **Ein Problem melden** auf der Willkommensseite. Dadurch wird ein Fenster für das Ablegen eines Fehlerberichts geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fecb0-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="fecb0-109">Sie können Ihr Feedback im Portal der [Entwicklercommunity](https://developercommunity.visualstudio.com/spaces/8/index.html) verfolgen.</span><span class="sxs-lookup"><span data-stu-id="fecb0-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="fecb0-110">Um einen Vorschlag zu machen, wählen Sie **Hilfe** > **Vorschlag senden** im Menü oder **Vorschlag senden** auf der Willkommensseite aus. Dadurch gelangen Sie zur Webseite [Visual Studio für Mac-Entwicklercommunity](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="fecb0-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fecb0-111">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="fecb0-111">Prerequisites</span></span>

<span data-ttu-id="fecb0-112">Weitere Informationen finden Sie unter dem Thema [Voraussetzungen für .NET Core unter Mac](../../core/macos-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="fecb0-112">See the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md) topic.</span></span>

## <a name="getting-started"></a><span data-ttu-id="fecb0-113">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="fecb0-113">Getting started</span></span>

<span data-ttu-id="fecb0-114">Wenn Sie bereits die erforderlichen Komponenten und Visual Studio für Mac installiert haben, überspringen Sie diesen Abschnitt, und fahren Sie mit [Erstellen eines Projekts](#creating-a-project) fort.</span><span class="sxs-lookup"><span data-stu-id="fecb0-114">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="fecb0-115">Um die erforderlichen Komponenten und Visual Studio für Mac zu installieren, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="fecb0-115">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="fecb0-116">Laden Sie den [Visual Studio für Mac-Installer](https://visualstudio.microsoft.com/vs/visual-studio-mac/) herunter.</span><span class="sxs-lookup"><span data-stu-id="fecb0-116">Download the [Visual Studio for Mac installer](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span></span> <span data-ttu-id="fecb0-117">Führen Sie den Installer aus.</span><span class="sxs-lookup"><span data-stu-id="fecb0-117">Run the installer.</span></span> <span data-ttu-id="fecb0-118">Lesen und akzeptieren Sie die Lizenzbedingungen.</span><span class="sxs-lookup"><span data-stu-id="fecb0-118">Read and accept the license agreement.</span></span> <span data-ttu-id="fecb0-119">Während der Installation haben Sie die Möglichkeit zum Installieren von Xamarin, einer plattformübergreifenden mobilen App-Entwicklungstechnologie.</span><span class="sxs-lookup"><span data-stu-id="fecb0-119">During the install, you're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="fecb0-120">Das Installieren von Xamarin und den zugehörigen Komponenten ist für die Entwicklung mit .NET Core optional.</span><span class="sxs-lookup"><span data-stu-id="fecb0-120">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="fecb0-121">Eine exemplarische Vorgehensweise für den Visual Studio für Mac-Installationsvorgang finden Sie unter [Introducing Visual Studio for Mac (Einführung in Visual Studio für Mac)](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="fecb0-121">For a walk-through of the Visual Studio for Mac install process, see [Introducing Visual Studio for Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span></span> <span data-ttu-id="fecb0-122">Wenn die Installation abgeschlossen ist, starten Sie Visual Studio für Mac-IDE.</span><span class="sxs-lookup"><span data-stu-id="fecb0-122">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="fecb0-123">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="fecb0-123">Creating a project</span></span>

1. <span data-ttu-id="fecb0-124">Wählen Sie **Neues Projekt** auf der Willkommensseite aus.</span><span class="sxs-lookup"><span data-stu-id="fecb0-124">Select **New Project** on the Welcome screen.</span></span>

   ![Schaltfläche für „Neues Projekt“ auf der Willkommensseite von Visual Studio für Mac](./media/using-on-mac-vs/vsmac1.png)

1. <span data-ttu-id="fecb0-126">Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **.NET Core** **App** aus.</span><span class="sxs-lookup"><span data-stu-id="fecb0-126">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="fecb0-127">Wählen Sie die **Konsolenanwendung**-Vorlage und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="fecb0-127">Select the **Console Application** template followed by **Next**.</span></span>

   ![Liste neuer Projektvorlagen](./media/using-on-mac-vs/vsmac2.png)

1. <span data-ttu-id="fecb0-129">Geben Sie „HelloWorld“ als **Projektname** ein.</span><span class="sxs-lookup"><span data-stu-id="fecb0-129">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="fecb0-130">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="fecb0-130">Select **Create**.</span></span>

   ![Dialogfeld „Konfigurieren Sie Ihre neue Konsolenanwendung“](./media/using-on-mac-vs/vsmac3.png)

1. <span data-ttu-id="fecb0-132">Warten Sie, während die Abhängigkeiten des Projekts wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fecb0-132">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="fecb0-133">Das Projekt enthält eine einzelne C#-Datei, *Program.cs*, mit einer `Program`-Klasse mit einer `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="fecb0-133">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="fecb0-134">Die `Console.WriteLine`-Anweisung wird „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="fecb0-134">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="fecb0-135">in der Konsole ausgeben, wenn die App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fecb0-135">to the console when the app is run.</span></span>

   ![Hauptfenster mit der geöffneten Datei „Program.cs“](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a><span data-ttu-id="fecb0-137">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="fecb0-137">Run the application</span></span>

<span data-ttu-id="fecb0-138">Führen Sie diese Anwendung durch Drücken von <kbd>F5</kbd> im Debugmodus oder durch Drücken von <kbd>STRG</kbd>+<kbd>F5</kbd> im Releasemodus aus.</span><span class="sxs-lookup"><span data-stu-id="fecb0-138">Run the app in Debug mode using <kbd>F5</kbd> or in Release mode using <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>

![Der Ausgabebereich der Anwendung zeigt „Hello World!“ an](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a><span data-ttu-id="fecb0-140">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="fecb0-140">Next step</span></span>

<span data-ttu-id="fecb0-141">Das Thema [Building a complete .NET Core solution on macOS using Visual Studio for Mac (Erstellen einer vollständigen .NET Core-Projektmappe unter macOS mit Visual Studio für Mac)](using-on-mac-vs-full-solution.md) veranschaulicht Ihnen, wie Sie eine vollständige .NET Core-Projektmappe erstellen, die eine wiederverwendbare Bibliothek und Komponententests enthält.</span><span class="sxs-lookup"><span data-stu-id="fecb0-141">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
