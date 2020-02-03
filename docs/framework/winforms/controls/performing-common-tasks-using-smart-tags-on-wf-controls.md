---
title: Ausführen allgemeiner Aufgaben mit Smarttags für Steuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 826313d0a89410f62c034a5fba4dee32e90a1750
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744257"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a><span data-ttu-id="dd85e-102">Exemplarische Vorgehensweise: Ausführen allgemeiner Aufgaben mit Smarttags</span><span class="sxs-lookup"><span data-stu-id="dd85e-102">Walkthrough: Perform Common Tasks Using Smart Tags</span></span>

<span data-ttu-id="dd85e-103">Wenn Sie Formulare und Steuerelemente für Ihre Windows Forms-Anwendung erstellen, gibt es viele Aufgaben, die Sie wiederholt ausführen werden.</span><span class="sxs-lookup"><span data-stu-id="dd85e-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="dd85e-104">Dies sind einige der häufig ausgeführten Aufgaben, die Sie ausführen werden:</span><span class="sxs-lookup"><span data-stu-id="dd85e-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="dd85e-105">Hinzufügen oder Entfernen einer Registerkarte auf einem <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="dd85e-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="dd85e-106">Andocken eines Steuer Elements an das übergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="dd85e-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="dd85e-107">Ändern der Ausrichtung eines <xref:System.Windows.Forms.SplitContainer> Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="dd85e-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="dd85e-108">Um die Entwicklung zu beschleunigen, bieten viele Steuerelemente Smarttags, bei denen es sich um Kontextbezogene Menüs handelt, mit denen Sie häufige Aufgaben wie diese in einer einzigen Geste zur Entwurfszeit ausführen können.</span><span class="sxs-lookup"><span data-stu-id="dd85e-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="dd85e-109">Diese Aufgaben werden als *Smarttag-Verben*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dd85e-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="dd85e-110">Smarttags bleiben während ihrer Lebensdauer im Designer an eine Steuerelement Instanz angefügt und sind immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dd85e-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="dd85e-111">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="dd85e-111">Create the project</span></span>

<span data-ttu-id="dd85e-112">Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="dd85e-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="dd85e-113">Erstellen Sie in Visual Studio ein Windows-basiertes Anwendungsprojekt mit dem Namen **SmartTagsExample**.</span><span class="sxs-lookup"><span data-stu-id="dd85e-113">In Visual Studio, create a Windows-based application project called **SmartTagsExample**.</span></span>

2. <span data-ttu-id="dd85e-114">Wählen Sie in der **Windows Forms-Designer**das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="dd85e-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="dd85e-115">Smarttags verwenden</span><span class="sxs-lookup"><span data-stu-id="dd85e-115">Use smart tags</span></span>

<span data-ttu-id="dd85e-116">Smarttags sind immer zur Entwurfszeit für Steuerelemente verfügbar, die Sie bieten.</span><span class="sxs-lookup"><span data-stu-id="dd85e-116">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="dd85e-117">Ziehen Sie eine <xref:System.Windows.Forms.TabControl> aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="dd85e-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="dd85e-118">Beachten Sie das Smarttag-Symbol (![smarttagglyphe](./media/vs-winformsmttagglyph.gif)), das auf der Seite des <xref:System.Windows.Forms.TabControl>angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dd85e-118">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="dd85e-119">Klicken Sie auf das Smarttagsymbol.</span><span class="sxs-lookup"><span data-stu-id="dd85e-119">Click the smart-tag glyph.</span></span> <span data-ttu-id="dd85e-120">Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **Registerkarte hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dd85e-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="dd85e-121">Beachten Sie, dass dem <xref:System.Windows.Forms.TabControl>eine neue Registerkarte hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dd85e-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="dd85e-122">Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="dd85e-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="dd85e-123">Klicken Sie auf das Smarttagsymbol.</span><span class="sxs-lookup"><span data-stu-id="dd85e-123">Click the smart-tag glyph.</span></span> <span data-ttu-id="dd85e-124">Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **Spalten hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dd85e-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="dd85e-125">Beachten Sie, dass dem <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement eine neue Spalte hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dd85e-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="dd85e-126">Ziehen Sie ein <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="dd85e-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="dd85e-127">Klicken Sie auf das Smarttagsymbol.</span><span class="sxs-lookup"><span data-stu-id="dd85e-127">Click the smart-tag glyph.</span></span> <span data-ttu-id="dd85e-128">Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **horizontale Splitter Ausrichtung** aus.</span><span class="sxs-lookup"><span data-stu-id="dd85e-128">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="dd85e-129">Beachten Sie, dass die Splitter Leiste des <xref:System.Windows.Forms.SplitContainer> Steuer Elements nun horizontal ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="dd85e-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd85e-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd85e-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
