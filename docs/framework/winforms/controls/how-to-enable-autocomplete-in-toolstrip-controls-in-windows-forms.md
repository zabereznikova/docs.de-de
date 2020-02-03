---
title: 'Gewusst wie: Aktivieren von AutoComplete in ToolStrip-Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
ms.openlocfilehash: db411023ad624e4c3d60b09bdbd588c85f8e22d1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745506"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>Gewusst wie: Aktivieren von AutoComplete in ToolStrip-Steuerelementen in Windows Forms
Im folgenden Verfahren wird eine <xref:System.Windows.Forms.ToolStripLabel> mit einer <xref:System.Windows.Forms.ToolStripComboBox> kombiniert, die zum Anzeigen einer Liste von Elementen, z. b. zuletzt besuchten Websites, gelöscht werden können. Wenn der Benutzer ein Zeichen eingibt, das mit dem ersten Zeichen eines der Elemente in der Liste übereinstimmt, wird das Element sofort angezeigt.  
  
> [!NOTE]
> Die automatische Vervollständigung funktioniert mit `ToolStrip` Steuerelementen auf die gleiche Weise wie bei herkömmlichen Steuerelementen wie <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.TextBox>.  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>So aktivieren Sie AutoComplete in einem ToolStrip-Steuerelement  
  
1. Erstellen Sie ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement, und fügen Sie ihm Elemente hinzu.  
  
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
  
2. Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>-Eigenschaft der Bezeichnung und das Kombinations Feld auf <xref:System.Windows.Forms.ToolStripItemOverflow.Never> fest, damit die Liste unabhängig von der Formular Größe immer verfügbar ist.  
  
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
  
3. Fügen Sie der Items-Auflistung des <xref:System.Windows.Forms.ToolStripComboBox>-Steuer Elements Wörter hinzu.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. Legen Sie die <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A>-Eigenschaft des Kombinations Felds auf <xref:System.Windows.Forms.AutoCompleteMode.Append>fest.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. Legen Sie die <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A>-Eigenschaft des Kombinations Felds auf <xref:System.Windows.Forms.AutoCompleteSource.ListItems>fest.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
- [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md)
- [Zusammenfassung der ToolStrip-Technologie](toolstrip-technology-summary.md)
