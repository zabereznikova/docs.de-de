---
title: Installieren des Modell-Generators
description: Erfahren Sie, wie Sie das ML.NET-Modell-Generator-Tool installieren.
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.custom: mvc, how-to, mlnet-tooling
ms.openlocfilehash: b944d7f6044553251132824e7e4213119e34500e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78848651"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="6b79a-103">Installieren des ML.NET-Modell-Generators</span><span class="sxs-lookup"><span data-stu-id="6b79a-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="6b79a-104">Erfahren Sie, wie Sie den ML.NET-Modell-Generator installieren, um Ihre .NET-Anwendungen mit maschinellem Lernen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="6b79a-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="6b79a-105">Der Modell-Generator befindet sich derzeit in der Vorschauphase.</span><span class="sxs-lookup"><span data-stu-id="6b79a-105">Model Builder is currently in Preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6b79a-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6b79a-106">Prerequisites</span></span>

- <span data-ttu-id="6b79a-107">Visual Studio 2017 Version 15.9.12 oder höher/Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6b79a-107">Visual Studio 2017 version 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="6b79a-108">.NET Core 2.1 SDK oder höher.</span><span class="sxs-lookup"><span data-stu-id="6b79a-108">.NET Core 2.1 SDK or later.</span></span>

> [!NOTE]
> <span data-ttu-id="6b79a-109">Das .NET Core 3.0 SDK wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6b79a-109">.NET Core 3.0 SDK is not currently supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="6b79a-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6b79a-110">Limitations</span></span>

- <span data-ttu-id="6b79a-111">Die Erweiterung für den ML.NET-Modell-Generator funktioniert zurzeit nur in Visual Studio für Windows.</span><span class="sxs-lookup"><span data-stu-id="6b79a-111">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="6b79a-112">Die Größe des Trainingsdatasets ist auf 1 GB beschränkt.</span><span class="sxs-lookup"><span data-stu-id="6b79a-112">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="6b79a-113">Für SQL Server gilt ein Grenzwert von 100.000 Zeilen für das Training.</span><span class="sxs-lookup"><span data-stu-id="6b79a-113">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="6b79a-114">Microsoft SQL Server Data Tools für Visual Studio 2017 wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6b79a-114">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="6b79a-115">Installieren</span><span class="sxs-lookup"><span data-stu-id="6b79a-115">Install</span></span>

<span data-ttu-id="6b79a-116">Der ML.NET-Modell-Generator kann entweder über den Visual Studio Marketplace oder aus Visual Studio heraus installiert werden.</span><span class="sxs-lookup"><span data-stu-id="6b79a-116">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span>

### <a name="visual-studio-marketplace"></a><span data-ttu-id="6b79a-117">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="6b79a-117">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="6b79a-118">Herunterladen vom [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span><span class="sxs-lookup"><span data-stu-id="6b79a-118">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="6b79a-119">Befolgen Sie die Anweisungen zur Installation auf der jeweiligen Visual Studio-Version.</span><span class="sxs-lookup"><span data-stu-id="6b79a-119">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="6b79a-120">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="6b79a-120">Visual Studio 2017</span></span>

