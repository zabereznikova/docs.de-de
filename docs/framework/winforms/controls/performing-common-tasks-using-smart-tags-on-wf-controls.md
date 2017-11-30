---
title: "Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags auf Windows Forms-Steuerelementen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2e6b815be85576f037e0f24668c44756b95abd6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="a49f0-102">Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags auf Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="a49f0-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="a49f0-103">Wie Sie Formulare und Steuerelemente für Windows Forms-Anwendung erstellen, sind viele Aufgaben, die wiederholt ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a49f0-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="a49f0-104">Dies sind einige der häufig ausgeführten Aufgaben, die auftreten können:</span><span class="sxs-lookup"><span data-stu-id="a49f0-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
-   <span data-ttu-id="a49f0-105">Hinzufügen oder Entfernen einer Registerkarte auf eine <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="a49f0-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
-   <span data-ttu-id="a49f0-106">Andocken eines Steuerelements an seinem übergeordneten Element.</span><span class="sxs-lookup"><span data-stu-id="a49f0-106">Docking a control to its parent.</span></span>  
  
-   <span data-ttu-id="a49f0-107">Ändern der Ausrichtung eines ein <xref:System.Windows.Forms.SplitContainer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a49f0-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="a49f0-108">Zum Beschleunigen der Entwicklung bieten viele Steuerelemente Smarttags kontextbezogene Menüs sind, mit die häufige Aufgaben wie diese in eine einzelne Geste zur Entwurfszeit ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="a49f0-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="a49f0-109">Diese Aufgaben heißen *Smarttag-Verben*.</span><span class="sxs-lookup"><span data-stu-id="a49f0-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="a49f0-110">Smarttags für seine Lebensdauer im Designer mit einer Instanz des Steuerelements verbunden bleiben und sind immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a49f0-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="a49f0-111">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="a49f0-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="a49f0-112">Erstellen eines Windows Forms-Projekts</span><span class="sxs-lookup"><span data-stu-id="a49f0-112">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="a49f0-113">Mithilfe der Smarttags</span><span class="sxs-lookup"><span data-stu-id="a49f0-113">Using smart tags</span></span>  
  
-   <span data-ttu-id="a49f0-114">Aktivieren und Deaktivieren von Smarttags</span><span class="sxs-lookup"><span data-stu-id="a49f0-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="a49f0-115">Wenn Sie diese Aufgaben durchgearbeitet haben, besitzen Sie ein Verständnis für die Rolle, die diese wichtigen Layoutfunktionen spielen.</span><span class="sxs-lookup"><span data-stu-id="a49f0-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a49f0-116">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="a49f0-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a49f0-117">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a49f0-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a49f0-118">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="a49f0-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="a49f0-119">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="a49f0-119">Creating the Project</span></span>  
 <span data-ttu-id="a49f0-120">Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="a49f0-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="a49f0-121">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="a49f0-121">To create the project</span></span>  
  
1.  <span data-ttu-id="a49f0-122">Erstellen Sie ein Windows-basierten Anwendung mit dem Namen "SmartTagsExample".</span><span class="sxs-lookup"><span data-stu-id="a49f0-122">Create a Windows-based application project called "SmartTagsExample".</span></span> <span data-ttu-id="a49f0-123">Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="a49f0-123">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="a49f0-124">Wählen Sie das Formular in der **Windows Forms-Designer**.</span><span class="sxs-lookup"><span data-stu-id="a49f0-124">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="a49f0-125">Mithilfe der Smarttags</span><span class="sxs-lookup"><span data-stu-id="a49f0-125">Using Smart Tags</span></span>  
 <span data-ttu-id="a49f0-126">Smarttags sind zur Entwurfszeit auf Steuerelemente, die sie bieten immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a49f0-126">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="a49f0-127">Verwendung von smart tags</span><span class="sxs-lookup"><span data-stu-id="a49f0-127">To use smart tags</span></span>  
  
1.  <span data-ttu-id="a49f0-128">Ziehen Sie eine <xref:System.Windows.Forms.TabControl> aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="a49f0-128">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="a49f0-129">Beachten Sie das Smarttag-Symbol (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), die angezeigt wird, auf der Seite des der <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="a49f0-129">Note the smart-tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2.  <span data-ttu-id="a49f0-130">Klicken Sie auf das Smarttag-Symbol.</span><span class="sxs-lookup"><span data-stu-id="a49f0-130">Click the smart-tag glyph.</span></span> <span data-ttu-id="a49f0-131">Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, die **Registerkarte hinzufügen** Element.</span><span class="sxs-lookup"><span data-stu-id="a49f0-131">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="a49f0-132">Beachten Sie, dass eine neue Registerkarte hinzugefügt wird die <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="a49f0-132">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3.  <span data-ttu-id="a49f0-133">Ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="a49f0-133">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="a49f0-134">Klicken Sie auf das Smarttag-Symbol.</span><span class="sxs-lookup"><span data-stu-id="a49f0-134">Click the smart-tag glyph.</span></span> <span data-ttu-id="a49f0-135">Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, die **Add Column** Element.</span><span class="sxs-lookup"><span data-stu-id="a49f0-135">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="a49f0-136">Beachten Sie, dass eine neue Spalte hinzugefügt wird die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a49f0-136">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5.  <span data-ttu-id="a49f0-137">Ziehen Sie eine <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="a49f0-137">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6.  <span data-ttu-id="a49f0-138">Klicken Sie auf das Smarttag-Symbol.</span><span class="sxs-lookup"><span data-stu-id="a49f0-138">Click the smart-tag glyph.</span></span> <span data-ttu-id="a49f0-139">Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, die **horizontale aufteilungsausrichtung** Element.</span><span class="sxs-lookup"><span data-stu-id="a49f0-139">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="a49f0-140">Beachten Sie, dass die <xref:System.Windows.Forms.SplitContainer> des Steuerelements Teilerleiste ist jetzt horizontal ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="a49f0-140">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a49f0-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a49f0-141">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [<span data-ttu-id="a49f0-142">Exemplarische Vorgehensweise: Hinzufügen von Smarttags in eine Komponente für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a49f0-142">Walkthrough: Adding Smart Tags to a Windows Forms Component</span></span>](http://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
