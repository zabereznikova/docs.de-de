---
title: Installieren des Modell-Generators
description: Erfahren Sie, wie Sie das ML.NET-Modell-Generator-Tool installieren.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: 54ab595c56f816517180aab48022c7df207fe84d
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410568"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="749ec-103">Installieren des ML.NET-Modell-Generators</span><span class="sxs-lookup"><span data-stu-id="749ec-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="749ec-104">Erfahren Sie, wie Sie den ML.NET-Modell-Generator installieren, um Ihre .NET-Anwendungen mit maschinellem Lernen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="749ec-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="749ec-105">Der Modell-Generator befindet sich derzeit in der Vorschauphase.</span><span class="sxs-lookup"><span data-stu-id="749ec-105">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="749ec-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="749ec-106">Pre-requisites</span></span>

- <span data-ttu-id="749ec-107">Visual Studio 2017 15.9.12 oder höher/ Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="749ec-107">Visual Studio 2017 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="749ec-108">.NET Core 2.1 oder ein höheres SDK</span><span class="sxs-lookup"><span data-stu-id="749ec-108">.NET Core 2.1 or later SDK</span></span>

## <a name="limitations"></a><span data-ttu-id="749ec-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="749ec-109">Limitations</span></span>

- <span data-ttu-id="749ec-110">Die Erweiterung für den ML.NET-Modell-Generator funktioniert zurzeit nur in Visual Studio für Windows.</span><span class="sxs-lookup"><span data-stu-id="749ec-110">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="749ec-111">Die Größe des Trainingsdatasets ist auf 1 GB beschränkt.</span><span class="sxs-lookup"><span data-stu-id="749ec-111">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="749ec-112">Für SQL Server gilt ein Grenzwert von 100.000 Zeilen für das Training.</span><span class="sxs-lookup"><span data-stu-id="749ec-112">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="749ec-113">Microsoft SQL Server Data Tools für Visual Studio 2017 wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="749ec-113">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="749ec-114">Installieren</span><span class="sxs-lookup"><span data-stu-id="749ec-114">Install</span></span>

<span data-ttu-id="749ec-115">Der ML.NET-Modell-Generator kann entweder über den Visual Studio Marketplace oder aus Visual Studio heraus installiert werden.</span><span class="sxs-lookup"><span data-stu-id="749ec-115">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span> 

### <a name="visual-studio-marketplace"></a><span data-ttu-id="749ec-116">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="749ec-116">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="749ec-117">Herunterladen vom [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span><span class="sxs-lookup"><span data-stu-id="749ec-117">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="749ec-118">Befolgen Sie die Anweisungen zur Installation auf der jeweiligen Visual Studio-Version.</span><span class="sxs-lookup"><span data-stu-id="749ec-118">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="749ec-119">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="749ec-119">Visual Studio 2017</span></span>

1. <span data-ttu-id="749ec-120">Klicken Sie in der Menüleiste auf **Tools** > **Erweiterungen und Updates**.</span><span class="sxs-lookup"><span data-stu-id="749ec-120">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>
1. <span data-ttu-id="749ec-121">Wählen Sie in der Anzeige *Erweiterungen und Updates* den *Onlineknoten* aus.</span><span class="sxs-lookup"><span data-stu-id="749ec-121">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="749ec-122">Suchen Sie in der Suchleiste nach *ML.NET-Modell-Generator*, und wählen Sie in den Ergebnissen „ML.NET-Modell-Generator (Vorschauversion)“ aus.</span><span class="sxs-lookup"><span data-stu-id="749ec-122">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>
1. <span data-ttu-id="749ec-123">Folgen Sie den Anweisungen, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="749ec-123">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="749ec-124">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="749ec-124">Visual Studio 2019</span></span>

1. <span data-ttu-id="749ec-125">Wählen Sie in der Menüleiste **Erweiterungen** > **Erweiterungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="749ec-125">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>
1. <span data-ttu-id="749ec-126">Wählen Sie in der Anzeige *Erweiterungen und Updates* den *Onlineknoten* aus.</span><span class="sxs-lookup"><span data-stu-id="749ec-126">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="749ec-127">Geben Sie in die Suchleiste *ML.NET-Modell-Generator* ein, und wählen Sie „ML.NET-Modellgenerator (Vorschauversion)“ aus.</span><span class="sxs-lookup"><span data-stu-id="749ec-127">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>
1. <span data-ttu-id="749ec-128">Folgen Sie den Anweisungen, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="749ec-128">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="749ec-129">Deinstallieren</span><span class="sxs-lookup"><span data-stu-id="749ec-129">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="749ec-130">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="749ec-130">Visual Studio 2017</span></span>

1. <span data-ttu-id="749ec-131">Wählen Sie in der Menüleiste **Tools** > **Erweiterungen und Updates** aus.</span><span class="sxs-lookup"><span data-stu-id="749ec-131">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>
1. <span data-ttu-id="749ec-132">Erweitern Sie innerhalb der Eingabeaufforderung *Erweiterung und Updates* den Knoten *Installiert*, und wählen Sie *Tools* aus.</span><span class="sxs-lookup"><span data-stu-id="749ec-132">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="749ec-133">Wählen Sie in der Liste der Tools „ML.NET-Modell-Generator“ (Vorschauversion) aus und dann *Deinstallieren*.</span><span class="sxs-lookup"><span data-stu-id="749ec-133">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>
1. <span data-ttu-id="749ec-134">Folgen Sie den Anweisungen, um die Deinstallation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="749ec-134">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="749ec-135">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="749ec-135">Visual Studio 2019</span></span>

1. <span data-ttu-id="749ec-136">Wählen Sie in der Menüleiste **Erweiterungen** > **Erweiterungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="749ec-136">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>
1. <span data-ttu-id="749ec-137">Erweitern Sie innerhalb der Eingabeaufforderung *Erweiterung und Updates* den Knoten *Installiert*, und wählen Sie *Tools* aus.</span><span class="sxs-lookup"><span data-stu-id="749ec-137">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="749ec-138">Wählen Sie in der Liste der Tools „ML.NET-Modell-Generator“ (Vorschauversion) aus und dann *Deinstallieren*.</span><span class="sxs-lookup"><span data-stu-id="749ec-138">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>
1. <span data-ttu-id="749ec-139">Folgen Sie den Anweisungen, um die Deinstallation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="749ec-139">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="749ec-140">Upgrade</span><span class="sxs-lookup"><span data-stu-id="749ec-140">Upgrade</span></span>

<span data-ttu-id="749ec-141">Der Upgradevorgang ähnelt dem Installationsvorgang.</span><span class="sxs-lookup"><span data-stu-id="749ec-141">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="749ec-142">Laden Sie entweder die neueste Version vom Visual Studio Marketplace herunter oder verwenden Sie den Erweiterungs-Manager in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="749ec-142">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
