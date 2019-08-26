---
title: Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac
description: Dieses Thema führt Sie durch die Erstellung einer einfachen Konsolenanwendung mit Visual Studio für Mac und .NET Core.
author: mairaw
ms.date: 07/11/2019
ms.custom: seodec18
ms.openlocfilehash: 7dd8d5e8828c5337a52e9d1ea207aa5ef568556e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660504"
---
# <a name="get-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="ffc5c-103">Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="ffc5c-103">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="ffc5c-104">Visual Studio für Mac bietet eine umfassende integrierte Entwicklungsumgebung (IDE) für die Entwicklung von .NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="ffc5c-105">Dieses Thema führt Sie durch die Erstellung einer einfachen Konsolenanwendung mit Visual Studio für Mac und .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-105">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="ffc5c-106">Ihr Feedback ist uns sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-106">Your feedback is highly valued.</span></span> <span data-ttu-id="ffc5c-107">Es gibt zwei Möglichkeiten, wie Sie Feedback für das Entwicklungsteam von Visual Studio für Mac bereitstellen können:</span><span class="sxs-lookup"><span data-stu-id="ffc5c-107">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="ffc5c-108">Klicken Sie in Visual Studio für Mac auf **Hilfe** > **Ein Problem melden** im Menü oder auf **Ein Problem melden** auf der Willkommensseite. Dadurch wird ein Fenster für das Ablegen eines Fehlerberichts geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="ffc5c-109">Sie können Ihr Feedback im Portal der [Entwicklercommunity](https://developercommunity.visualstudio.com/spaces/8/index.html) verfolgen.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="ffc5c-110">Um einen Vorschlag zu machen, wählen Sie **Hilfe** > **Vorschlag senden** im Menü oder **Vorschlag senden** auf der Willkommensseite aus. Dadurch gelangen Sie zur Webseite [Visual Studio für Mac-Entwicklercommunity](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="ffc5c-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ffc5c-111">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="ffc5c-111">Prerequisites</span></span>

