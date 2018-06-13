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
ms.openlocfilehash: 37843d27211bd07c2749b3e6fc14ec03d7bf570d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529715"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Gewusst wie: Hinzufügen von Erweiterungen zu ToolStripMenuItems
Sie können die Verwendbarkeit verbessern <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> Steuerelemente auf folgende Weise:  
  
-   Hinzufügen von Häkchen zu bestimmen, ob eine Funktion aktiviert oder deaktiviert, wird z. B., ob ein Lineal am Rand eines Textverarbeitungsprogramms angezeigt wird, oder um anzugeben, welche Datei in einer Liste von Dateien angezeigt, z. B. auf wird eine **Fenster** Menü ".  
  
-   Hinzufügen von Bildern, die Befehle im Menü visuell darstellen.  
  
-   Anzeigen von Tastenkombinationen auf eine Tastatur, Maus Alternative zum Ausführen von Befehlen. Drücken STRG + C führt z. B. die **Kopie** Befehl.  
  
-   Anzeigen von Tastenkombinationen im Menünavigation eine Alternative zur Maus bereit. Beispielsweise wählt die Tastenkombination ALT + F drücken der **Datei** Menü.  
  
-   Zeigen Sie Trennlinien zum Gruppieren verwandter Befehle und Menüs besser lesbar zu machen.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>Ein Häkchen auf einen Menübefehl angezeigt werden sollen.  
  
-   Legen Sie dessen <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Eigenschaft `true`.  
  
     Dies setzt auch die <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> Eigenschaft `true`. Verwenden Sie dieses Verfahren nur, wenn Sie möchten, dass den Menübefehl angezeigt wie aktiviert ist, wird standardmäßig unabhängig davon, ob es aktiviert ist.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>Ein Häkchen angezeigt, die mit jedem Klicken auf die statusänderung  
  
-   Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Eigenschaft `true`.  
  
### <a name="to-add-an-image-to-a-menu-command"></a>Zum Hinzufügen eines Bilds in einen Menübefehl  
  
-   Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripItem.Image%2A> -Eigenschaft auf den Namen des Bilds. Wenn die <xref:System.Windows.Forms.ToolStripItemDisplayStyle> des mit diesem Befehl wird-Eigenschaftensatz auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> oder <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, das Bild kann nicht angezeigt werden.  
  
> [!NOTE]
>  Der Image-Rand kann auch ein Häkchen anzeigen, wenn Sie also entscheiden. Sie können auch festlegen, die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Eigenschaft des Images `true`, und das Bild wird zur Laufzeit mit einem schraffierten Rahmen angezeigt.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>Um eine Tastenkombination für einen Menübefehl anzuzeigen.  
  
-   Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> Eigenschaft, um die gewünschte Tastenkombination, z. B. STRG + O, für die **öffnen** Menübefehl aus, und legen die <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> Eigenschaft `true`.  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>Benutzerdefinierte Tastenkombinationen für einen Menübefehl angezeigt.  
  
-   Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> Eigenschaft, um die gewünschte Tastenkombination, z. B. STRG + UMSCHALT + O anstatt UMSCHALT + STRG + O, und legen die <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> Eigenschaft `true`.  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>Um eine Zugriffstaste für einen Menübefehl anzuzeigen.  
  
-   Beim Festlegen der <xref:System.Windows.Forms.ToolStripItem.Text%2A> -Eigenschaft für den Menübefehl aus, geben Sie ein kaufmännisches und-Zeichen (&) vor dem Buchstaben als Zugriffstaste unterstrichen angezeigt werden sollen. Geben Sie z. B. `&Open` als die <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaft eines Menüelements führt dazu, einen Menübefehl, das wie **O**Stift.  
  
     Drücken Sie ALT, um den Fokus erhalten, um zu dieser Menübefehl zu navigieren, die <xref:System.Windows.Forms.MenuStrip>, und drücken Sie die Zugriffstaste für den Namen des Menüs. Wenn das Menü geöffnet und Elemente mit Zugriffstasten zeigt, müssen Sie nur zum Drücken der Zugriffstaste auf den Menübefehl auszuwählen.  
  
> [!NOTE]
>  Vermeiden Sie doppelte Zugriffstasten, gehört das Definieren von ALT + F zweimal in der gleichen Menüsystem definieren. Die Reihenfolge der Auswahl der doppelte Zugriffstasten kann nicht garantiert werden.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>Eine Trennlinie zwischen Menübefehlen angezeigt.  
  
-   Nach dem Definieren der <xref:System.Windows.Forms.MenuStrip> und die darin enthaltenen Elemente verwenden die <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> oder <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> Methode, um die Befehle im Menü hinzuzufügen und <xref:System.Windows.Forms.ToolStripSeparator> -Steuerelementen an die <xref:System.Windows.Forms.MenuStrip> in der gewünschten Reihenfolge.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
