---
title: 'Vorgehensweise: Aktivieren von AutoComplete in ToolStrip-Steuerelementen in Windows Forms'
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
ms.openlocfilehash: d7919bf87444ef6c4a64ee236356e762da14853f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307898"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>Vorgehensweise: Aktivieren von AutoComplete in ToolStrip-Steuerelementen in Windows Forms
Das folgende Verfahren kombiniert eine <xref:System.Windows.Forms.ToolStripLabel> mit einer <xref:System.Windows.Forms.ToolStripComboBox> , können gelöscht werden, nach unten zum Anzeigen einer Liste von Elementen, z. B. zuletzt besuchten Websites. Wenn der Benutzer ein Zeichen, der das erste Zeichen eines der Elemente in der Liste entspricht eingibt, wird das Element sofort angezeigt.  
  
> [!NOTE]
>  Automatische Vervollständigung funktioniert mit `ToolStrip` Steuerelemente auf die gleiche Weise, die sie mit traditionellen Steuerelementen, wie z. B. funktioniert <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.TextBox>.  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>Zum Aktivieren von AutoComplete in ToolStrip-Steuerelement  
  
1. Erstellen Sie eine <xref:System.Windows.Forms.ToolStrip> steuern, und fügen Sie Elemente hinzu.  
  
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
  
2. Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> Eigenschaft der Bezeichnung und das Kombinationsfeld <xref:System.Windows.Forms.ToolStripItemOverflow.Never> , damit die Liste immer zur Verfügung, unabhängig von der Größe des Formulars ist.  
  
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
  
3. Hinzufügen von Wörtern, die Items-Auflistung, der die <xref:System.Windows.Forms.ToolStripComboBox> Steuerelement.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. Legen Sie die <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> -Eigenschaft des Kombinationsfelds auf <xref:System.Windows.Forms.AutoCompleteMode.Append>.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. Legen Sie die <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> -Eigenschaft des Kombinationsfelds auf <xref:System.Windows.Forms.AutoCompleteSource.ListItems>.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
- [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md)
- [Zusammenfassung der ToolStrip-Technologie](toolstrip-technology-summary.md)
