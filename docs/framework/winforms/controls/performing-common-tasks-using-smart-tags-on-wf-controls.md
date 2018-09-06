---
title: 'Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags auf Windows Forms-Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: d1c69d2e9e89e0a4fed767216e8743a0ac9ac81d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43741132"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="1f74b-102">Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags auf Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="1f74b-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="1f74b-103">Wie Sie Formulare und Steuerelemente für die Windows Forms-Anwendung erstellen, gibt es viele Aufgaben, die Sie wiederholt ausführen.</span><span class="sxs-lookup"><span data-stu-id="1f74b-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="1f74b-104">Dies sind einige der häufig ausgeführten Aufgaben, die auftreten:</span><span class="sxs-lookup"><span data-stu-id="1f74b-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
-   <span data-ttu-id="1f74b-105">Hinzufügen oder Entfernen einer Registerkarte auf eine <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="1f74b-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
-   <span data-ttu-id="1f74b-106">Andocken eines Steuerelements zu seinem übergeordneten Element.</span><span class="sxs-lookup"><span data-stu-id="1f74b-106">Docking a control to its parent.</span></span>  
  
-   <span data-ttu-id="1f74b-107">Ändern der Ausrichtung einer <xref:System.Windows.Forms.SplitContainer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1f74b-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="1f74b-108">Um die Entwicklung zu beschleunigen, bieten viele Steuerelemente Smarttags, Kontextmenüs, die Ihnen ermöglichen, allgemeine Aufgaben wie das in einer einzigen Geste zur Entwurfszeit auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1f74b-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="1f74b-109">Diese Aufgaben heißen *Smarttag-Verben*.</span><span class="sxs-lookup"><span data-stu-id="1f74b-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="1f74b-110">Smarttags bleiben, dessen Lebensdauer im Designer eine Steuerelementinstanz zugeordnet und stehen immer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1f74b-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="1f74b-111">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1f74b-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="1f74b-112">Erstellen eines Windows Forms-Projekts</span><span class="sxs-lookup"><span data-stu-id="1f74b-112">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="1f74b-113">Mithilfe von Smarttags</span><span class="sxs-lookup"><span data-stu-id="1f74b-113">Using smart tags</span></span>  
  
-   <span data-ttu-id="1f74b-114">Aktivieren und Deaktivieren von Smarttags</span><span class="sxs-lookup"><span data-stu-id="1f74b-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="1f74b-115">Wenn Sie diese Aufgaben durchgearbeitet haben, besitzen Sie ein Verständnis für die Rolle, die diese wichtigen Layoutfunktionen spielen.</span><span class="sxs-lookup"><span data-stu-id="1f74b-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f74b-116">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="1f74b-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1f74b-117">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1f74b-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1f74b-118">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="1f74b-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="1f74b-119">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="1f74b-119">Creating the Project</span></span>  
 <span data-ttu-id="1f74b-120">Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="1f74b-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="1f74b-121">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="1f74b-121">To create the project</span></span>  
  
1.  <span data-ttu-id="1f74b-122">Erstellen Sie eine Windows-basiertes Anwendungsprojekt mit dem Namen "SmartTagsExample" (**Datei** > **neu** > **Projekt**  >   **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="1f74b-122">Create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="1f74b-123">Wählen Sie das Formular in der **Windows Forms-Designer**.</span><span class="sxs-lookup"><span data-stu-id="1f74b-123">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="1f74b-124">Mithilfe von Smarttags</span><span class="sxs-lookup"><span data-stu-id="1f74b-124">Using Smart Tags</span></span>  
 <span data-ttu-id="1f74b-125">Smarttags sind zur Entwurfszeit auf Steuerelemente, bei denen sie immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1f74b-125">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="1f74b-126">Verwenden von Smarttags</span><span class="sxs-lookup"><span data-stu-id="1f74b-126">To use smart tags</span></span>  
  
1.  <span data-ttu-id="1f74b-127">Ziehen Sie eine <xref:System.Windows.Forms.TabControl> aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="1f74b-127">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="1f74b-128">Beachten Sie die Smarttag-Glyphe (![Smarttag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), die angezeigt wird, auf der Seite des der <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="1f74b-128">Note the smart-tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2.  <span data-ttu-id="1f74b-129">Klicken Sie auf das Smarttag-Symbol.</span><span class="sxs-lookup"><span data-stu-id="1f74b-129">Click the smart-tag glyph.</span></span> <span data-ttu-id="1f74b-130">Wählen Sie das Kontextmenü, das neben dem Symbol angezeigt wird, die **Registerkarte hinzufügen** Element.</span><span class="sxs-lookup"><span data-stu-id="1f74b-130">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="1f74b-131">Beachten Sie, dass eine neue Registerkarte hinzugefügt wird die <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="1f74b-131">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3.  <span data-ttu-id="1f74b-132">Ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="1f74b-132">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="1f74b-133">Klicken Sie auf das Smarttag-Symbol.</span><span class="sxs-lookup"><span data-stu-id="1f74b-133">Click the smart-tag glyph.</span></span> <span data-ttu-id="1f74b-134">Wählen Sie das Kontextmenü, das neben dem Symbol angezeigt wird, die **Add Column** Element.</span><span class="sxs-lookup"><span data-stu-id="1f74b-134">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="1f74b-135">Beachten Sie, dass eine neue Spalte hinzugefügt wird die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1f74b-135">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5.  <span data-ttu-id="1f74b-136">Ziehen Sie eine <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="1f74b-136">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6.  <span data-ttu-id="1f74b-137">Klicken Sie auf das Smarttag-Symbol.</span><span class="sxs-lookup"><span data-stu-id="1f74b-137">Click the smart-tag glyph.</span></span> <span data-ttu-id="1f74b-138">Wählen Sie das Kontextmenü, das neben dem Symbol angezeigt wird, die **horizontale teilerausrichtung** Element.</span><span class="sxs-lookup"><span data-stu-id="1f74b-138">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="1f74b-139">Beachten Sie, dass die <xref:System.Windows.Forms.SplitContainer> Teilerleiste des Steuerelements ist jetzt horizontal ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="1f74b-139">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f74b-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f74b-140">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [<span data-ttu-id="1f74b-141">Exemplarische Vorgehensweise: Hinzufügen von Smarttags zu einer Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1f74b-141">Walkthrough: Adding Smart Tags to a Windows Forms Component</span></span>](https://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