<span data-ttu-id="ffc5c-112">Weitere Informationen finden Sie unter dem Thema [Voraussetzungen für .NET Core unter Mac](../macos-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="ffc5c-112">See the [Prerequisites for .NET Core on Mac](../macos-prerequisites.md) topic.</span></span>

<span data-ttu-id="ffc5c-113">Vergewissern Sie sich unter [.NET Core-Unterstützung](https://docs.microsoft.com/visualstudio/mac/net-core-support?view=vsmac-2019), dass Sie eine unterstützte Version von .NET Core verwenden.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-113">Check the [.NET Core Support](https://docs.microsoft.com/visualstudio/mac/net-core-support?view=vsmac-2019) guide to ensure you're using a supported version of .NET Core.</span></span>

## <a name="get-started"></a><span data-ttu-id="ffc5c-114">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="ffc5c-114">Get started</span></span>

<span data-ttu-id="ffc5c-115">Wenn Sie bereits die erforderlichen Komponenten und Visual Studio für Mac installiert haben, überspringen Sie diesen Abschnitt, und fahren Sie mit [Erstellen eines Projekts](#creating-a-project) fort.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-115">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="ffc5c-116">Um die erforderlichen Komponenten und Visual Studio für Mac zu installieren, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="ffc5c-116">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="ffc5c-117">Laden Sie den [Visual Studio für Mac-Installer](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) herunter.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-117">Download the [Visual Studio for Mac installer](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="ffc5c-118">Führen Sie den Installer aus.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-118">Run the installer.</span></span> <span data-ttu-id="ffc5c-119">Lesen und akzeptieren Sie die Lizenzbedingungen.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-119">Read and accept the license agreement.</span></span> <span data-ttu-id="ffc5c-120">Wählen Sie im Rahmen der Installation die Option zum Installieren von .NET Core aus.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-120">During the install, select the option to install .NET Core.</span></span> <span data-ttu-id="ffc5c-121">Sie haben die Möglichkeit, Xamarin zu installieren – eine plattformübergreifende Entwicklungstechnologie für mobile Apps.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-121">You're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="ffc5c-122">Das Installieren von Xamarin und den zugehörigen Komponenten ist für die Entwicklung mit .NET Core optional.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-122">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="ffc5c-123">Eine exemplarische Vorgehensweise für den Visual Studio für Mac-Installationsvorgang finden Sie in der [Dokumentation für Visual Studio für Mac](/visualstudio/mac/).</span><span class="sxs-lookup"><span data-stu-id="ffc5c-123">For a walk-through of the Visual Studio for Mac install process, see [Visual Studio for Mac documentation](/visualstudio/mac/).</span></span> <span data-ttu-id="ffc5c-124">Wenn die Installation abgeschlossen ist, starten Sie Visual Studio für Mac-IDE.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-124">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="ffc5c-125">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="ffc5c-125">Creating a project</span></span>

1. <span data-ttu-id="ffc5c-126">Wählen Sie im Startfenster die Option **Neu** aus.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-126">Select **New** on the Start Window.</span></span>

   ![Schaltfläche „Neu“ auf der Startseite von Visual Studio für Mac](./media/using-on-mac-vs/visual-studio-mac-new-project.png)

1. <span data-ttu-id="ffc5c-128">Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **.NET Core** **App** aus.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-128">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="ffc5c-129">Wählen Sie die **Konsolenanwendung**-Vorlage und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-129">Select the **Console Application** template followed by **Next**.</span></span>

   ![Liste neuer Projektvorlagen](./media/using-on-mac-vs/visual-studio-mac-new-dialog.png)

1. <span data-ttu-id="ffc5c-131">Sollten mehrere Versionen von .NET Core installiert sein, wählen Sie das Zielframework für Ihr Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-131">If you have more than one version of .NET Core installed, select the target framework for your project.</span></span>

1. <span data-ttu-id="ffc5c-132">Geben Sie „HelloWorld“ als **Projektname** ein.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-132">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="ffc5c-133">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-133">Select **Create**.</span></span>

   ![Dialogfeld „Konfigurieren Sie Ihre neue Konsolenanwendung“](./media/using-on-mac-vs/visual-studio-mac-new-options.png)

1. <span data-ttu-id="ffc5c-135">Warten Sie, während die Abhängigkeiten des Projekts wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-135">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="ffc5c-136">Das Projekt enthält eine einzelne C#-Datei, *Program.cs*, mit einer `Program`-Klasse mit einer `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-136">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="ffc5c-137">Die `Console.WriteLine`-Anweisung wird „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="ffc5c-137">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="ffc5c-138">in der Konsole ausgeben, wenn die App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-138">to the console when the app is run.</span></span>

   ![Hauptfenster mit der geöffneten Datei „Program.cs“](./media/using-on-mac-vs/visual-studio-mac-editor.png)

## <a name="run-the-application"></a><span data-ttu-id="ffc5c-140">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="ffc5c-140">Run the application</span></span>

<span data-ttu-id="ffc5c-141">Führen Sie die App mit ⌘ ↵ (BEFEHL+EINGABE) im Debugmodus oder mit ⌥ ⌘ ↵ (WAHL+BEFEHL+EINGABE) im Releasemodus aus.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-141">Run the app in Debug mode using ⌘ ↵ (command + enter) or in Release mode using ⌥ ⌘ ↵ (option + command + enter).</span></span>

![Der Ausgabebereich der Anwendung zeigt „Hello World!“ an](./media/using-on-mac-vs/visual-studio-mac-output.png)

## <a name="next-step"></a><span data-ttu-id="ffc5c-143">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ffc5c-143">Next step</span></span>

<span data-ttu-id="ffc5c-144">Das Thema [Building a complete .NET Core solution on macOS using Visual Studio for Mac (Erstellen einer vollständigen .NET Core-Projektmappe unter macOS mit Visual Studio für Mac)](using-on-mac-vs-full-solution.md) veranschaulicht Ihnen, wie Sie eine vollständige .NET Core-Projektmappe erstellen, die eine wiederverwendbare Bibliothek und Komponententests enthält.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-144">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
