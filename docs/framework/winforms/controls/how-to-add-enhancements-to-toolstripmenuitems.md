---
title: 'Vorgehensweise: Hinzufügen von Erweiterungen zu ToolStripMenuItems'
ms.date: 03/30/2017
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
ms.openlocfilehash: 9e95c3623bf9bad8395f586392a0557ad1cde880
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912585"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="d206a-102">Vorgehensweise: Hinzufügen von Erweiterungen zu ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="d206a-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="d206a-103">Es gibt folgende Möglichkeiten, um <xref:System.Windows.Forms.MenuStrip> die <xref:System.Windows.Forms.ContextMenuStrip> Verwendbarkeit von-und-Steuerelementen zu verbessern:</span><span class="sxs-lookup"><span data-stu-id="d206a-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="d206a-104">Fügen Sie Kontrollzeichen hinzu, um anzugeben, ob eine Funktion aktiviert oder deaktiviert ist, z. b. ob ein Lineal am Rand einer Textverarbeitungsanwendung angezeigt wird, oder um anzugeben, welche Datei in einer Liste von Dateien angezeigt wird, z. b. in einem **Fenster** Menü.</span><span class="sxs-lookup"><span data-stu-id="d206a-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="d206a-105">Fügen Sie Bilder hinzu, die Menübefehle visuell darstellen.</span><span class="sxs-lookup"><span data-stu-id="d206a-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="d206a-106">Zeigen Sie Tastenkombinationen an, um eine Tastatur Alternative zur Maus zum Ausführen von Befehlen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d206a-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="d206a-107">Wenn Sie z. b. STRG + C drücken, wird der Befehl **Kopieren** durchführt.</span><span class="sxs-lookup"><span data-stu-id="d206a-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="d206a-108">Zeigen Sie Zugriffstasten an, um eine Tastatur Alternative zur Maus zur Menü Navigation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d206a-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="d206a-109">Wenn Sie z. b. ALT + F drücken, wird das Menü **Datei** ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="d206a-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="d206a-110">Trennlinien zum Gruppieren verwandter Befehle anzeigen und Menüs besser lesbar machen.</span><span class="sxs-lookup"><span data-stu-id="d206a-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="d206a-111">So zeigen Sie ein Häkchen in einem Menübefehl an</span><span class="sxs-lookup"><span data-stu-id="d206a-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="d206a-112">Legen Sie <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> die- `true`Eigenschaft auf fest.</span><span class="sxs-lookup"><span data-stu-id="d206a-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="d206a-113">Dadurch wird auch die <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> -Eigenschaft `true`auf festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d206a-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="d206a-114">Verwenden Sie dieses Verfahren nur, wenn der Menübefehl standardmäßig als aktiviert angezeigt werden soll, unabhängig davon, ob er ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d206a-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="d206a-115">So zeigen Sie ein Häkchen an, das den Zustand bei jedem Klick ändert</span><span class="sxs-lookup"><span data-stu-id="d206a-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="d206a-116">Legen Sie die- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Eigenschaft des Menübefehls auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="d206a-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="d206a-117">So fügen Sie einem Menübefehl ein Bild hinzu</span><span class="sxs-lookup"><span data-stu-id="d206a-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="d206a-118">Legen Sie die-Eigenschaft <xref:System.Windows.Forms.ToolStripItem.Image%2A> des Menübefehls auf den Namen des Bilds fest.</span><span class="sxs-lookup"><span data-stu-id="d206a-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="d206a-119">Wenn die <xref:System.Windows.Forms.ToolStripItemDisplayStyle> -Eigenschaft dieses Menübefehls auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> oder <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>festgelegt ist, kann das Bild nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d206a-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d206a-120">Der Bildrand kann auch ein Häkchen anzeigen, wenn Sie diese Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="d206a-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="d206a-121">Außerdem können Sie die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> -Eigenschaft des Bilds auf `true`festlegen, und das Bild wird zur Laufzeit mit einem ausgebrüpften Rahmen herum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d206a-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="d206a-122">So zeigen Sie eine Tastenkombination für einen Menübefehl an</span><span class="sxs-lookup"><span data-stu-id="d206a-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="d206a-123">Legen Sie die-Eigenschaft <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> des Menübefehls auf die gewünschte Tastaturkombination fest, z. b. STRG + O für den Menübefehl <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> **Öffnen** , `true`und legen Sie die-Eigenschaft auf fest.</span><span class="sxs-lookup"><span data-stu-id="d206a-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="d206a-124">So zeigen Sie benutzerdefinierte Tastenkombinationen für einen Menübefehl an</span><span class="sxs-lookup"><span data-stu-id="d206a-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="d206a-125">Legen Sie die-Eigenschaft <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> des Menübefehls auf die gewünschte Tastaturkombination fest, z. b. STRG + UMSCHALT + o anstelle von UMSCHALT + STRG + <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> o, `true`und legen Sie die-Eigenschaft auf fest.</span><span class="sxs-lookup"><span data-stu-id="d206a-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="d206a-126">So zeigen Sie eine Zugriffstaste für einen Menübefehl an</span><span class="sxs-lookup"><span data-stu-id="d206a-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="d206a-127">Wenn Sie die <xref:System.Windows.Forms.ToolStripItem.Text%2A> -Eigenschaft für den Menübefehl festgelegt haben, geben Sie vor dem Buchstaben, den Sie als Zugriffsschlüssel unterstrichen möchten, ein kaufmännisches und-Objekt (&) ein.</span><span class="sxs-lookup"><span data-stu-id="d206a-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="d206a-128">Wenn Sie z. `&Open` b. <xref:System.Windows.Forms.ToolStripItem.Text%2A> als Eigenschaft eines Menü Elements eingeben, führt dies zu einem Menübefehl, der als <u>O</u>Pen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d206a-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="d206a-129">Zum Navigieren zu diesem Menübefehl drücken Sie alt, um den <xref:System.Windows.Forms.MenuStrip>Fokus auf zu setzen, und drücken Sie die Zugriffstaste des Menü namens.</span><span class="sxs-lookup"><span data-stu-id="d206a-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="d206a-130">Wenn das Menü geöffnet wird und Elemente mit Zugriffs Schlüsseln angezeigt werden, müssen Sie nur die Zugriffstaste drücken, um den Menübefehl auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d206a-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d206a-131">Vermeiden Sie das definieren doppelter Zugriffsschlüssel, z. b. das doppelte definieren von Alt + F im gleichen Menüsystem.</span><span class="sxs-lookup"><span data-stu-id="d206a-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="d206a-132">Die Auswahl Reihenfolge doppelter Zugriffsschlüssel kann nicht garantiert werden.</span><span class="sxs-lookup"><span data-stu-id="d206a-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="d206a-133">So zeigen Sie eine Trennlinie zwischen Menübefehlen an</span><span class="sxs-lookup"><span data-stu-id="d206a-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="d206a-134">Nachdem Sie <xref:System.Windows.Forms.MenuStrip> das und die darin enthaltenen Elemente definiert haben, verwenden Sie <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> die <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> -Methode oder die-Methode, <xref:System.Windows.Forms.ToolStripSeparator> um die Menü <xref:System.Windows.Forms.MenuStrip> Befehle und-Steuerelemente in der gewünschten Reihenfolge hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d206a-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d206a-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d206a-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="d206a-136">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d206a-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