1. <span data-ttu-id="6b79a-121">Klicken Sie in der Menüleiste auf **Tools** > **Erweiterungen und Updates**.</span><span class="sxs-lookup"><span data-stu-id="6b79a-121">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017-Dialogfeld zum Öffnen des Erweiterungs-Managers](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="6b79a-123">Wählen Sie in der Anzeige *Erweiterungen und Updates* den *Onlineknoten* aus.</span><span class="sxs-lookup"><span data-stu-id="6b79a-123">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="6b79a-124">Suchen Sie in der Suchleiste nach *ML.NET-Modell-Generator*, und wählen Sie in den Ergebnissen „ML.NET-Modell-Generator (Vorschauversion)“ aus.</span><span class="sxs-lookup"><span data-stu-id="6b79a-124">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![VS2017-Dialogfeld zum Suchen und Installieren der Modell-Generator-Erweiterung im Erweiterungs-Manager](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="6b79a-126">Folgen Sie den Anweisungen, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6b79a-126">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="6b79a-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6b79a-127">Visual Studio 2019</span></span>

1. <span data-ttu-id="6b79a-128">Wählen Sie in der Menüleiste **Erweiterungen** > **Erweiterungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="6b79a-128">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019-Dialogfeld zum Öffnen des Erweiterungs-Managers](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="6b79a-130">Wählen Sie in der Anzeige *Erweiterungen und Updates* den *Onlineknoten* aus.</span><span class="sxs-lookup"><span data-stu-id="6b79a-130">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="6b79a-131">Geben Sie in die Suchleiste *ML.NET-Modell-Generator* ein, und wählen Sie „ML.NET-Modellgenerator (Vorschauversion)“ aus.</span><span class="sxs-lookup"><span data-stu-id="6b79a-131">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![VS2019-Dialogfeld zum Suchen und Installieren der Modell-Generator-Erweiterung im Erweiterungs-Manager](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="6b79a-133">Folgen Sie den Anweisungen, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6b79a-133">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="6b79a-134">Deinstallieren</span><span class="sxs-lookup"><span data-stu-id="6b79a-134">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="6b79a-135">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="6b79a-135">Visual Studio 2017</span></span>

1. <span data-ttu-id="6b79a-136">Wählen Sie in der Menüleiste **Tools** > **Erweiterungen und Updates** aus.</span><span class="sxs-lookup"><span data-stu-id="6b79a-136">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017-Dialogfeld zum Öffnen der Verwaltungserweiterungen](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="6b79a-138">Erweitern Sie innerhalb der Eingabeaufforderung *Erweiterung und Updates* den Knoten *Installiert*, und wählen Sie *Tools* aus.</span><span class="sxs-lookup"><span data-stu-id="6b79a-138">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="6b79a-139">Wählen Sie in der Liste der Tools „ML.NET-Modell-Generator“ (Vorschauversion) aus und dann *Deinstallieren*.</span><span class="sxs-lookup"><span data-stu-id="6b79a-139">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2017-Dialogfeld zum Suchen und Deinstallieren der Modell-Generator-Erweiterung im Erweiterungs-Manager](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="6b79a-141">Folgen Sie den Anweisungen, um die Deinstallation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6b79a-141">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="6b79a-142">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6b79a-142">Visual Studio 2019</span></span>

1. <span data-ttu-id="6b79a-143">Wählen Sie in der Menüleiste **Erweiterungen** > **Erweiterungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="6b79a-143">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019-Dialogfeld zum Öffnen der Verwaltungserweiterungen](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="6b79a-145">Erweitern Sie innerhalb der Eingabeaufforderung *Erweiterung und Updates* den Knoten *Installiert*, und wählen Sie *Tools* aus.</span><span class="sxs-lookup"><span data-stu-id="6b79a-145">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="6b79a-146">Wählen Sie in der Liste der Tools „ML.NET-Modell-Generator“ (Vorschauversion) aus und dann *Deinstallieren*.</span><span class="sxs-lookup"><span data-stu-id="6b79a-146">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2019-Dialogfeld zum Suchen und Deinstallieren der Modell-Generator-Erweiterung im Erweiterungs-Manager](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="6b79a-148">Folgen Sie den Anweisungen, um die Deinstallation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6b79a-148">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="6b79a-149">Upgrade</span><span class="sxs-lookup"><span data-stu-id="6b79a-149">Upgrade</span></span>

<span data-ttu-id="6b79a-150">Der Upgradevorgang ähnelt dem Installationsvorgang.</span><span class="sxs-lookup"><span data-stu-id="6b79a-150">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="6b79a-151">Laden Sie entweder die neueste Version vom Visual Studio Marketplace herunter oder verwenden Sie den Erweiterungs-Manager in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6b79a-151">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
