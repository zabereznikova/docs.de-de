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
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Gewusst wie: Hinzufügen von Erweiterungen zu ToolStripMenuItems
Sie können die Benutzerfreundlichkeit und <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> Steuerelemente auf folgende Weise verbessern:  
  
- Fügen Sie Häkchen hinzu, um anzugeben, ob ein Feature aktiviert oder deaktiviert ist, z. B. ob ein Lineal am Rand einer Textverarbeitungsanwendung angezeigt wird, oder um anzugeben, welche Datei in einer Dateiliste angezeigt wird, z. B. in einem **Fenstermenü.**  
  
- Fügen Sie Bilder hinzu, die Menübefehle visuell darstellen.  
  
- Tastenkombinationen anzeigen, um eine Tastaturalternative zur Maus zum Ausführen von Befehlen bereitzustellen. Wenn Sie z. B. STRG+C drücken, wird der Befehl **Kopieren** ausgeführt.  
  
- Zeigen Sie Die Zugriffstasten an, um eine Tastaturalternative zur Maus für die Menünavigation bereitzustellen. Wenn Sie z. B. ALT+F drücken, wird das Menü **Datei** ausgesucht.  
  
- Zeigen Sie Trennleisten an, um verwandte Befehle zu gruppieren, und machen Menüs lesbarer.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>So zeigen Sie ein Häkchen in einem Menübefehl an  
  
- Legen <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Sie `true`die Eigenschaft auf .  
  
     Dadurch wird <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> auch `true`die Eigenschaft auf festgelegt. Verwenden Sie dieses Verfahren nur, wenn der Menübefehl standardmäßig als aktiviert angezeigt werden soll, unabhängig davon, ob er ausgewählt ist.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>So zeigen Sie ein Häkchen an, das den Status mit jedem Klick ändert  
  
- Legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Eigenschaft `true`des Menübefehls auf .  
  
### <a name="to-add-an-image-to-a-menu-command"></a>So fügen Sie einem Menübefehl ein Bild hinzu  
  
- Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Image%2A> Eigenschaft des Menübefehls auf den Namen des Bildes fest. Wenn <xref:System.Windows.Forms.ToolStripItemDisplayStyle> die Eigenschaft dieses Menübefehls auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> oder <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>festgelegt ist, kann das Bild nicht angezeigt werden.  
  
> [!NOTE]
> Der Bildrand kann auch ein Häkchen anzeigen, wenn Sie dies wünschen. Außerdem können Sie <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> die Eigenschaft des `true`Bildes auf festlegen, und das Bild wird zur Laufzeit mit einem geschlüpften Rahmen um das Bild herum angezeigt.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>So zeigen Sie eine Tastenkombination für einen Menübefehl an  
  
- Legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> Eigenschaft des Menübefehls auf die gewünschte Tastaturkombination fest, z. <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> B. STRG+O für den Befehl **Öffnen** des Menüs, und legen Sie die Eigenschaft auf fest. `true`  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>So zeigen Sie benutzerdefinierte Tastenkombinationen für einen Menübefehl an  
  
- Legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> Eigenschaft des Menübefehls auf die gewünschte Tastaturkombination fest, z. B. STRG+UMSCHALT+O anstelle von SHIFT+CTRL+O, und legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> Eigenschaft auf fest. `true`  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>So zeigen Sie eine Zugriffstaste für einen Menübefehl an  
  
- Wenn Sie <xref:System.Windows.Forms.ToolStripItem.Text%2A> die Eigenschaft für den Menübefehl festlegen, geben Sie ein & vor dem Buchstaben ein, den Sie als Zugriffsschlüssel unterstrichen werden möchten. Wenn Sie z. `&Open` <xref:System.Windows.Forms.ToolStripItem.Text%2A> B. als Eigenschaft eines Menüelements eingeben, wird ein Menübefehl angezeigt, der als <u>O-Stift</u>angezeigt wird.
  
     Um zu diesem Menübefehl zu navigieren, <xref:System.Windows.Forms.MenuStrip>drücken Sie ALT, um den Fokus auf die zu geben, und drücken Sie die Zugriffstaste des Menünamens. Wenn das Menü geöffnet wird und Elemente mit Zugriffstasten anzeigt, müssen Sie nur die Zugriffstaste drücken, um den Menübefehl auszuwählen.  
  
> [!NOTE]
> Vermeiden Sie das Definieren doppelter Zugriffsschlüssel, z. B. das definieren von ALT+F zweimal im selben Menüsystem. Die Auswahlreihenfolge doppelter Zugriffsschlüssel kann nicht garantiert werden.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>So zeigen Sie eine Trennleiste zwischen Menübefehlen an  
  
- Nachdem Sie <xref:System.Windows.Forms.MenuStrip> Ihre und die darin enthaltenen <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> Elemente definiert haben, <xref:System.Windows.Forms.ToolStripSeparator> verwenden Sie <xref:System.Windows.Forms.MenuStrip> die oder-Methode, um die Menübefehle und Steuerelemente in der gewünschten Reihenfolge hinzuzufügen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Übersicht über das MenuStrip-Steuerelement](menustrip-control-overview-windows-forms.md)
