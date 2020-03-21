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
ms.openlocfilehash: 18b17aaea9d2354c03bb43f3fdd8d3779697cf58
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142017"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>Gewusst wie: Aktivieren von AutoComplete in ToolStrip-Steuerelementen in Windows Forms
Das folgende Verfahren <xref:System.Windows.Forms.ToolStripLabel> kombiniert <xref:System.Windows.Forms.ToolStripComboBox> eine mit einer, die heruntergelassen werden kann, um eine Liste von Elementen anzuzeigen, z. B. kürzlich besuchte Websites. Wenn der Benutzer ein Zeichen eingibt, das mit dem ersten Zeichen eines der Elemente in der Liste übereinstimmt, wird das Element sofort angezeigt.  
  
> [!NOTE]
> Die automatische `ToolStrip` Vervollständigung funktioniert mit Steuerelementen auf die <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.TextBox>gleiche Weise wie mit herkömmlichen Steuerelementen wie und .  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>So aktivieren Sie AutoComplete in einem ToolStrip-Steuerelement  
  
1. Erstellen <xref:System.Windows.Forms.ToolStrip> Sie ein Steuerelement, und fügen Sie ihm Elemente hinzu.  
  
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
  
2. Legen <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> Sie die Eigenschaft der Beschriftung <xref:System.Windows.Forms.ToolStripItemOverflow.Never> und des Kombinationsfelds so fest, dass die Liste unabhängig von der Größe des Formulars immer verfügbar ist.  
  
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
  
3. Fügen Sie der Items-Auflistung des <xref:System.Windows.Forms.ToolStripComboBox> Steuerelements Wörter hinzu.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. Legen <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> Sie die Eigenschaft <xref:System.Windows.Forms.AutoCompleteMode.Append>des Kombinationsfelds auf .  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. Legen <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> Sie die Eigenschaft <xref:System.Windows.Forms.AutoCompleteSource.ListItems>des Kombinationsfelds auf .  
  
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
