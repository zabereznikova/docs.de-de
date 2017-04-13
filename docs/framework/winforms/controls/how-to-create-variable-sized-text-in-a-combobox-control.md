---
title: "Gewusst wie: Erstellen von Text mit variabler Gr&#246;&#223;e in einem ComboBox-Steuerelement | Microsoft Docs"
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
  - "Kombinationsfelder, Zeichnen von Text"
  - "ComboBox-Steuerelement [Windows Forms], Zeichnen von benutzerdefiniertem Text"
  - "ComboBox-Steuerelement [Windows Forms], Beispiele [C#]"
  - "Beispiele [Windows Forms], ComboBox-Steuerelement"
  - "Text, Zeichnen in Kombinationsfeldern"
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen von Text mit variabler Gr&#246;&#223;e in einem ComboBox-Steuerelement
In diesem Beispiel wird das benutzerdefinierte Zeichnen von Text in einem <xref:System.Windows.Forms.ComboBox>\-Steuerelement veranschaulicht.  Wenn ein Element ein bestimmtes Kriterium erfüllt, wird es in einer größeren Schriftart gezeichnet und rot dargestellt.  
  
## Beispiel  
  
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
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein Windows Form muss vorhanden sein.  
  
-   Ein <xref:System.Windows.Forms.ComboBox>\-Steuerelement mit dem Namen  `ListBox1`  mit drei Elementen in der <xref:System.Windows.Forms.ComboBox.Items%2A>\-Eigenschaft.  In diesem Beispiel lauten die drei Elemente `"One", Two", and Three"`.  Die <xref:System.Windows.Forms.ComboBox.DrawMode%2A>\-Eigenschaft von `ComboBox1` muss auf <xref:System.Windows.Forms.DrawMode> festgelegt sein.  
  
    > [!NOTE]
    >  Diese Methode kann auch auf das <xref:System.Windows.Forms.ListBox>\-Steuerelement angewendet werden – Sie können eine <xref:System.Windows.Forms.ListBox> für die <xref:System.Windows.Forms.ComboBox> ersetzen.  
  
-   Verweise auf den <xref:System.Windows.Forms?displayProperty=fullName>\-Namespace und den <xref:System.Drawing?displayProperty=fullName>\-Namespace.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ComboBox.DrawItem>   
 <xref:System.Windows.Forms.DrawItemEventArgs>   
 <xref:System.Windows.Forms.ComboBox.MeasureItem>   
 [Steuerelemente mit integrierter Ownerdrawing\-Unterstützung](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)   
 [ListBox\-Steuerelement](../../../../docs/framework/winforms/controls/listbox-control-windows-forms.md)   
 [ComboBox\-Steuerelement](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)