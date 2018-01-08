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
ms.workload: dotnetcore
ms.openlocfilehash: dad4a66fc943f4232806f7512705fc96decd1904
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="6ad80-104">Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="6ad80-104">Getting started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="6ad80-105">Visual Studio für Mac bietet eine umfassende integrierte Entwicklungsumgebung (IDE) für die Entwicklung von .NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="6ad80-105">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="6ad80-106">Dieses Thema führt Sie durch die Erstellung einer einfachen Konsolenanwendung mit Visual Studio für Mac und .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6ad80-106">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="6ad80-107">Ihr Feedback ist uns sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="6ad80-107">Your feedback is highly valued.</span></span> <span data-ttu-id="6ad80-108">Es gibt zwei Möglichkeiten, wie Sie Feedback für das Entwicklungsteam von Visual Studio für Mac bereitstellen können:</span><span class="sxs-lookup"><span data-stu-id="6ad80-108">There are a two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="6ad80-109">Klicken Sie in Visual Studio für Mac auf **Hilfe** > **Ein Problem melden** im Menü oder auf **Ein Problem melden** auf der Willkommensseite. Dadurch wird ein Fenster für das Ablegen eines Fehlerberichts geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6ad80-109">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="6ad80-110">Sie können Ihr Feedback im Portal der [Entwicklercommunity](https://developercommunity.visualstudio.com/spaces/8/index.html) verfolgen.</span><span class="sxs-lookup"><span data-stu-id="6ad80-110">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="6ad80-111">Um einen Vorschlag zu machen, klicken Sie auf **Hilfe** > **Vorschlag senden** im Menü oder auf **Vorschlag senden** auf der Willkommensseite. Dadurch gelangen Sie zur [Visual Studio for Mac UserVoice webpage (UserVoice-Webseite von Visual Studio für Mac)](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="6ad80-111">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac UserVoice webpage](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6ad80-112">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="6ad80-112">Prerequisites</span></span>

<span data-ttu-id="6ad80-113">Weitere Informationen finden Sie unter dem Thema [Voraussetzungen für .NET Core unter Mac](../../core/macos-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="6ad80-113">See the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md) topic.</span></span>

## <a name="getting-started"></a><span data-ttu-id="6ad80-114">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="6ad80-114">Getting started</span></span>

<span data-ttu-id="6ad80-115">Wenn Sie bereits die erforderlichen Komponenten und Visual Studio für Mac installiert haben, überspringen Sie diesen Abschnitt, und fahren Sie mit [Erstellen eines Projekts](#creating-a-project) fort.</span><span class="sxs-lookup"><span data-stu-id="6ad80-115">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="6ad80-116">Um die erforderlichen Komponenten und Visual Studio für Mac zu installieren, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="6ad80-116">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="6ad80-117">Laden Sie den [Visual Studio für Mac-Installer](https://www.visualstudio.com/vs/visual-studio-mac/) herunter.</span><span class="sxs-lookup"><span data-stu-id="6ad80-117">Download the [Visual Studio for Mac installer](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> <span data-ttu-id="6ad80-118">Führen Sie den Installer aus.</span><span class="sxs-lookup"><span data-stu-id="6ad80-118">Run the installer.</span></span> <span data-ttu-id="6ad80-119">Lesen und akzeptieren Sie die Lizenzbedingungen.</span><span class="sxs-lookup"><span data-stu-id="6ad80-119">Read and accept the license agreement.</span></span> <span data-ttu-id="6ad80-120">Während der Installation haben Sie die Möglichkeit zum Installieren von Xamarin, einer plattformübergreifenden mobilen App-Entwicklungstechnologie.</span><span class="sxs-lookup"><span data-stu-id="6ad80-120">During the install, you're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="6ad80-121">Das Installieren von Xamarin und den zugehörigen Komponenten ist für die Entwicklung mit .NET Core optional.</span><span class="sxs-lookup"><span data-stu-id="6ad80-121">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="6ad80-122">Eine exemplarische Vorgehensweise für den Visual Studio für Mac-Installationsvorgang finden Sie unter [Introducing Visual Studio for Mac (Einführung in Visual Studio für Mac)](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="6ad80-122">For a walk-through of the Visual Studio for Mac install process, see [Introducing Visual Studio for Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span></span> <span data-ttu-id="6ad80-123">Wenn die Installation abgeschlossen ist, starten Sie Visual Studio für Mac-IDE.</span><span class="sxs-lookup"><span data-stu-id="6ad80-123">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="6ad80-124">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="6ad80-124">Creating a project</span></span>

1. <span data-ttu-id="6ad80-125">Wählen Sie **Neues Projekt** auf der Willkommensseite aus.</span><span class="sxs-lookup"><span data-stu-id="6ad80-125">Select **New Project** on the Welcome screen.</span></span>

   ![Schaltfläche für „Neues Projekt“ auf der Willkommensseite von Visual Studio für Mac](./media/using-on-mac-vs/vsmac1.png)

1. <span data-ttu-id="6ad80-127">Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **.NET Core** **App** aus.</span><span class="sxs-lookup"><span data-stu-id="6ad80-127">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="6ad80-128">Wählen Sie die **Konsolenanwendung**-Vorlage und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="6ad80-128">Select the **Console Application** template followed by **Next**.</span></span>

   ![Liste neuer Projektvorlagen](./media/using-on-mac-vs/vsmac2.png)

1. <span data-ttu-id="6ad80-130">Geben Sie „HelloWorld“ als **Projektname** ein.</span><span class="sxs-lookup"><span data-stu-id="6ad80-130">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="6ad80-131">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="6ad80-131">Select **Create**.</span></span>

   ![Dialogfeld „Konfigurieren Sie Ihre neue Konsolenanwendung“](./media/using-on-mac-vs/vsmac3.png)

1. <span data-ttu-id="6ad80-133">Warten Sie, während die Abhängigkeiten des Projekts wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6ad80-133">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="6ad80-134">Das Projekt enthält eine einzelne C#-Datei, *Program.cs*, mit einer `Program`-Klasse mit einer `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="6ad80-134">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="6ad80-135">Die `Console.WriteLine`-Anweisung wird „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="6ad80-135">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="6ad80-136">in der Konsole ausgeben, wenn die App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6ad80-136">to the console when the app is run.</span></span>

   ![Hauptfenster mit der geöffneten Datei „Program.cs“](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a><span data-ttu-id="6ad80-138">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="6ad80-138">Run the application</span></span>

<span data-ttu-id="6ad80-139">Führen Sie diese Anwendung durch Drücken von <kbd>F5</kbd> im Debugmodus oder durch Drücken von <kbd>STRG</kbd>+<kbd>F5</kbd> im Releasemodus aus.</span><span class="sxs-lookup"><span data-stu-id="6ad80-139">Run the app in Debug mode using <kbd>F5</kbd> or in Release mode using <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>

![Der Ausgabebereich der Anwendung zeigt „Hello World!“ an](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a><span data-ttu-id="6ad80-141">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="6ad80-141">Next step</span></span>

<span data-ttu-id="6ad80-142">Das Thema [Building a complete .NET Core solution on macOS using Visual Studio for Mac (Erstellen einer vollständigen .NET Core-Projektmappe unter macOS mit Visual Studio für Mac)](using-on-mac-vs-full-solution.md) veranschaulicht Ihnen, wie Sie eine vollständige .NET Core-Projektmappe erstellen, die eine wiederverwendbare Bibliothek und Komponententests enthält.</span><span class="sxs-lookup"><span data-stu-id="6ad80-142">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
