---
title: Installieren von F#
description: Erfahren Sie, wie Sie die Datei auf verschiedene Arten installieren.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401094"
---
# <a name="install-f"></a><span data-ttu-id="5b56e-103">Installieren F\#</span><span class="sxs-lookup"><span data-stu-id="5b56e-103">Install F\#</span></span>

<span data-ttu-id="5b56e-104">Je nach Umgebung können Sie die Datei auf verschiedene Arten installieren.</span><span class="sxs-lookup"><span data-stu-id="5b56e-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="5b56e-105">Installieren von F-Code mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b56e-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="5b56e-106">Wenn Sie Visual [Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) zum ersten Mal herunterladen, wird Visual Studio Installer zuerst installiert.</span><span class="sxs-lookup"><span data-stu-id="5b56e-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="5b56e-107">Installieren Sie die entsprechende Edition von Visual Studio aus dem Installationsprogramm.</span><span class="sxs-lookup"><span data-stu-id="5b56e-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="5b56e-108">Wenn Sie Visual Studio bereits installiert haben, wählen Sie neben der Edition, der Sie F- hinzufügen möchten, die Option **Ändern** aus.</span><span class="sxs-lookup"><span data-stu-id="5b56e-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="5b56e-109">Wählen Sie auf der Seite Workloads die **ASP.NET- und Webentwicklungs-Workload** aus, die die Unterstützung von F- und .NET Core für ASP.NET Core-Projekte umfasst.</span><span class="sxs-lookup"><span data-stu-id="5b56e-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="5b56e-110">Wählen Sie In der unteren rechten Ecke **ändern** aus, um alles zu installieren, was Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="5b56e-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="5b56e-111">Anschließend können Sie Visual Studio mit F- öffnen, indem Sie **Launch** in Visual Studio Installer auswählen.</span><span class="sxs-lookup"><span data-stu-id="5b56e-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="5b56e-112">Installieren von F-Code mit Visual Studio-Code</span><span class="sxs-lookup"><span data-stu-id="5b56e-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="5b56e-113">Stellen Sie sicher, dass [Git](https://git-scm.com/download) auf Ihrem PATH installiert und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="5b56e-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="5b56e-114">Sie können überprüfen, ob es ordnungsgemäß `git --version` installiert ist, indem Sie eine Eingabeaufforderung eingeben und **die Eingabeeingabe**drücken.</span><span class="sxs-lookup"><span data-stu-id="5b56e-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="5b56e-115">Installieren Sie [das .NET Core SDK](https://dotnet.microsoft.com/download) und [Visual Studio Code](https://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="5b56e-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="5b56e-116">Wählen Sie das Symbol Erweiterungen und suchen Sie nach "Ionide":</span><span class="sxs-lookup"><span data-stu-id="5b56e-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="5b56e-117">Das einzige Plugin, das für die F-Unterstützung in Visual Studio Code erforderlich ist, ist [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="5b56e-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="5b56e-118">Sie können jedoch auch [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) installieren, um [FAKE-Unterstützung](https://fake.build/) und [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) zu erhalten, um [Paket-Unterstützung](https://fsprojects.github.io/Paket/) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5b56e-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="5b56e-119">FAKE und Paket sind zusätzliche Tools für die Community, um Projekte zu erstellen bzw. Abhängigkeiten zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="5b56e-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="5b56e-120">Installieren von F-Code mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="5b56e-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="5b56e-121">In [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)wird standardmäßig f- installiert, unabhängig davon, welche Konfiguration Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="5b56e-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="5b56e-122">Nachdem die Installation abgeschlossen ist, wählen Sie **Visual Studio starten**.</span><span class="sxs-lookup"><span data-stu-id="5b56e-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="5b56e-123">Sie können Visual Studio auch über Finder unter macOS öffnen.</span><span class="sxs-lookup"><span data-stu-id="5b56e-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="5b56e-124">Installieren von F- auf einem Buildserver</span><span class="sxs-lookup"><span data-stu-id="5b56e-124">Install F# on a build server</span></span>

<span data-ttu-id="5b56e-125">Wenn Sie .NET Core oder .NET Framework über das .NET SDK verwenden, müssen Sie einfach das .NET SDK auf Ihrem Buildserver installieren.</span><span class="sxs-lookup"><span data-stu-id="5b56e-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="5b56e-126">Es hat alles, was Sie brauchen.</span><span class="sxs-lookup"><span data-stu-id="5b56e-126">It has everything you need.</span></span>

<span data-ttu-id="5b56e-127">Wenn Sie .NET Framework verwenden und das .NET SDK **nicht** verwenden, müssen Sie die [Visual Studio Build Tools-SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) auf Ihrem Windows Server installieren.</span><span class="sxs-lookup"><span data-stu-id="5b56e-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="5b56e-128">Wählen Sie im Installationsprogramm **.NET Desktopbuildtools**aus, und wählen Sie dann auf der rechten Seite des Installationsmenüs die **Compilerkomponente "F"** aus.</span><span class="sxs-lookup"><span data-stu-id="5b56e-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
