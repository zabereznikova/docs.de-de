---
title: "Gewusst wie: Aktivieren von AutoComplete in ToolStrip-Steuerelementen in Windows Forms | Microsoft Docs"
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
  - "AutoComplete, Aktivieren in Symbolleisten"
  - "AutoComplete, Beispiele"
  - "Beispiele [Windows Forms], Symbolleisten"
  - "Symbolleisten [Windows Forms], AutoComplete"
  - "ToolStrip-Steuerelement [Windows Forms], AutoComplete"
  - "ToolStripComboBox-Klasse, Beispiele"
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Aktivieren von AutoComplete in ToolStrip-Steuerelementen in Windows Forms
In der folgenden Prozedur wird eine <xref:System.Windows.Forms.ToolStripLabel> mit einer <xref:System.Windows.Forms.ToolStripComboBox> kombiniert, die eine Liste mit Elementen anzeigen kann, z. B. kürzlich besuchte Websites.  Wenn der Benutzer ein Zeichen eingibt, das mit dem ersten Zeichen eines der Elemente in der Liste übereinstimmt, wird dieses Element unverzüglich angezeigt.  
  
> [!NOTE]
>  Die automatische Vervollständigung funktioniert mit `ToolStrip`\-Steuerelementen genauso wie mit herkömmlichen Steuerelementen wie <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.TextBox>.  
  
### So aktivieren Sie die automatische Vervollständigung in einem ToolStrip\-Steuerelement  
  
1.  Erstellen Sie ein <xref:System.Windows.Forms.ToolStrip>\-Steuerelement, und fügen Sie ihm Elemente hinzu.  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]   
        {toolStripLabel1, toolStripComboBox1});  
  
    ```  
  
2.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>\-Eigenschaft der Bezeichnung und das Kombinationsfeld auf <xref:System.Windows.Forms.ToolStripItemOverflow> fest, sodass die Liste unabhängig von der Größe des Formulars immer verfügbar ist.  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
  
    ```  
  
3.  Fügen Sie der Items\-Auflistung des <xref:System.Windows.Forms.ToolStripComboBox>\-Steuerelements Wörter hinzu.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
  
    ```  
  
4.  Legen Sie die <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A>\-Eigenschaft des Kombinationsfelds auf <xref:System.Windows.Forms.AutoCompleteMode> fest.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
  
    ```  
  
5.  Legen Sie die <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A>\-Eigenschaft des Kombinationsfelds auf <xref:System.Windows.Forms.AutoCompleteSource> fest.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripLabel>   
 <xref:System.Windows.Forms.ToolStripComboBox>   
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>   
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>   
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Architektur des ToolStrip\-Steuerelements](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Zusammenfassung der ToolStrip\-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)