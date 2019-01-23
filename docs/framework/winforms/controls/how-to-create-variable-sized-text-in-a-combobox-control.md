---
title: 'Vorgehensweise: Erstellen von Text mit variabler Größe in einem ComboBox-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- text [Windows Forms], drawing in combo boxes
- examples [Windows Forms], ComboBox control
- combo boxes [Windows Forms], drawing text
- ComboBox control [Windows Forms], examples [C#]
- ComboBox control [Windows Forms], drawing custom text
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
ms.openlocfilehash: 2a9f6e8a1c96c2a9bf9e56c1c6acefc4181a18dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526989"
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a>Vorgehensweise: Erstellen von Text mit variabler Größe in einem ComboBox-Steuerelement
In diesem Beispiel wird veranschaulicht, benutzerdefinierte Zeichnungen von Text in einem <xref:System.Windows.Forms.ComboBox> Steuerelement. Wenn ein Element eine bestimmte Kriterien erfüllt, dabei handelt es sich in einer größeren Schrift gezeichnet roten aktiviert.  
  
## <a name="example"></a>Beispiel  
  
```vb  
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
    Dim siText As SizeF  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _  
lFont)  
    Else  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)  
    End If  
  
    e.ItemHeight = siText.Height  
    e.ItemWidth = siText.Width  
End Sub  
  
Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem  
    Dim g As Graphics = e.Graphics  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _  
e.Bounds.X, e.Bounds.Y)  
    Else  
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)  
    End If  
End Sub  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein Windows-Formular.  
  
-   Ein <xref:System.Windows.Forms.ComboBox> Steuerelement mit dem Namen `ListBox1` mit drei Elementen in der <xref:System.Windows.Forms.ComboBox.Items%2A> Eigenschaft. In diesem Beispiel werden die drei Elemente benannt `"One", Two", and Three"`. Die <xref:System.Windows.Forms.ComboBox.DrawMode%2A> Eigenschaft `ComboBox1` muss festgelegt werden, um <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>.  
  
    > [!NOTE]
    >  Dieses Verfahren gilt auch für die <xref:System.Windows.Forms.ListBox> Steuerelement – können Sie auch eine <xref:System.Windows.Forms.ListBox> für die <xref:System.Windows.Forms.ComboBox>.  
  
-   Verweise auf die Namespaces <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ComboBox.DrawItem>
- <xref:System.Windows.Forms.DrawItemEventArgs>
- <xref:System.Windows.Forms.ComboBox.MeasureItem>
- [Steuerelemente mit integrierter Ownerdrawing-Unterstützung](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)
- [ListBox-Steuerelement](../../../../docs/framework/winforms/controls/listbox-control-windows-forms.md)
- [ComboBox-Steuerelement](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)
