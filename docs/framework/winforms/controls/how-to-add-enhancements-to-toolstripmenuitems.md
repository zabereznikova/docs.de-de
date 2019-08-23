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
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Vorgehensweise: Hinzufügen von Erweiterungen zu ToolStripMenuItems
Es gibt folgende Möglichkeiten, um <xref:System.Windows.Forms.MenuStrip> die <xref:System.Windows.Forms.ContextMenuStrip> Verwendbarkeit von-und-Steuerelementen zu verbessern:  
  
- Fügen Sie Kontrollzeichen hinzu, um anzugeben, ob eine Funktion aktiviert oder deaktiviert ist, z. b. ob ein Lineal am Rand einer Textverarbeitungsanwendung angezeigt wird, oder um anzugeben, welche Datei in einer Liste von Dateien angezeigt wird, z. b. in einem **Fenster** Menü.  
  
- Fügen Sie Bilder hinzu, die Menübefehle visuell darstellen.  
  
- Zeigen Sie Tastenkombinationen an, um eine Tastatur Alternative zur Maus zum Ausführen von Befehlen bereitzustellen. Wenn Sie z. b. STRG + C drücken, wird der Befehl **Kopieren** durchführt.  
  
- Zeigen Sie Zugriffstasten an, um eine Tastatur Alternative zur Maus zur Menü Navigation bereitzustellen. Wenn Sie z. b. ALT + F drücken, wird das Menü **Datei** ausgewählt.  
  
- Trennlinien zum Gruppieren verwandter Befehle anzeigen und Menüs besser lesbar machen.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>So zeigen Sie ein Häkchen in einem Menübefehl an  
  
- Legen Sie <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> die- `true`Eigenschaft auf fest.  
  
     Dadurch wird auch die <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> -Eigenschaft `true`auf festgelegt. Verwenden Sie dieses Verfahren nur, wenn der Menübefehl standardmäßig als aktiviert angezeigt werden soll, unabhängig davon, ob er ausgewählt ist.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>So zeigen Sie ein Häkchen an, das den Zustand bei jedem Klick ändert  
  
- Legen Sie die- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Eigenschaft des Menübefehls auf `true`fest.  
  
### <a name="to-add-an-image-to-a-menu-command"></a>So fügen Sie einem Menübefehl ein Bild hinzu  
  
- Legen Sie die-Eigenschaft <xref:System.Windows.Forms.ToolStripItem.Image%2A> des Menübefehls auf den Namen des Bilds fest. Wenn die <xref:System.Windows.Forms.ToolStripItemDisplayStyle> -Eigenschaft dieses Menübefehls auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> oder <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>festgelegt ist, kann das Bild nicht angezeigt werden.  
  
> [!NOTE]
> Der Bildrand kann auch ein Häkchen anzeigen, wenn Sie diese Option auswählen. Außerdem können Sie die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> -Eigenschaft des Bilds auf `true`festlegen, und das Bild wird zur Laufzeit mit einem ausgebrüpften Rahmen herum angezeigt.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>So zeigen Sie eine Tastenkombination für einen Menübefehl an  
  
- Legen Sie die-Eigenschaft <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> des Menübefehls auf die gewünschte Tastaturkombination fest, z. b. STRG + O für den Menübefehl <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> **Öffnen** , `true`und legen Sie die-Eigenschaft auf fest.  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>So zeigen Sie benutzerdefinierte Tastenkombinationen für einen Menübefehl an  
  
- Legen Sie die-Eigenschaft <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> des Menübefehls auf die gewünschte Tastaturkombination fest, z. b. STRG + UMSCHALT + o anstelle von UMSCHALT + STRG + <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> o, `true`und legen Sie die-Eigenschaft auf fest.  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>So zeigen Sie eine Zugriffstaste für einen Menübefehl an  
  
- Wenn Sie die <xref:System.Windows.Forms.ToolStripItem.Text%2A> -Eigenschaft für den Menübefehl festgelegt haben, geben Sie vor dem Buchstaben, den Sie als Zugriffsschlüssel unterstrichen möchten, ein kaufmännisches und-Objekt (&) ein. Wenn Sie z. `&Open` b. <xref:System.Windows.Forms.ToolStripItem.Text%2A> als Eigenschaft eines Menü Elements eingeben, führt dies zu einem Menübefehl, der als <u>O</u>Pen angezeigt wird.
  
     Zum Navigieren zu diesem Menübefehl drücken Sie alt, um den <xref:System.Windows.Forms.MenuStrip>Fokus auf zu setzen, und drücken Sie die Zugriffstaste des Menü namens. Wenn das Menü geöffnet wird und Elemente mit Zugriffs Schlüsseln angezeigt werden, müssen Sie nur die Zugriffstaste drücken, um den Menübefehl auszuwählen.  
  
> [!NOTE]
> Vermeiden Sie das definieren doppelter Zugriffsschlüssel, z. b. das doppelte definieren von Alt + F im gleichen Menüsystem. Die Auswahl Reihenfolge doppelter Zugriffsschlüssel kann nicht garantiert werden.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>So zeigen Sie eine Trennlinie zwischen Menübefehlen an  
  
- Nachdem Sie <xref:System.Windows.Forms.MenuStrip> das und die darin enthaltenen Elemente definiert haben, verwenden Sie <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> die <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> -Methode oder die-Methode, <xref:System.Windows.Forms.ToolStripSeparator> um die Menü <xref:System.Windows.Forms.MenuStrip> Befehle und-Steuerelemente in der gewünschten Reihenfolge hinzuzufügen.  
  
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
- [Übersicht über das MenuStrip-Steuerelement](menustrip-control-overview-windows-forms.md)
