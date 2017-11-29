---
title: "Gewusst wie: Hinzufügen von Erweiterungen zu ToolStripMenuItems"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [Windows Forms], grouping on menus
- check marks [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], displaying access keys
- menus [Windows Forms], grouping commands
- menu items [Windows Forms], displaying shortcut keys
- ToolStripMenuItems
- separators [Windows Forms], displaying on menus
- menu items [Windows Forms], showing separators
- menu items [Windows Forms], adding check marks
- ToolStripMenuItems [Windows Forms], adding check marks
- menu items [Windows Forms], adding images
- ToolStripSeparators [Windows Forms], displaying on MenuStrips
- menu items [Windows Forms], displaying access keys
- ToolStripMenuItems [Windows Forms], displaying shortcut keys
- ToolStripMenuItems [Windows Forms], adding images
- keyboard shortcuts [Windows Forms], displaying on menus
- images [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], showing separator bars
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2701094ffcbcf7eeb14444163b995816398876fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="055e6-102">Gewusst wie: Hinzufügen von Erweiterungen zu ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="055e6-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="055e6-103">Sie können die Verwendbarkeit verbessern <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> Steuerelemente auf folgende Weise:</span><span class="sxs-lookup"><span data-stu-id="055e6-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
-   <span data-ttu-id="055e6-104">Hinzufügen von Häkchen zu bestimmen, ob eine Funktion aktiviert oder deaktiviert, wird z. B., ob ein Lineal am Rand eines Textverarbeitungsprogramms angezeigt wird, oder um anzugeben, welche Datei in einer Liste von Dateien angezeigt, z. B. auf wird eine **Fenster** Menü ".</span><span class="sxs-lookup"><span data-stu-id="055e6-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
-   <span data-ttu-id="055e6-105">Hinzufügen von Bildern, die Befehle im Menü visuell darstellen.</span><span class="sxs-lookup"><span data-stu-id="055e6-105">Add images that visually represent menu commands.</span></span>  
  
-   <span data-ttu-id="055e6-106">Anzeigen von Tastenkombinationen auf eine Tastatur, Maus Alternative zum Ausführen von Befehlen.</span><span class="sxs-lookup"><span data-stu-id="055e6-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="055e6-107">Drücken STRG + C führt z. B. die **Kopie** Befehl.</span><span class="sxs-lookup"><span data-stu-id="055e6-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
-   <span data-ttu-id="055e6-108">Anzeigen von Tastenkombinationen im Menünavigation eine Alternative zur Maus bereit.</span><span class="sxs-lookup"><span data-stu-id="055e6-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="055e6-109">Beispielsweise wählt die Tastenkombination ALT + F drücken der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="055e6-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
-   <span data-ttu-id="055e6-110">Zeigen Sie Trennlinien zum Gruppieren verwandter Befehle und Menüs besser lesbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="055e6-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="055e6-111">Ein Häkchen auf einen Menübefehl angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="055e6-111">To display a check mark on a menu command</span></span>  
  
-   <span data-ttu-id="055e6-112">Legen Sie dessen <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="055e6-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="055e6-113">Dies setzt auch die <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="055e6-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="055e6-114">Verwenden Sie dieses Verfahren nur, wenn Sie möchten, dass den Menübefehl angezeigt wie aktiviert ist, wird standardmäßig unabhängig davon, ob es aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="055e6-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="055e6-115">Ein Häkchen angezeigt, die mit jedem Klicken auf die statusänderung</span><span class="sxs-lookup"><span data-stu-id="055e6-115">To display a check mark that changes state with each click</span></span>  
  
-   <span data-ttu-id="055e6-116">Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="055e6-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="055e6-117">Zum Hinzufügen eines Bilds in einen Menübefehl</span><span class="sxs-lookup"><span data-stu-id="055e6-117">To add an image to a menu command</span></span>  
  
