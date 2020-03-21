---
title: 'Gewusst wie: Hinzufügen von Erweiterungen zu ToolStripMenuItems'
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
ms.openlocfilehash: 61a79b9bbe101d7bf694240bdffdecee5187adf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182319"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="3b720-102">Gewusst wie: Hinzufügen von Erweiterungen zu ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="3b720-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="3b720-103">Sie können die Benutzerfreundlichkeit und <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> Steuerelemente auf folgende Weise verbessern:</span><span class="sxs-lookup"><span data-stu-id="3b720-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="3b720-104">Fügen Sie Häkchen hinzu, um anzugeben, ob ein Feature aktiviert oder deaktiviert ist, z. B. ob ein Lineal am Rand einer Textverarbeitungsanwendung angezeigt wird, oder um anzugeben, welche Datei in einer Dateiliste angezeigt wird, z. B. in einem **Fenstermenü.**</span><span class="sxs-lookup"><span data-stu-id="3b720-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="3b720-105">Fügen Sie Bilder hinzu, die Menübefehle visuell darstellen.</span><span class="sxs-lookup"><span data-stu-id="3b720-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="3b720-106">Tastenkombinationen anzeigen, um eine Tastaturalternative zur Maus zum Ausführen von Befehlen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3b720-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="3b720-107">Wenn Sie z. B. STRG+C drücken, wird der Befehl **Kopieren** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3b720-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="3b720-108">Zeigen Sie Die Zugriffstasten an, um eine Tastaturalternative zur Maus für die Menünavigation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3b720-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="3b720-109">Wenn Sie z. B. ALT+F drücken, wird das Menü **Datei** ausgesucht.</span><span class="sxs-lookup"><span data-stu-id="3b720-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="3b720-110">Zeigen Sie Trennleisten an, um verwandte Befehle zu gruppieren, und machen Menüs lesbarer.</span><span class="sxs-lookup"><span data-stu-id="3b720-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="3b720-111">So zeigen Sie ein Häkchen in einem Menübefehl an</span><span class="sxs-lookup"><span data-stu-id="3b720-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="3b720-112">Legen <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Sie `true`die Eigenschaft auf .</span><span class="sxs-lookup"><span data-stu-id="3b720-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="3b720-113">Dadurch wird <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> auch `true`die Eigenschaft auf festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3b720-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="3b720-114">Verwenden Sie dieses Verfahren nur, wenn der Menübefehl standardmäßig als aktiviert angezeigt werden soll, unabhängig davon, ob er ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="3b720-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="3b720-115">So zeigen Sie ein Häkchen an, das den Status mit jedem Klick ändert</span><span class="sxs-lookup"><span data-stu-id="3b720-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="3b720-116">Legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Eigenschaft `true`des Menübefehls auf .</span><span class="sxs-lookup"><span data-stu-id="3b720-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="3b720-117">So fügen Sie einem Menübefehl ein Bild hinzu</span><span class="sxs-lookup"><span data-stu-id="3b720-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="3b720-118">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Image%2A> Eigenschaft des Menübefehls auf den Namen des Bildes fest.</span><span class="sxs-lookup"><span data-stu-id="3b720-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="3b720-119">Wenn <xref:System.Windows.Forms.ToolStripItemDisplayStyle> die Eigenschaft dieses Menübefehls auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> oder <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>festgelegt ist, kann das Bild nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3b720-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b720-120">Der Bildrand kann auch ein Häkchen anzeigen, wenn Sie dies wünschen.</span><span class="sxs-lookup"><span data-stu-id="3b720-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="3b720-121">Außerdem können Sie <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> die Eigenschaft des `true`Bildes auf festlegen, und das Bild wird zur Laufzeit mit einem geschlüpften Rahmen um das Bild herum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b720-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="3b720-122">So zeigen Sie eine Tastenkombination für einen Menübefehl an</span><span class="sxs-lookup"><span data-stu-id="3b720-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="3b720-123">Legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> Eigenschaft des Menübefehls auf die gewünschte Tastaturkombination fest, z. <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> B. STRG+O für den Befehl **Öffnen** des Menüs, und legen Sie die Eigenschaft auf fest. `true`</span><span class="sxs-lookup"><span data-stu-id="3b720-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="3b720-124">So zeigen Sie benutzerdefinierte Tastenkombinationen für einen Menübefehl an</span><span class="sxs-lookup"><span data-stu-id="3b720-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="3b720-125">Legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> Eigenschaft des Menübefehls auf die gewünschte Tastaturkombination fest, z. B. STRG+UMSCHALT+O anstelle von SHIFT+CTRL+O, und legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> Eigenschaft auf fest. `true`</span><span class="sxs-lookup"><span data-stu-id="3b720-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="3b720-126">So zeigen Sie eine Zugriffstaste für einen Menübefehl an</span><span class="sxs-lookup"><span data-stu-id="3b720-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="3b720-127">Wenn Sie <xref:System.Windows.Forms.ToolStripItem.Text%2A> die Eigenschaft für den Menübefehl festlegen, geben Sie ein & vor dem Buchstaben ein, den Sie als Zugriffsschlüssel unterstrichen werden möchten.</span><span class="sxs-lookup"><span data-stu-id="3b720-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="3b720-128">Wenn Sie z. `&Open` <xref:System.Windows.Forms.ToolStripItem.Text%2A> B. als Eigenschaft eines Menüelements eingeben, wird ein Menübefehl angezeigt, der als <u>O-Stift</u>angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3b720-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="3b720-129">Um zu diesem Menübefehl zu navigieren, <xref:System.Windows.Forms.MenuStrip>drücken Sie ALT, um den Fokus auf die zu geben, und drücken Sie die Zugriffstaste des Menünamens.</span><span class="sxs-lookup"><span data-stu-id="3b720-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="3b720-130">Wenn das Menü geöffnet wird und Elemente mit Zugriffstasten anzeigt, müssen Sie nur die Zugriffstaste drücken, um den Menübefehl auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3b720-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b720-131">Vermeiden Sie das Definieren doppelter Zugriffsschlüssel, z. B. das definieren von ALT+F zweimal im selben Menüsystem.</span><span class="sxs-lookup"><span data-stu-id="3b720-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="3b720-132">Die Auswahlreihenfolge doppelter Zugriffsschlüssel kann nicht garantiert werden.</span><span class="sxs-lookup"><span data-stu-id="3b720-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="3b720-133">So zeigen Sie eine Trennleiste zwischen Menübefehlen an</span><span class="sxs-lookup"><span data-stu-id="3b720-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="3b720-134">Nachdem Sie <xref:System.Windows.Forms.MenuStrip> Ihre und die darin enthaltenen <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> Elemente definiert haben, <xref:System.Windows.Forms.ToolStripSeparator> verwenden Sie <xref:System.Windows.Forms.MenuStrip> die oder-Methode, um die Menübefehle und Steuerelemente in der gewünschten Reihenfolge hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3b720-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3b720-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b720-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="3b720-136">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3b720-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
