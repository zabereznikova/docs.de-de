---
title: Installieren von F#
description: Erfahren Sie, wie F# Sie basierend auf Ihrer Umgebung installieren.
ms.date: 09/05/2019
ms.openlocfilehash: 18b660ff640904119d63f57405752a14f7673e0c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400721"
---
# <a name="install-f"></a><span data-ttu-id="12cdb-103">Installieren von F\#</span><span class="sxs-lookup"><span data-stu-id="12cdb-103">Install F\#</span></span>

<span data-ttu-id="12cdb-104">Sie können F# auf verschiedene Arten, abhängig von Ihrer Umgebung installieren.</span><span class="sxs-lookup"><span data-stu-id="12cdb-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="12cdb-105">Installieren F# mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="12cdb-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="12cdb-106">Wenn Sie [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) zum ersten Mal herunterladen, wird zunächst der Visual Studio-Installer installiert.</span><span class="sxs-lookup"><span data-stu-id="12cdb-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="12cdb-107">Installieren Sie die entsprechende SKU von Visual Studio über den Installer.</span><span class="sxs-lookup"><span data-stu-id="12cdb-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="12cdb-108">Wenn Sie es bereits installiert haben, klicken Sie auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="12cdb-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="12cdb-109">Im nächsten Schritt sehen Sie eine Liste der Workloads.</span><span class="sxs-lookup"><span data-stu-id="12cdb-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="12cdb-110">Wählen Sie **ASP.NET und Webentwicklung** der F#-Unterstützung und Unterstützung für ASP.NET Core-Projekte für .NET Core installieren.</span><span class="sxs-lookup"><span data-stu-id="12cdb-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="12cdb-111">Klicken Sie anschließend in der unteren rechten Ecke auf **ändern** .</span><span class="sxs-lookup"><span data-stu-id="12cdb-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="12cdb-112">Dadurch wird alles installiert, was Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="12cdb-112">This will install everything you have selected.</span></span> <span data-ttu-id="12cdb-113">Sie können dann Visual Studio 2017 mit F# Sprachunterstützung öffnen, indem Sie auf **starten**klicken.</span><span class="sxs-lookup"><span data-stu-id="12cdb-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="12cdb-114">Installieren von F# in Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="12cdb-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="12cdb-115">F#wird standardmäßig in [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)installiert, unabhängig von der Konfiguration, die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="12cdb-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="12cdb-116">Nachdem die Installation abgeschlossen ist, wählen Sie "Visual Studio starten" aus.</span><span class="sxs-lookup"><span data-stu-id="12cdb-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="12cdb-117">Sie können Sie auch über Finder unter macOS starten.</span><span class="sxs-lookup"><span data-stu-id="12cdb-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="12cdb-118">Installieren von F# mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="12cdb-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="12cdb-119">[Git muss installiert](https://git-scm.com/download) sein und auf dem Pfad verfügbar sein, um Projektvorlagen verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="12cdb-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="12cdb-120">Sie können überprüfen, ob die Installation korrekt ist `git --version` , indem Sie an einer Eingabeaufforderung eingeben und die **Eingabe**Taste drücken.</span><span class="sxs-lookup"><span data-stu-id="12cdb-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="12cdb-121">macOS</span><span class="sxs-lookup"><span data-stu-id="12cdb-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="12cdb-122">[Mono](https://www.mono-project.com) dient zur [F# Interactive](../tutorials/fsharp-interactive/index.md) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="12cdb-122">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="12cdb-123">Die einfachste Möglichkeit, Mono unter macOS zu installieren, ist über Homebrew.</span><span class="sxs-lookup"><span data-stu-id="12cdb-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="12cdb-124">Geben Sie im Terminal einfach Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="12cdb-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="12cdb-125">Installieren Sie auch die [.net Core SDK](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="12cdb-125">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="12cdb-126">Linux</span><span class="sxs-lookup"><span data-stu-id="12cdb-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="12cdb-127">[Mono](https://www.mono-project.com) dient zur [F# Interactive](../tutorials/fsharp-interactive/index.md) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="12cdb-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="12cdb-128">Wenn Sie mit Debian oder Ubuntu arbeiten, können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="12cdb-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="12cdb-129">Installieren Sie auch die [.net Core SDK](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="12cdb-129">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="12cdb-130">Windows</span><span class="sxs-lookup"><span data-stu-id="12cdb-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="12cdb-131">Installieren Sie [Visual Studio mit F#-Unterstützung](#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="12cdb-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="12cdb-132">Dadurch werden alle erforderlichen Komponenten zum Schreiben, kompilieren und Ausführen von F#-Code installiert.</span><span class="sxs-lookup"><span data-stu-id="12cdb-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="12cdb-133">Installieren Sie auch die [.net Core SDK](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="12cdb-133">Also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="12cdb-134">Sie müssen dann [Visual Studio Code](https://code.visualstudio.com) installieren.</span><span class="sxs-lookup"><span data-stu-id="12cdb-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="12cdb-135">Klicken Sie anschließend auf das Symbol Erweiterungen, und suchen Sie nach "ionide":</span><span class="sxs-lookup"><span data-stu-id="12cdb-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="12cdb-136">Erforderlich für F#-Unterstützung in Visual Studio Code ist die einzige-Plug-in [Ionide-Fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="12cdb-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="12cdb-137">Sie können jedoch auch [ionide-Fake](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) installieren, um [gefälschte](https://fsharp.github.io/FAKE/) Unterstützung und [ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) zu erhalten, um Unterstützung für das [Paket](https://fsprojects.github.io/Paket/) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="12cdb-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="12cdb-138">Fake und Paket sind zusätzliche F# communitytools zum Entwickeln von Projekten und zum Verwalten von Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="12cdb-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="12cdb-139">Auf F# einem Buildserver installieren</span><span class="sxs-lookup"><span data-stu-id="12cdb-139">Install F# on a Build Server</span></span>

<span data-ttu-id="12cdb-140">Wenn Sie .net Core oder .NET Framework über das .NET SDK verwenden, müssen Sie einfach das .NET SDK auf dem Buildserver installieren.</span><span class="sxs-lookup"><span data-stu-id="12cdb-140">If you are using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="12cdb-141">Sie verfügt über alles, was Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="12cdb-141">It has everything you need.</span></span>

<span data-ttu-id="12cdb-142">Wenn Sie .NET Framework verwenden und das .NET SDK **nicht** verwenden, müssen Sie die [Visual Studio Build Tools-SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) auf Ihrem Windows-Server installieren.</span><span class="sxs-lookup"><span data-stu-id="12cdb-142">If you are using .NET Framework and you are **not** using the .NET SDK, then you will need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="12cdb-143">Wählen Sie im Installationsprogramm **.net-** desktopbuildtools aus, und wählen Sie dann die  **F# Compilerkomponente** auf der rechten Seite des Installations Menüs aus.</span><span class="sxs-lookup"><span data-stu-id="12cdb-143">In the installer, select **.NET desktop build tools** and then select the **F# compiler** component on the right side of the installer menu.</span></span>
