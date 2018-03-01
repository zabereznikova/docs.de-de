---
title: "Gewusst wie: Erstellen von Text mit variabler Größe in einem ComboBox-Steuerelement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- vb
helpviewer_keywords:
- text [Windows Forms], drawing in combo boxes
- examples [Windows Forms], ComboBox control
- combo boxes [Windows Forms], drawing text
- ComboBox control [Windows Forms], examples [C#]
- ComboBox control [Windows Forms], drawing custom text
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b8658b51515d8d3934613b40a8d4bec0ab9bf618
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a>Gewusst wie: Erstellen von Text mit variabler Größe in einem ComboBox-Steuerelement
In diesem Beispiel veranschaulicht das benutzerdefinierte Zeichnen von Text in einem <xref:System.Windows.Forms.ComboBox> Steuerelement. Wenn ein Element eine bestimmte Kriterien erfüllt, ist es in einer größeren Schrift gezeichnet und Rot.  
  
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
  
-   Ein Windows Form.  
  
-   Ein <xref:System.Windows.Forms.ComboBox> Steuerelement namens `ListBox1` mit drei Elementen in der <xref:System.Windows.Forms.ComboBox.Items%2A> Eigenschaft. In diesem Beispiel werden die drei Elemente mit Namen `"One", Two", and Three"`. Die <xref:System.Windows.Forms.ComboBox.DrawMode%2A> Eigenschaft `ComboBox1` muss festgelegt werden, um <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>.  
  
    > [!NOTE]
    >  Dieses Verfahren gilt auch für die <xref:System.Windows.Forms.ListBox> Steuerelement – können Sie auch eine <xref:System.Windows.Forms.ListBox> für die <xref:System.Windows.Forms.ComboBox>.  
  
-   Verweise auf die Namespaces <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ComboBox.DrawItem>  
 <xref:System.Windows.Forms.DrawItemEventArgs>  
 <xref:System.Windows.Forms.ComboBox.MeasureItem>  
 [Steuerelemente mit integrierter Ownerdrawing-Unterstützung](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)  
 [ListBox-Steuerelement](../../../../docs/framework/winforms/controls/listbox-control-windows-forms.md)  
 [ComboBox-Steuerelement](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)
