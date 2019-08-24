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
ms.openlocfilehash: acc5ee47536772d98fcfe98849335933c24a41d7
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015903"
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a>Vorgehensweise: Erstellen von Text mit variabler Größe in einem ComboBox-Steuerelement
Dieses Beispiel zeigt die benutzerdefinierte Zeichnung von Text <xref:System.Windows.Forms.ComboBox> in einem-Steuerelement. Wenn ein Element bestimmte Kriterien erfüllt, wird es in einer größeren Schriftart gezeichnet und rot angezeigt.

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

- Ein Windows Form.

- Ein <xref:System.Windows.Forms.ComboBox> -Steuer `ListBox1` Element mit dem Namen mit <xref:System.Windows.Forms.ComboBox.Items%2A> drei Elementen in der-Eigenschaft. In diesem Beispiel werden die drei Elemente benannt `"One", Two", and Three"`. Die <xref:System.Windows.Forms.ComboBox.DrawMode%2A> -Eigenschaft `ComboBox1` von muss auf <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>festgelegt werden.

    > [!NOTE]
    > Dieses Verfahren gilt auch für das <xref:System.Windows.Forms.ListBox> -Steuerelement – Sie können einen <xref:System.Windows.Forms.ListBox> für die <xref:System.Windows.Forms.ComboBox>ersetzen.

- Verweise auf die Namespaces <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ComboBox.DrawItem>
- <xref:System.Windows.Forms.DrawItemEventArgs>
- <xref:System.Windows.Forms.ComboBox.MeasureItem>
- [Steuerelemente mit integrierter Ownerdrawing-Unterstützung](controls-with-built-in-owner-drawing-support.md)
- [ListBox-Steuerelement](listbox-control-windows-forms.md)
- [ComboBox-Steuerelement](combobox-control-windows-forms.md)
