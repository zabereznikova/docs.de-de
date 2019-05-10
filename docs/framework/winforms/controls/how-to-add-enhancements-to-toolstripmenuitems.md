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
ms.openlocfilehash: 2aa2315667b34ac448ac34cd29402e39d59e79dc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624100"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="1965e-102">Vorgehensweise: Hinzufügen von Erweiterungen zu ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="1965e-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="1965e-103">Sie können die benutzerfreundlichkeit verbessern <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> Steuerelemente es gibt folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="1965e-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="1965e-104">Hinzufügen von Häkchen, um festzulegen, ob ein Feature aktiviert ist, aktiviert oder deaktiviert, wie z. B., ob ein Lineal am Rand des eine textverarbeitungsanwendung angezeigt wird, oder, um anzugeben, welche Datei in einer Liste von Dateien angezeigt, z. B. auf wird eine **Fenster** ein Menü.</span><span class="sxs-lookup"><span data-stu-id="1965e-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="1965e-105">Hinzufügen von Bildern, die Befehle im Menü visuell darstellen.</span><span class="sxs-lookup"><span data-stu-id="1965e-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="1965e-106">Zeigen Sie die Tastenkombinationen für die eine Alternative, die der Maus, die zum Ausführen der Befehle bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1965e-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="1965e-107">Drücken STRG + C führt z. B. die **Kopie** Befehl.</span><span class="sxs-lookup"><span data-stu-id="1965e-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="1965e-108">Anzeigen von Tastenkombinationen Menünavigation eine Alternative zur Maus bereit.</span><span class="sxs-lookup"><span data-stu-id="1965e-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="1965e-109">Z. B. durch Drücken von ALT + F wählt die **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="1965e-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="1965e-110">Anzeigen von Trennleisten gruppiert Befehle und Menüs besser lesbar machen.</span><span class="sxs-lookup"><span data-stu-id="1965e-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="1965e-111">So zeigen Sie ein Häkchen auf einen Menübefehl an</span><span class="sxs-lookup"><span data-stu-id="1965e-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="1965e-112">Legen Sie dessen <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="1965e-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="1965e-113">Hiermit auch die <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="1965e-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="1965e-114">Verwenden Sie dieses Verfahren nur, wenn Sie die Menübefehls so, als unabhängig davon, ob diese Option ausgewählt ist standardmäßig als aktiviert dargestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1965e-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="1965e-115">Um ein Häkchen anzuzeigen, die mit jedem Klick Zustandsänderungen</span><span class="sxs-lookup"><span data-stu-id="1965e-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="1965e-116">Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="1965e-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="1965e-117">Hinzufügen eines Bilds zu einem Menübefehl</span><span class="sxs-lookup"><span data-stu-id="1965e-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="1965e-118">Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripItem.Image%2A> -Eigenschaft auf den Namen des Bilds.</span><span class="sxs-lookup"><span data-stu-id="1965e-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="1965e-119">Wenn die <xref:System.Windows.Forms.ToolStripItemDisplayStyle> dieses Menübefehls-Eigenschaftensatz auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> oder <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, das Bild kann nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1965e-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1965e-120">Bildrand kann auch mit einem Häkchen versehen anzeigen, wenn Sie es wünschen.</span><span class="sxs-lookup"><span data-stu-id="1965e-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="1965e-121">Sie können auch festlegen, die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Eigenschaft des Bildes, das `true`, und das Bild wird zur Laufzeit mit einem schraffierten Rahmen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1965e-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="1965e-122">Um eine Tastenkombination für einen Menübefehl anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1965e-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="1965e-123">Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> Eigenschaft, um die gewünschte Tastenkombination wie STRG + O, für die **öffnen** Kontextmenübefehl von "", und legen die <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="1965e-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="1965e-124">Benutzerdefinierte Tastenkombinationen für einen Menübefehl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1965e-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="1965e-125">Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> Eigenschaft, um die gewünschte Tastenkombination wie STRG + UMSCHALT + O anstatt UMSCHALT + STRG + O und Menge der <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="1965e-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="1965e-126">Eine Zugriffstaste für einen Menübefehl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1965e-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="1965e-127">Beim Festlegen der <xref:System.Windows.Forms.ToolStripItem.Text%2A> -Eigenschaft für den Menübefehl aus, geben Sie ein kaufmännisches und-Zeichen (&) vor dem Buchstaben als Zugriffstaste unterstrichen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1965e-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="1965e-128">Geben Sie z. B. `&Open` als die <xref:System.Windows.Forms.ToolStripItem.Text%2A> -Eigenschaft eines Menüelements führt dazu, einen Menübefehl, der als erscheint <u>O</u>Stift.</span><span class="sxs-lookup"><span data-stu-id="1965e-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="1965e-129">Drücken Sie ALT, um den Fokus erhalten, navigieren Sie zu dieser Menübefehl, der <xref:System.Windows.Forms.MenuStrip>, und drücken Sie den Zugriffsschlüssel, der den Namen des Menüs.</span><span class="sxs-lookup"><span data-stu-id="1965e-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="1965e-130">Wenn das Menü geöffnet und Elemente mit Zugriffstasten zeigt, müssen Sie nur die Access-Taste auf den Menübefehl auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="1965e-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1965e-131">Vermeiden Sie doppelte Zugriffstasten, dazu gehört das Definieren von ALT + F zweimal im gleichen Menüsystem definieren.</span><span class="sxs-lookup"><span data-stu-id="1965e-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="1965e-132">Die Reihenfolge der Auswahl der doppelte Zugriffstasten kann nicht garantiert werden.</span><span class="sxs-lookup"><span data-stu-id="1965e-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="1965e-133">Eine Trennlinie zwischen Befehle im Menü angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1965e-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="1965e-134">Nach der Definition Ihrer <xref:System.Windows.Forms.MenuStrip> und die Elemente enthält, verwenden die <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> oder <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> Methode, um die Befehle im Menü hinzuzufügen und <xref:System.Windows.Forms.ToolStripSeparator> -Steuerelementen an die <xref:System.Windows.Forms.MenuStrip> in der gewünschten Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="1965e-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1965e-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1965e-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="1965e-136">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1965e-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