-   <span data-ttu-id="055e6-118">Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripItem.Image%2A> -Eigenschaft auf den Namen des Bilds.</span><span class="sxs-lookup"><span data-stu-id="055e6-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="055e6-119">Wenn die <xref:System.Windows.Forms.ToolStripItemDisplayStyle> des mit diesem Befehl wird-Eigenschaftensatz auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> oder <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, das Bild kann nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="055e6-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="055e6-120">Der Image-Rand kann auch ein Häkchen anzeigen, wenn Sie also entscheiden.</span><span class="sxs-lookup"><span data-stu-id="055e6-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="055e6-121">Sie können auch festlegen, die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Eigenschaft des Images `true`, und das Bild wird zur Laufzeit mit einem schraffierten Rahmen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="055e6-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="055e6-122">Um eine Tastenkombination für einen Menübefehl anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="055e6-122">To display a shortcut key for a menu command</span></span>  
  
-   <span data-ttu-id="055e6-123">Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> Eigenschaft, um die gewünschte Tastenkombination, z. B. STRG + O, für die **öffnen** Menübefehl aus, und legen die <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="055e6-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="055e6-124">Benutzerdefinierte Tastenkombinationen für einen Menübefehl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="055e6-124">To display custom shortcut keys for a menu command</span></span>  
  
-   <span data-ttu-id="055e6-125">Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> Eigenschaft, um die gewünschte Tastenkombination, z. B. STRG + UMSCHALT + O anstatt UMSCHALT + STRG + O, und legen die <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="055e6-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="055e6-126">Um eine Zugriffstaste für einen Menübefehl anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="055e6-126">To display an access key for a menu command</span></span>  
  
-   <span data-ttu-id="055e6-127">Beim Festlegen der <xref:System.Windows.Forms.ToolStripItem.Text%2A> -Eigenschaft für den Menübefehl aus, geben Sie ein kaufmännisches und-Zeichen (&) vor dem Buchstaben als Zugriffstaste unterstrichen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="055e6-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="055e6-128">Geben Sie z. B. `&Open` als die <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaft eines Menüelements führt dazu, einen Menübefehl, das wie **O**Stift.</span><span class="sxs-lookup"><span data-stu-id="055e6-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as **O**pen.</span></span>  
  
     <span data-ttu-id="055e6-129">Drücken Sie ALT, um den Fokus erhalten, um zu dieser Menübefehl zu navigieren, die <xref:System.Windows.Forms.MenuStrip>, und drücken Sie die Zugriffstaste für den Namen des Menüs.</span><span class="sxs-lookup"><span data-stu-id="055e6-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="055e6-130">Wenn das Menü geöffnet und Elemente mit Zugriffstasten zeigt, müssen Sie nur zum Drücken der Zugriffstaste auf den Menübefehl auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="055e6-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="055e6-131">Vermeiden Sie doppelte Zugriffstasten, gehört das Definieren von ALT + F zweimal in der gleichen Menüsystem definieren.</span><span class="sxs-lookup"><span data-stu-id="055e6-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="055e6-132">Die Reihenfolge der Auswahl der doppelte Zugriffstasten kann nicht garantiert werden.</span><span class="sxs-lookup"><span data-stu-id="055e6-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="055e6-133">Eine Trennlinie zwischen Menübefehlen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="055e6-133">To display a separator bar between menu commands</span></span>  
  
-   <span data-ttu-id="055e6-134">Nach dem Definieren der <xref:System.Windows.Forms.MenuStrip> und die darin enthaltenen Elemente verwenden die <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> oder <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> Methode, um die Befehle im Menü hinzuzufügen und <xref:System.Windows.Forms.ToolStripSeparator> -Steuerelementen an die <xref:System.Windows.Forms.MenuStrip> in der gewünschten Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="055e6-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
    ```vb  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,   
    ' and the Save and Exit menu commands to the top-level File menu,   
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
    ```  
  
    ```csharp  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,   
    // and the Save and Exit menu commands to the top-level File menu,   
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="055e6-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="055e6-135">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="055e6-136">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="055e6-136">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
