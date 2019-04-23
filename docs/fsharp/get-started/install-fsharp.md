---
title: Installieren von F#
description: Informationen zum Installieren F# basierend auf Ihrer Umgebung.
ms.date: 08/28/2018
ms.openlocfilehash: 792c61c0522cd4d0c68a64572f2892ce33f71ea6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331974"
---
# <a name="install-f"></a><span data-ttu-id="629a6-103">Installieren von F\#</span><span class="sxs-lookup"><span data-stu-id="629a6-103">Install F\#</span></span>

<span data-ttu-id="629a6-104">Sie können F# auf verschiedene Arten, abhängig von Ihrer Umgebung installieren.</span><span class="sxs-lookup"><span data-stu-id="629a6-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="629a6-105">Installieren Sie F# mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="629a6-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="629a6-106">Wenn Sie herunterladen werden [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) zum ersten Mal wird es zunächst Visual Studio-Installer installieren.</span><span class="sxs-lookup"><span data-stu-id="629a6-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="629a6-107">Installieren Sie die entsprechende SKU von Visual Studio über den Installer.</span><span class="sxs-lookup"><span data-stu-id="629a6-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="629a6-108">Wenn Sie bereits installiert haben, klicken Sie auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="629a6-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="629a6-109">Als Nächstes sehen Sie, eine Liste von Workloads.</span><span class="sxs-lookup"><span data-stu-id="629a6-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="629a6-110">Wählen Sie **ASP.NET und Webentwicklung** der F#-Unterstützung und Unterstützung für ASP.NET Core-Projekte für .NET Core installieren.</span><span class="sxs-lookup"><span data-stu-id="629a6-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="629a6-111">Klicken Sie anschließend **ändern** in der unteren rechten Ecke.</span><span class="sxs-lookup"><span data-stu-id="629a6-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="629a6-112">Dadurch wird alles, was installiert, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="629a6-112">This will install everything you have selected.</span></span> <span data-ttu-id="629a6-113">Anschließend können Sie Visual Studio 2017 mit öffnen F# sprachunterstützung durch Klicken auf **starten**.</span><span class="sxs-lookup"><span data-stu-id="629a6-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="629a6-114">Installieren von F# in Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="629a6-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="629a6-115">F#wird standardmäßig unter installiert [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), unabhängig davon, welche Konfiguration Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="629a6-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="629a6-116">Nachdem die Installation abgeschlossen ist, wählen Sie "Starten Sie Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="629a6-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="629a6-117">Sie können es auch über den Finder unter MacOS starten.</span><span class="sxs-lookup"><span data-stu-id="629a6-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="629a6-118">Installieren von F# mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="629a6-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="629a6-119">Sie benötigen [Git-Installation](https://git-scm.com/download) und verfügbar ist, auf dem Weg zur Stellen verwenden der Projektvorlagen das Projekt.</span><span class="sxs-lookup"><span data-stu-id="629a6-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="629a6-120">Sie können überprüfen, dass es ordnungsgemäß, durch Eingabe installiert ist `git --version` an einer Eingabeaufforderung, und drücken **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="629a6-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="629a6-121">macOS</span><span class="sxs-lookup"><span data-stu-id="629a6-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="629a6-122">[Mono](https://www.mono-project.com) dient zur [F# Interactive](../tutorials/fsharp-interactive/index.md) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="629a6-122">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="629a6-123">Die einfachste Möglichkeit zum Installieren von Mono unter MacOS ist über Homebrew.</span><span class="sxs-lookup"><span data-stu-id="629a6-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="629a6-124">Geben Sie einfach Folgendes in Ihrem Terminal ein:</span><span class="sxs-lookup"><span data-stu-id="629a6-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="629a6-125">Installieren Sie auch die [.NET Core SDK](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="629a6-125">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="629a6-126">Linux</span><span class="sxs-lookup"><span data-stu-id="629a6-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="629a6-127">[Mono](https://www.mono-project.com) dient zur [F# Interactive](../tutorials/fsharp-interactive/index.md) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="629a6-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="629a6-128">Wenn Sie sich unter Debian oder Ubuntu sind, können Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="629a6-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="629a6-129">Installieren Sie auch die [.NET Core SDK](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="629a6-129">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="629a6-130">Windows</span><span class="sxs-lookup"><span data-stu-id="629a6-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="629a6-131">Installieren Sie [Visual Studio mit F#-Unterstützung](#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="629a6-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="629a6-132">Dadurch werden alle erforderlichen Komponenten zum Schreiben, kompilieren und Ausführen von F#-Code installiert.</span><span class="sxs-lookup"><span data-stu-id="629a6-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="629a6-133">Installieren Sie auch die [.NET Core SDK](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="629a6-133">Also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="629a6-134">Sie müssen dann [Visual Studio Code](https://code.visualstudio.com) installiert.</span><span class="sxs-lookup"><span data-stu-id="629a6-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="629a6-135">Klicken Sie dann auf das Symbol "Erweiterungen" und suchen Sie nach "Ionide":</span><span class="sxs-lookup"><span data-stu-id="629a6-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="629a6-136">Erforderlich für F#-Unterstützung in Visual Studio Code ist die einzige-Plug-in [Ionide-Fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="629a6-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="629a6-137">Allerdings können Sie auch installieren [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) abzurufenden [FAKE](https://fsharp.github.io/FAKE/) unterstützen und [Ionide-Paket-Abhängigkeits](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) abzurufenden [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="629a6-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="629a6-138">Falsche und Paket-Abhängigkeits sind zusätzliche F# communitytools für die Projekte erstellen und Verwalten von Abhängigkeiten, bzw.</span><span class="sxs-lookup"><span data-stu-id="629a6-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>
