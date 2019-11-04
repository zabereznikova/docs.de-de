---
title: Installieren des Modell-Generators
description: Erfahren Sie, wie Sie das ML.NET-Modell-Generator-Tool installieren.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: a1034d294012b8df5ec778fc40602fe52223961d
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774567"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="5d509-103">Installieren des ML.NET-Modell-Generators</span><span class="sxs-lookup"><span data-stu-id="5d509-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="5d509-104">Erfahren Sie, wie Sie den ML.NET-Modell-Generator installieren, um Ihre .NET-Anwendungen mit maschinellem Lernen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="5d509-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="5d509-105">Der Modell-Generator befindet sich derzeit in der Vorschauphase.</span><span class="sxs-lookup"><span data-stu-id="5d509-105">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="5d509-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5d509-106">Pre-requisites</span></span>

- <span data-ttu-id="5d509-107">Visual Studio 2017 Version 15.9.12 oder höher/Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5d509-107">Visual Studio 2017 version 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="5d509-108">.NET Core 2.1 oder ein höheres SDK</span><span class="sxs-lookup"><span data-stu-id="5d509-108">.NET Core 2.1 or later SDK</span></span>

## <a name="limitations"></a><span data-ttu-id="5d509-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5d509-109">Limitations</span></span>

- <span data-ttu-id="5d509-110">Die Erweiterung für den ML.NET-Modell-Generator funktioniert zurzeit nur in Visual Studio für Windows.</span><span class="sxs-lookup"><span data-stu-id="5d509-110">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="5d509-111">Die Größe des Trainingsdatasets ist auf 1 GB beschränkt.</span><span class="sxs-lookup"><span data-stu-id="5d509-111">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="5d509-112">Für SQL Server gilt ein Grenzwert von 100.000 Zeilen für das Training.</span><span class="sxs-lookup"><span data-stu-id="5d509-112">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="5d509-113">Microsoft SQL Server Data Tools für Visual Studio 2017 wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5d509-113">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="5d509-114">Installieren</span><span class="sxs-lookup"><span data-stu-id="5d509-114">Install</span></span>

<span data-ttu-id="5d509-115">Der ML.NET-Modell-Generator kann entweder über den Visual Studio Marketplace oder aus Visual Studio heraus installiert werden.</span><span class="sxs-lookup"><span data-stu-id="5d509-115">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span>

### <a name="visual-studio-marketplace"></a><span data-ttu-id="5d509-116">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="5d509-116">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="5d509-117">Herunterladen vom [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span><span class="sxs-lookup"><span data-stu-id="5d509-117">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="5d509-118">Befolgen Sie die Anweisungen zur Installation auf der jeweiligen Visual Studio-Version.</span><span class="sxs-lookup"><span data-stu-id="5d509-118">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="5d509-119">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="5d509-119">Visual Studio 2017</span></span>

1. <span data-ttu-id="5d509-120">Klicken Sie in der Menüleiste auf **Tools** > **Erweiterungen und Updates**.</span><span class="sxs-lookup"><span data-stu-id="5d509-120">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017-Dialogfeld zum Öffnen des Erweiterungs-Managers](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="5d509-122">Wählen Sie in der Anzeige *Erweiterungen und Updates* den *Onlineknoten* aus.</span><span class="sxs-lookup"><span data-stu-id="5d509-122">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="5d509-123">Suchen Sie in der Suchleiste nach *ML.NET-Modell-Generator*, und wählen Sie in den Ergebnissen „ML.NET-Modell-Generator (Vorschauversion)“ aus.</span><span class="sxs-lookup"><span data-stu-id="5d509-123">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![VS2017-Dialogfeld zum Suchen und Installieren der Modell-Generator-Erweiterung im Erweiterungs-Manager](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="5d509-125">Folgen Sie den Anweisungen, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5d509-125">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="5d509-126">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5d509-126">Visual Studio 2019</span></span>

1. <span data-ttu-id="5d509-127">Wählen Sie in der Menüleiste **Erweiterungen** > **Erweiterungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="5d509-127">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019-Dialogfeld zum Öffnen des Erweiterungs-Managers](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="5d509-129">Wählen Sie in der Anzeige *Erweiterungen und Updates* den *Onlineknoten* aus.</span><span class="sxs-lookup"><span data-stu-id="5d509-129">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="5d509-130">Geben Sie in die Suchleiste *ML.NET-Modell-Generator* ein, und wählen Sie „ML.NET-Modellgenerator (Vorschauversion)“ aus.</span><span class="sxs-lookup"><span data-stu-id="5d509-130">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![VS2019-Dialogfeld zum Suchen und Installieren der Modell-Generator-Erweiterung im Erweiterungs-Manager](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="5d509-132">Folgen Sie den Anweisungen, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5d509-132">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="5d509-133">Deinstallieren</span><span class="sxs-lookup"><span data-stu-id="5d509-133">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="5d509-134">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="5d509-134">Visual Studio 2017</span></span>

1. <span data-ttu-id="5d509-135">Wählen Sie in der Menüleiste **Tools** > **Erweiterungen und Updates** aus.</span><span class="sxs-lookup"><span data-stu-id="5d509-135">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017-Dialogfeld zum Öffnen der Verwaltungserweiterungen](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="5d509-137">Erweitern Sie innerhalb der Eingabeaufforderung *Erweiterung und Updates* den Knoten *Installiert*, und wählen Sie *Tools* aus.</span><span class="sxs-lookup"><span data-stu-id="5d509-137">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="5d509-138">Wählen Sie in der Liste der Tools „ML.NET-Modell-Generator“ (Vorschauversion) aus und dann *Deinstallieren*.</span><span class="sxs-lookup"><span data-stu-id="5d509-138">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2017-Dialogfeld zum Suchen und Deinstallieren der Modell-Generator-Erweiterung im Erweiterungs-Manager](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="5d509-140">Folgen Sie den Anweisungen, um die Deinstallation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5d509-140">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="5d509-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5d509-141">Visual Studio 2019</span></span>

1. <span data-ttu-id="5d509-142">Wählen Sie in der Menüleiste **Erweiterungen** > **Erweiterungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="5d509-142">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019-Dialogfeld zum Öffnen der Verwaltungserweiterungen](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="5d509-144">Erweitern Sie innerhalb der Eingabeaufforderung *Erweiterung und Updates* den Knoten *Installiert*, und wählen Sie *Tools* aus.</span><span class="sxs-lookup"><span data-stu-id="5d509-144">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="5d509-145">Wählen Sie in der Liste der Tools „ML.NET-Modell-Generator“ (Vorschauversion) aus und dann *Deinstallieren*.</span><span class="sxs-lookup"><span data-stu-id="5d509-145">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2019-Dialogfeld zum Suchen und Deinstallieren der Modell-Generator-Erweiterung im Erweiterungs-Manager](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="5d509-147">Folgen Sie den Anweisungen, um die Deinstallation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5d509-147">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="5d509-148">Upgrade</span><span class="sxs-lookup"><span data-stu-id="5d509-148">Upgrade</span></span>

<span data-ttu-id="5d509-149">Der Upgradevorgang ähnelt dem Installationsvorgang.</span><span class="sxs-lookup"><span data-stu-id="5d509-149">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="5d509-150">Laden Sie entweder die neueste Version vom Visual Studio Marketplace herunter oder verwenden Sie den Erweiterungs-Manager in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5d509-150">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
