---
title: 'Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags für Windows Forms-Steuerelemente'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 34c14c0afd9632b06947fd72e46ddbda070cfb0f
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015762"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a><span data-ttu-id="dc6f3-102">Exemplarische Vorgehensweise: Ausführen allgemeiner Aufgaben mit Smarttags</span><span class="sxs-lookup"><span data-stu-id="dc6f3-102">Walkthrough: Perform Common Tasks Using Smart Tags</span></span>

<span data-ttu-id="dc6f3-103">Wenn Sie Formulare und Steuerelemente für Ihre Windows Forms-Anwendung erstellen, gibt es viele Aufgaben, die Sie wiederholt ausführen werden.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="dc6f3-104">Dies sind einige der häufig ausgeführten Aufgaben, die Sie ausführen werden:</span><span class="sxs-lookup"><span data-stu-id="dc6f3-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="dc6f3-105">Hinzufügen oder Entfernen einer Registerkarte <xref:System.Windows.Forms.TabControl>auf einem.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="dc6f3-106">Andocken eines Steuer Elements an das übergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="dc6f3-107">Ändern der Ausrichtung eines <xref:System.Windows.Forms.SplitContainer> Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="dc6f3-108">Um die Entwicklung zu beschleunigen, bieten viele Steuerelemente Smarttags, bei denen es sich um Kontextbezogene Menüs handelt, mit denen Sie häufige Aufgaben wie diese in einer einzigen Geste zur Entwurfszeit ausführen können.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="dc6f3-109">Diese Aufgaben werden als *Smarttag-Verben*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="dc6f3-110">Smarttags bleiben während ihrer Lebensdauer im Designer an eine Steuerelement Instanz angefügt und sind immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="dc6f3-111">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="dc6f3-111">Create the project</span></span>

<span data-ttu-id="dc6f3-112">Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="dc6f3-113">Erstellen Sie in Visual Studio ein Windows-basiertes Anwendungsprojekt mit dem Namen **SmartTagsExample**.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-113">In Visual Studio, create a Windows-based application project called **SmartTagsExample**.</span></span>

2. <span data-ttu-id="dc6f3-114">Wählen Sie in der **Windows Forms-Designer**das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="dc6f3-115">Smarttags verwenden</span><span class="sxs-lookup"><span data-stu-id="dc6f3-115">Use smart tags</span></span>

<span data-ttu-id="dc6f3-116">Smarttags sind immer zur Entwurfszeit für Steuerelemente verfügbar, die Sie bieten.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-116">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="dc6f3-117">Ziehen Sie <xref:System.Windows.Forms.TabControl> ein aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="dc6f3-118">Beachten Sie das Smarttagsymbol (![smarttagglyphe](./media/vs-winformsmttagglyph.gif)), das <xref:System.Windows.Forms.TabControl>auf der Seite von angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-118">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="dc6f3-119">Klicken Sie auf das Smarttagsymbol.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-119">Click the smart-tag glyph.</span></span> <span data-ttu-id="dc6f3-120">Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **Registerkarte hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="dc6f3-121">Beachten Sie, dass der <xref:System.Windows.Forms.TabControl>eine neue Registerkarte hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="dc6f3-122">Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="dc6f3-123">Klicken Sie auf das Smarttagsymbol.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-123">Click the smart-tag glyph.</span></span> <span data-ttu-id="dc6f3-124">Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **Spalten hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="dc6f3-125">Beachten Sie, dass dem <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement eine neue Spalte hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="dc6f3-126">Ziehen Sie ein <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="dc6f3-127">Klicken Sie auf das Smarttagsymbol.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-127">Click the smart-tag glyph.</span></span> <span data-ttu-id="dc6f3-128">Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **horizontale Splitter Ausrichtung** aus.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-128">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="dc6f3-129">Beachten Sie, <xref:System.Windows.Forms.SplitContainer> dass die Splitter Leiste des Steuer Elements nun horizontal ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="dc6f3-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc6f3-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc6f3-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
