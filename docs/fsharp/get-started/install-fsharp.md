---
title: Installieren von F#
description: 'Erfahren Sie, wie Sie F # auf verschiedene Arten installieren.'
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224292"
---
# <a name="install-f"></a><span data-ttu-id="c0201-103">Installieren von F\#</span><span class="sxs-lookup"><span data-stu-id="c0201-103">Install F\#</span></span>

<span data-ttu-id="c0201-104">Sie können F # auf verschiedene Weise installieren, abhängig von Ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="c0201-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="c0201-105">Installieren von F # mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c0201-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="c0201-106">Wenn Sie [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) zum ersten Mal herunterladen, wird zuerst Visual Studio-Installer installiert.</span><span class="sxs-lookup"><span data-stu-id="c0201-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="c0201-107">Installieren Sie die entsprechende Edition von Visual Studio über den Installer.</span><span class="sxs-lookup"><span data-stu-id="c0201-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="c0201-108">Wenn Sie Visual Studio bereits installiert haben, wählen Sie neben der Edition, der Sie F # hinzufügen möchten, die Option **ändern** aus.</span><span class="sxs-lookup"><span data-stu-id="c0201-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="c0201-109">Wählen Sie auf der Seite "Workloads" die Arbeitsauslastung **ASP.net und Webentwicklung** aus, die Unterstützung für die Unterstützung von F # und .net Core für ASP.net Core Projekte umfasst</span><span class="sxs-lookup"><span data-stu-id="c0201-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="c0201-110">Wählen Sie in der unteren rechten Ecke **ändern** aus, um alles zu installieren, was Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="c0201-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="c0201-111">Anschließend können Sie Visual Studio mit F # öffnen, indem Sie in Visual Studio-Installer **starten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c0201-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="c0201-112">Installieren von F # mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c0201-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="c0201-113">Stellen Sie sicher, dass [git](https://git-scm.com/download) auf Ihrem Pfad installiert und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c0201-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="c0201-114">Sie können überprüfen, ob Sie ordnungsgemäß installiert ist, indem Sie `git --version` an einer Eingabeaufforderung eingeben und die **Eingabe**Taste drücken.</span><span class="sxs-lookup"><span data-stu-id="c0201-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="c0201-115">Installieren Sie die [.net Core SDK](https://dotnet.microsoft.com/download) und [Visual Studio Code](https://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="c0201-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="c0201-116">Wählen Sie das Symbol Erweiterungen aus, und suchen Sie nach "ionide":</span><span class="sxs-lookup"><span data-stu-id="c0201-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="c0201-117">Das einzige für die F #-Unterstützung in Visual Studio Code erforderliche Plug-in ist " [ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)".</span><span class="sxs-lookup"><span data-stu-id="c0201-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="c0201-118">Sie können jedoch auch [ionide-Fake](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) installieren, um [gefälschte](https://fake.build/) Unterstützung und [ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) zu erhalten, um Unterstützung für das [Paket](https://fsprojects.github.io/Paket/) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c0201-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="c0201-119">Fake und Paket sind zusätzliche F #-communitytools zum Entwickeln von Projekten und zum Verwalten von Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="c0201-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="c0201-120">Installieren von F # mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="c0201-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="c0201-121">F # wird standardmäßig in [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)installiert, unabhängig von der Konfiguration, die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="c0201-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="c0201-122">Nachdem die Installation abgeschlossen ist, klicken Sie auf **Visual Studio starten**.</span><span class="sxs-lookup"><span data-stu-id="c0201-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="c0201-123">Sie können Visual Studio auch über Finder auf macOS öffnen.</span><span class="sxs-lookup"><span data-stu-id="c0201-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="c0201-124">Installieren von F # auf einem Buildserver</span><span class="sxs-lookup"><span data-stu-id="c0201-124">Install F# on a build server</span></span>

<span data-ttu-id="c0201-125">Wenn Sie .net Core oder .NET Framework über das .NET SDK verwenden, müssen Sie einfach das .NET SDK auf dem Buildserver installieren.</span><span class="sxs-lookup"><span data-stu-id="c0201-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="c0201-126">Sie verfügt über alles, was Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="c0201-126">It has everything you need.</span></span>

<span data-ttu-id="c0201-127">Wenn Sie .NET Framework verwenden und das .NET SDK **nicht** verwenden, müssen Sie die [Visual Studio Build Tools-SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) auf Ihrem Windows-Server installieren.</span><span class="sxs-lookup"><span data-stu-id="c0201-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="c0201-128">Wählen Sie im Installationsprogramm **.net-** desktopbuildtools aus, und wählen Sie dann auf der rechten Seite des Installer-Menüs die **F #-Compilerkomponente** aus.</span><span class="sxs-lookup"><span data-stu-id="c0201-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
