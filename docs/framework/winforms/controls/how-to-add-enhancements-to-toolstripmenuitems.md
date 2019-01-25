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
ms.openlocfilehash: 621b96805543abb92bc73f734f1a090d9cdb7319
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685084"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Vorgehensweise: Hinzufügen von Erweiterungen zu ToolStripMenuItems
Sie können die benutzerfreundlichkeit verbessern <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> Steuerelemente es gibt folgende Möglichkeiten:  
  
-   Hinzufügen von Häkchen, um festzulegen, ob ein Feature aktiviert ist, aktiviert oder deaktiviert, wie z. B., ob ein Lineal am Rand des eine textverarbeitungsanwendung angezeigt wird, oder, um anzugeben, welche Datei in einer Liste von Dateien angezeigt, z. B. auf wird eine **Fenster** ein Menü.  
  
-   Hinzufügen von Bildern, die Befehle im Menü visuell darstellen.  
  
-   Zeigen Sie die Tastenkombinationen für die eine Alternative, die der Maus, die zum Ausführen der Befehle bereitzustellen. Drücken STRG + C führt z. B. die **Kopie** Befehl.  
  
-   Anzeigen von Tastenkombinationen Menünavigation eine Alternative zur Maus bereit. Z. B. durch Drücken von ALT + F wählt die **Datei** Menü.  
  
-   Anzeigen von Trennleisten gruppiert Befehle und Menüs besser lesbar machen.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>So zeigen Sie ein Häkchen auf einen Menübefehl an  
  
-   Legen Sie dessen <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Eigenschaft `true`.  
  
     Hiermit auch die <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> Eigenschaft `true`. Verwenden Sie dieses Verfahren nur, wenn Sie die Menübefehls so, als unabhängig davon, ob diese Option ausgewählt ist standardmäßig als aktiviert dargestellt werden soll.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>Um ein Häkchen anzuzeigen, die mit jedem Klick Zustandsänderungen  
  
-   Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Eigenschaft `true`.  
  
### <a name="to-add-an-image-to-a-menu-command"></a>Hinzufügen eines Bilds zu einem Menübefehl  
  
-   Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripItem.Image%2A> -Eigenschaft auf den Namen des Bilds. Wenn die <xref:System.Windows.Forms.ToolStripItemDisplayStyle> dieses Menübefehls-Eigenschaftensatz auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> oder <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, das Bild kann nicht angezeigt werden.  
  
> [!NOTE]
>  Bildrand kann auch mit einem Häkchen versehen anzeigen, wenn Sie es wünschen. Sie können auch festlegen, die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Eigenschaft des Bildes, das `true`, und das Bild wird zur Laufzeit mit einem schraffierten Rahmen angezeigt.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>Um eine Tastenkombination für einen Menübefehl anzuzeigen.  
  
-   Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> Eigenschaft, um die gewünschte Tastenkombination wie STRG + O, für die **öffnen** Kontextmenübefehl von "", und legen die <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> Eigenschaft `true`.  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>Benutzerdefinierte Tastenkombinationen für einen Menübefehl angezeigt.  
  
-   Legen Sie des Menübefehls <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> Eigenschaft, um die gewünschte Tastenkombination wie STRG + UMSCHALT + O anstatt UMSCHALT + STRG + O und Menge der <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> Eigenschaft `true`.  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>Eine Zugriffstaste für einen Menübefehl angezeigt.  
  
-   Beim Festlegen der <xref:System.Windows.Forms.ToolStripItem.Text%2A> -Eigenschaft für den Menübefehl aus, geben Sie ein kaufmännisches und-Zeichen (&) vor dem Buchstaben als Zugriffstaste unterstrichen werden sollen. Geben Sie z. B. `&Open` als die <xref:System.Windows.Forms.ToolStripItem.Text%2A> -Eigenschaft eines Menüelements führt dazu, einen Menübefehl, der als erscheint <u>O</u>Stift.
  
     Drücken Sie ALT, um den Fokus erhalten, navigieren Sie zu dieser Menübefehl, der <xref:System.Windows.Forms.MenuStrip>, und drücken Sie den Zugriffsschlüssel, der den Namen des Menüs. Wenn das Menü geöffnet und Elemente mit Zugriffstasten zeigt, müssen Sie nur die Access-Taste auf den Menübefehl auszuwählen.  
  
> [!NOTE]
>  Vermeiden Sie doppelte Zugriffstasten, dazu gehört das Definieren von ALT + F zweimal im gleichen Menüsystem definieren. Die Reihenfolge der Auswahl der doppelte Zugriffstasten kann nicht garantiert werden.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>Eine Trennlinie zwischen Befehle im Menü angezeigt.  
  
-   Nach der Definition Ihrer <xref:System.Windows.Forms.MenuStrip> und die Elemente enthält, verwenden die <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> oder <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> Methode, um die Befehle im Menü hinzuzufügen und <xref:System.Windows.Forms.ToolStripSeparator> -Steuerelementen an die <xref:System.Windows.Forms.MenuStrip> in der gewünschten Reihenfolge.  
  
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
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
