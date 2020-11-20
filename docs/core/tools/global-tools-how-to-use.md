---
title: 'Tutorial: In diesem Tutorial erfahren Sie, wie Sie ein globales .NET-Tool installieren und verwenden.'
description: Erfahren Sie, wie Sie ein .NET-Tool als globales Tool installieren und verwenden.
ms.topic: tutorial
ms.date: 02/12/2020
ms.openlocfilehash: 01b773516da92fb16fb0f67fc6617e0c70d17c9d
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633894"
---
# <a name="tutorial-install-and-use-a-net-global-tool-using-the-net-cli"></a><span data-ttu-id="35490-103">Tutorial: Installieren und Verwenden eines globalen .NET-Tools mithilfe der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="35490-103">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>

<span data-ttu-id="35490-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="35490-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="35490-105">In diesem Tutorial erfahren Sie, wie ein globales Tools installiert und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="35490-105">This tutorial teaches you how to install and use a global tool.</span></span> <span data-ttu-id="35490-106">Sie verwenden ein Tool, das Sie im [ersten Tutorial dieser Reihe](global-tools-how-to-create.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="35490-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="35490-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="35490-107">Prerequisites</span></span>

* <span data-ttu-id="35490-108">Absolvieren Sie das [erste Tutorial dieser Reihe](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="35490-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="use-the-tool-as-a-global-tool"></a><span data-ttu-id="35490-109">Verwenden des Tools als globales Tool</span><span class="sxs-lookup"><span data-stu-id="35490-109">Use the tool as a global tool</span></span>

1. <span data-ttu-id="35490-110">Installieren Sie das Tool aus dem Paket, indem Sie den Befehl [dotnet tool install](dotnet-tool-install.md) im Projektordner *microsoft.botsay* ausführen:</span><span class="sxs-lookup"><span data-stu-id="35490-110">Install the tool from the package by running the [dotnet tool install](dotnet-tool-install.md) command in the *microsoft.botsay* project folder:</span></span>

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="35490-111">Der Parameter `--global` weist die .NET-CLI an, die Binärdateien des Tools an einem Standardspeicherort zu installieren, der automatisch zur Umgebungsvariablen PATH hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="35490-111">The `--global` parameter tells the .NET CLI to install the tool binaries in a default location that is automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="35490-112">Der Parameter `--add-source` weist die .NET-CLI an, vorübergehend das Verzeichnis *./nupkg* als zusätzlichen Quellfeed für NuGet-Pakete zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="35490-112">The `--add-source` parameter tells the .NET CLI to temporarily use the *./nupkg* directory as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="35490-113">Sie haben Ihr Paket mit einem eindeutigen Namen versehen, um sicherzustellen, dass es nur im Verzeichnis *./nupkg* und nicht auf der Website Nuget.org gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="35490-113">You gave your package a unique name to make sure that it will only be found in the *./nupkg* directory, not on the Nuget.org site.</span></span>

   <span data-ttu-id="35490-114">Die Ausgabe zeigt den zum Aufrufen des Tools verwendeten Befehl und die installierte Version:</span><span class="sxs-lookup"><span data-stu-id="35490-114">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="35490-115">Rufen Sie das Tool auf:</span><span class="sxs-lookup"><span data-stu-id="35490-115">Invoke the tool:</span></span>

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > <span data-ttu-id="35490-116">Wenn dieser Befehl fehlschlägt, müssen Sie möglicherweise ein neues Terminal öffnen, um PATH zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="35490-116">If this command fails, you may need to open a new terminal to refresh the PATH.</span></span>

1. <span data-ttu-id="35490-117">Entfernen Sie das Tool, indem Sie den Befehl [dotnet tool uninstall](dotnet-tool-uninstall.md) ausführen:</span><span class="sxs-lookup"><span data-stu-id="35490-117">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   ```dotnetcli
   dotnet tool uninstall -g microsoft.botsay
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a><span data-ttu-id="35490-118">Verwenden des an einem benutzerdefinierten Speicherort installierten Tools als globales Tool</span><span class="sxs-lookup"><span data-stu-id="35490-118">Use the tool as a global tool installed in a custom location</span></span>

1. <span data-ttu-id="35490-119">Installieren Sie das Toll aus dem Paket.</span><span class="sxs-lookup"><span data-stu-id="35490-119">Install the tool from the package.</span></span>

   <span data-ttu-id="35490-120">Unter Windows:</span><span class="sxs-lookup"><span data-stu-id="35490-120">On Windows:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="35490-121">Unter Linux oder macOS:</span><span class="sxs-lookup"><span data-stu-id="35490-121">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="35490-122">Der Parameter `--tool-path` weist die .NET-CLI an, die Binärdateien des Tools am angegebenen Speicherort zu installieren.</span><span class="sxs-lookup"><span data-stu-id="35490-122">The `--tool-path` parameter tells the .NET CLI to install the tool binaries in the specified location.</span></span> <span data-ttu-id="35490-123">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="35490-123">If the directory doesn't exist, it is created.</span></span> <span data-ttu-id="35490-124">Dieses Verzeichnis wird nicht automatisch zur Umgebungsvariablen PATH hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="35490-124">This directory is not automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="35490-125">Die Ausgabe zeigt den zum Aufrufen des Tools verwendeten Befehl und die installierte Version:</span><span class="sxs-lookup"><span data-stu-id="35490-125">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="35490-126">Rufen Sie das Tool auf:</span><span class="sxs-lookup"><span data-stu-id="35490-126">Invoke the tool:</span></span>

   <span data-ttu-id="35490-127">Unter Windows:</span><span class="sxs-lookup"><span data-stu-id="35490-127">On Windows:</span></span>

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   <span data-ttu-id="35490-128">Unter Linux oder macOS:</span><span class="sxs-lookup"><span data-stu-id="35490-128">On Linux or macOS:</span></span>

   ```console
   ~/bin/botsay hello from the bot
   ```

1. <span data-ttu-id="35490-129">Entfernen Sie das Tool, indem Sie den Befehl [dotnet tool uninstall](dotnet-tool-uninstall.md) ausführen:</span><span class="sxs-lookup"><span data-stu-id="35490-129">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   <span data-ttu-id="35490-130">Unter Windows:</span><span class="sxs-lookup"><span data-stu-id="35490-130">On Windows:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools microsoft.botsay
   ```

   <span data-ttu-id="35490-131">Unter Linux oder macOS:</span><span class="sxs-lookup"><span data-stu-id="35490-131">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin microsoft.botsay
   ```

## <a name="troubleshoot"></a><span data-ttu-id="35490-132">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="35490-132">Troubleshoot</span></span>

<span data-ttu-id="35490-133">Falls im Verlauf des Tutorials eine Fehlermeldung angezeigt wird, finden Sie unter [Behandlung von Problemen bei der Nutzung von .NET-Tools](troubleshoot-usage-issues.md) weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="35490-133">If you get an error message while following the tutorial, see [Troubleshoot .NET tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="35490-134">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="35490-134">Next steps</span></span>

<span data-ttu-id="35490-135">In diesem Tutorial haben Sie ein Tool als globales Tool installiert und verwendet.</span><span class="sxs-lookup"><span data-stu-id="35490-135">In this tutorial, you installed and used a tool as a global tool.</span></span> <span data-ttu-id="35490-136">Um dasselbe Tool als lokales Tool zu installieren und zu verwenden, fahren Sie mit dem nächsten Tutorial fort.</span><span class="sxs-lookup"><span data-stu-id="35490-136">To install and use the same tool as a local tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="35490-137">Installieren und Verwenden lokaler Tools</span><span class="sxs-lookup"><span data-stu-id="35490-137">Install and use local tools</span></span>](local-tools-how-to-use.md)
