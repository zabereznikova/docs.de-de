---
title: 'Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags für Windows Forms-Steuerelemente'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 1cc854d735ba88a301d6e2f6a83fe5c8bf881380
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211418"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="1b81c-102">Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags für Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="1b81c-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>

<span data-ttu-id="1b81c-103">Wie Sie Formulare und Steuerelemente für die Windows Forms-Anwendung erstellen, gibt es viele Aufgaben, die Sie wiederholt ausführen.</span><span class="sxs-lookup"><span data-stu-id="1b81c-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="1b81c-104">Dies sind einige der häufig ausgeführten Aufgaben, die auftreten:</span><span class="sxs-lookup"><span data-stu-id="1b81c-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="1b81c-105">Hinzufügen oder Entfernen einer Registerkarte auf eine <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="1b81c-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="1b81c-106">Andocken eines Steuerelements zu seinem übergeordneten Element.</span><span class="sxs-lookup"><span data-stu-id="1b81c-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="1b81c-107">Ändern der Ausrichtung einer <xref:System.Windows.Forms.SplitContainer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1b81c-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="1b81c-108">Um die Entwicklung zu beschleunigen, bieten viele Steuerelemente Smarttags, Kontextmenüs, die Ihnen ermöglichen, allgemeine Aufgaben wie das in einer einzigen Geste zur Entwurfszeit auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1b81c-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="1b81c-109">Diese Aufgaben heißen *Smarttag-Verben*.</span><span class="sxs-lookup"><span data-stu-id="1b81c-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="1b81c-110">Smarttags bleiben, dessen Lebensdauer im Designer eine Steuerelementinstanz zugeordnet und stehen immer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1b81c-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

<span data-ttu-id="1b81c-111">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1b81c-111">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="1b81c-112">Erstellen eines Windows Forms-Projekts</span><span class="sxs-lookup"><span data-stu-id="1b81c-112">Creating a Windows Forms project</span></span>

- <span data-ttu-id="1b81c-113">Mithilfe von Smarttags</span><span class="sxs-lookup"><span data-stu-id="1b81c-113">Using smart tags</span></span>

- <span data-ttu-id="1b81c-114">Aktivieren und Deaktivieren von Smarttags</span><span class="sxs-lookup"><span data-stu-id="1b81c-114">Enabling and Disabling Smart Tags</span></span>

<span data-ttu-id="1b81c-115">Wenn Sie diese Aufgaben durchgearbeitet haben, besitzen Sie ein Verständnis für die Rolle, die diese wichtigen Layoutfunktionen spielen.</span><span class="sxs-lookup"><span data-stu-id="1b81c-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="1b81c-116">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="1b81c-116">Create the project</span></span>

<span data-ttu-id="1b81c-117">Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="1b81c-117">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="1b81c-118">Erstellen Sie in Visual Studio ein Windows-basiertes Anwendungsprojekt mit dem Namen "SmartTagsExample" (**Datei** > **neu** > **Projekt**  >  **Visual C#**  oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="1b81c-118">In Visual Studio, create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="1b81c-119">Wählen Sie das Formular in der **Windows Forms-Designer**.</span><span class="sxs-lookup"><span data-stu-id="1b81c-119">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="1b81c-120">Verwenden von Smarttags</span><span class="sxs-lookup"><span data-stu-id="1b81c-120">Use smart tags</span></span>

<span data-ttu-id="1b81c-121">Smarttags sind zur Entwurfszeit auf Steuerelemente, bei denen sie immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1b81c-121">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="1b81c-122">Ziehen Sie eine <xref:System.Windows.Forms.TabControl> aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="1b81c-122">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="1b81c-123">Beachten Sie die Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), die angezeigt wird, auf der Seite des der <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="1b81c-123">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="1b81c-124">Klicken Sie auf das Smarttag-Symbol.</span><span class="sxs-lookup"><span data-stu-id="1b81c-124">Click the smart-tag glyph.</span></span> <span data-ttu-id="1b81c-125">Wählen Sie das Kontextmenü, das neben dem Symbol angezeigt wird, die **Registerkarte hinzufügen** Element.</span><span class="sxs-lookup"><span data-stu-id="1b81c-125">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="1b81c-126">Beachten Sie, dass eine neue Registerkarte hinzugefügt wird die <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="1b81c-126">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="1b81c-127">Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="1b81c-127">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="1b81c-128">Klicken Sie auf das Smarttag-Symbol.</span><span class="sxs-lookup"><span data-stu-id="1b81c-128">Click the smart-tag glyph.</span></span> <span data-ttu-id="1b81c-129">Wählen Sie das Kontextmenü, das neben dem Symbol angezeigt wird, die **Add Column** Element.</span><span class="sxs-lookup"><span data-stu-id="1b81c-129">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="1b81c-130">Beachten Sie, dass eine neue Spalte hinzugefügt wird die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1b81c-130">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="1b81c-131">Ziehen Sie ein <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="1b81c-131">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="1b81c-132">Klicken Sie auf das Smarttag-Symbol.</span><span class="sxs-lookup"><span data-stu-id="1b81c-132">Click the smart-tag glyph.</span></span> <span data-ttu-id="1b81c-133">Wählen Sie das Kontextmenü, das neben dem Symbol angezeigt wird, die **horizontale teilerausrichtung** Element.</span><span class="sxs-lookup"><span data-stu-id="1b81c-133">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="1b81c-134">Beachten Sie, dass die <xref:System.Windows.Forms.SplitContainer> Teilerleiste des Steuerelements ist jetzt horizontal ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="1b81c-134">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b81c-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b81c-135">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- <span data-ttu-id="1b81c-136">[Exemplarische Vorgehensweise: Hinzufügen von Smarttags zu einer Komponente in Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="1b81c-136">[Walkthrough: Adding Smart Tags to a Windows Forms Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span></span>
