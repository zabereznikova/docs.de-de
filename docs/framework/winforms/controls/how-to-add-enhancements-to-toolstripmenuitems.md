---
title: "Gewusst wie: Hinzuf&#252;gen von Erweiterungen zu ToolStripMenuItems | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Häkchen, Hinzufügen zu Menüs"
  - "Befehle [Windows Forms], Gruppieren in Menüs"
  - "Bilder [Windows Forms], Hinzufügen zu Menüs"
  - "Tastenkombinationen, Anzeigen in Menüs"
  - "Menüelemente, Hinzufügen von Häkchen"
  - "Menüelemente, Hinzufügen von Grafiken"
  - "Menüelemente, Anzeigen von Zugriffstasten"
  - "Menüelemente, Anzeigen von Tastenkombinationen"
  - "Menüelemente, Anzeigen von Trennzeichen"
  - "Menüs, Gruppieren von Befehlen"
  - "Trennzeichen, Anzeigen in Menüs"
  - "ToolStripMenuItems"
  - "ToolStripMenuItems, Hinzufügen von Häkchen"
  - "ToolStripMenuItems, Hinzufügen von Grafiken"
  - "ToolStripMenuItems, Anzeigen von Zugriffstasten"
  - "ToolStripMenuItems, Anzeigen von Tastenkombinationen"
  - "ToolStripMenuItems, Anzeigen von Trennleisten"
  - "ToolStripSeparators, Anzeigen für MenuStrips"
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Hinzuf&#252;gen von Erweiterungen zu ToolStripMenuItems
Sie können die Verwendungsmöglichkeiten des <xref:System.Windows.Forms.MenuStrip>\-Steuerelements und <xref:System.Windows.Forms.ContextMenuStrip>\-Steuerelements wie folgt erweitern.  
  
-   Fügen Sie Häkchen hinzu, um zu kennzeichnen, ob ein Feature aktiviert oder deaktiviert ist \(ob beispielsweise ein Lineal am Rand eines Textverarbeitungsprogramms angezeigt wird\) oder welche Datei aus einer Dateiliste gerade angezeigt wird \(z. B. im Menü **Fenster**\).  
  
-   Fügen Sie Bilder hinzu, die Menübefehle visuell darstellen.  
  
-   Zeigen Sie Tastenkombinationen an, um eine Alternative zum Aufrufen von Befehlen mit der Maus bereitzustellen.  Durch Drücken von STRG\+C wird z. B. der Befehl **Copy** ausgeführt.  
  
-   Zeigen Sie Zugriffstasten an, um eine Alternative zur Menünavigation mit der Maus bereitzustellen.  Durch Drücken von ALT\+F wird z. B. das Menü **Datei** ausgewählt.  
  
-   Zeigen Sie Trennlinien an, um verwandte Befehle zu gruppieren und Menüs übersichtlicher zu gestalten.  
  
### So zeigen Sie für einen Menübefehl ein Häkchen an  
  
-   Legen Sie die entsprechende <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>\-Eigenschaft auf `true` fest.  
  
     Dadurch wird außerdem die <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A>\-Eigenschaft auf `true` festgelegt.  Verwenden Sie diese Prozedur nur, wenn der Menübefehl standardmäßig mit einem Häkchen angezeigt werden soll, unabhängig davon, ob er ausgewählt wurde.  
  
### So zeigen Sie ein Häkchen an, das seinen Zustand bei jedem Klick ändert  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>\-Eigenschaft des Menübefehls auf `true` fest.  
  
### So fügen Sie ein Bild zu einem Menübefehl hinzu  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Image%2A>\-Eigenschaft des Menübefehls auf den Namen des Bilds fest.  Wenn die <xref:System.Windows.Forms.ToolStripItemDisplayStyle>\-Eigenschaft dieses Menübefehls auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle> oder <xref:System.Windows.Forms.ToolStripItemDisplayStyle> festgelegt ist, kann das Bild nicht angezeigt werden.  
  
> [!NOTE]
>  Am Bildrand kann bei Bedarf ebenfalls ein Häkchen angezeigt werden.  Außerdem können Sie die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>\-Eigenschaft des Bildes auf `true` festlegen, sodass zur Laufzeit ein schraffierter Rand um das Bild angezeigt wird.  
  
### So zeigen Sie eine Tastenkombination für einen Menübefehl an  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>\-Eigenschaft des Menübefehls auf die gewünschte Tastenkombination fest \(z. B. STRG\+O für den Menübefehl **Öffnen**\), und legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>\-Eigenschaft auf `true` fest.  
  
### So zeigen Sie benutzerdefinierte Tastenkombinationen für einen Menübefehl an  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A>\-Eigenschaft des Menübefehls auf die gewünschte Tastenkombination fest \(z. B. STRG\+UMSCHALT\+O anstelle von UMSCHALT\-STRG\+O\), und legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>\-Eigenschaft auf `true` fest.  
  
### So zeigen Sie eine Zugriffstaste für einen Menübefehl an  
  
-   Wenn Sie die <xref:System.Windows.Forms.ToolStripItem.Text%2A>\-Eigenschaft für den Menübefehl festlegen, geben Sie ein kaufmännisches Und\-Zeichen \(&\) vor dem Buchstaben ein, den Sie als Zugriffstaste definieren möchten.  Wenn Sie beispielsweise `&Open` als <xref:System.Windows.Forms.ToolStripItem.Text%2A>\-Eigenschaft eines Menüelements eingeben, wird der Menübefehl **Ö**ffnen angezeigt.  
  
     Um zu diesem Menübefehlt zu navigieren, drücken Sie die ALT\-TASTE, damit <xref:System.Windows.Forms.MenuStrip> den Fokus erhält, und drücken dann die im Menünamen enthaltene Zugriffstaste.  Sobald das Menü geöffnet ist und Elemente mit Zugriffstasten angezeigt werden, brauchen Sie nur die Zugriffstaste zu drücken, um den betreffenden Menübefehl auszuwählen.  
  
> [!NOTE]
>  Definieren Sie keine doppelten Zugriffstasten, indem Sie beispielsweise ALT\+F im gleichen Menüsystem zweimal definieren.  Die Auswahlreihenfolge doppelter Zugriffstasten kann nicht garantiert werden.  
  
### So zeigen Sie zwischen Menübefehlen eine Trennlinie an  
  
-   Verwenden Sie nach der Definition des <xref:System.Windows.Forms.MenuStrip> und der darin enthaltenen Elemente die <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>\-Methode oder <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>\-Methode, um die Menübefehle und <xref:System.Windows.Forms.ToolStripSeparator>\-Steuerelemente in der gewünschten Reihenfolge zum <xref:System.Windows.Forms.MenuStrip> hinzuzufügen.  
  
     \[Visual Basic\]  
  
    ```  
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
  
     \[C\#\]  
  
    ```  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Übersicht über das MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)