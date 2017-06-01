---
title: "&#220;bersicht &#252;ber das ListBox-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ListBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Listenfelder, Informationen über Listenfelder"
  - "ListBox-Steuerelement [Windows Forms], Informationen über das ListBox-Steuerelement"
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# &#220;bersicht &#252;ber das ListBox-Steuerelement (Windows&#160;Forms)
Mit dem <xref:System.Windows.Forms.ListBox>\-Steuerelement für Windows Forms kann eine Liste angezeigt werden, aus der die Benutzer ein oder mehrere Elemente auswählen können.  Wenn nicht alle Elemente gleichzeitig angezeigt werden können, wird dem <xref:System.Windows.Forms.ListBox>\-Steuerelement automatisch eine Schiebeleiste hinzugefügt.  Wenn die <xref:System.Windows.Forms.ListBox.MultiColumn%2A>\-Eigenschaft auf `true` festgelegt ist, werden die Elemente im Listenfeld in mehreren Spalten angezeigt. Außerdem wird auch eine horizontale Schiebeleiste angezeigt.  Wenn die <xref:System.Windows.Forms.ListBox.MultiColumn%2A>\-Eigenschaft auf `false` festgelegt ist, werden die Elemente im Listenfeld in einer Spalte angezeigt. Außerdem wird eine vertikale Schiebeleiste angezeigt.  Wenn <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> auf `true` festgelegt ist, wird die Schiebeleiste unabhängig von der Anzahl der Elemente immer angezeigt.  Die <xref:System.Windows.Forms.ListBox.SelectionMode%2A>\-Eigenschaft bestimmt, wie viele Listenelemente gleichzeitig ausgewählt werden können.  
  
## Möglichkeiten zum Ändern des ListBox\-Steuerelements  
 Die <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>\-Eigenschaft gibt einen ganzzahligen Wert zurück, der dem ersten ausgewählten Listenelement entspricht.  Sie können das ausgewählte Element programmgesteuert ändern, indem Sie den <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>\-Wert im Code modifizieren. Das entsprechende Listenelement wird im Windows Form hervorgehoben.  Wenn kein Element ausgewählt ist, lautet der <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>\-Wert \-1.  Wenn das erste Element in der Liste ausgewählt ist, ist der <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>\-Wert 0.  Wenn mehrere Elemente ausgewählt werden, reflektiert der <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>\-Wert das ausgewählte Element, das zuerst in der Liste angezeigt wird.  Die <xref:System.Windows.Forms.ListBox.SelectedItem%2A>\-Eigenschaft ist mit <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> vergleichbar. Sie gibt jedoch das Element selbst zurück, normalerweise einen Zeichenfolgenwert.  Die <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A>\-Eigenschaft gibt die Anzahl der Listenelemente an. Der Wert der <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A>\-Eigenschaft ist immer um eins größer als der größtmöglichte <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>\-Wert, da <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> nullbasiert ist.  
  
 Verwenden Sie zum Hinzufügen oder zum Löschen von Elementen in einem <xref:System.Windows.Forms.ListBox>\-Steuerelement die Methoden <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> oder <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A>.  Alternativ können Sie Listenelemente auch zur Entwurfszeit mithilfe der <xref:System.Windows.Forms.ListBox.Items%2A>\-Eigenschaft hinzufügen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ListBox>   
 [Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox\-, ListBox\- oder CheckedListBox\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [Gewusst wie: Sortieren des Inhalts eines ComboBox\-, ListBox\- oder CheckedListBox\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [Gewusst wie: Binden eines ComboBox\-Steuerelements oder ListBox\-Steuerelements in Windows Forms an Daten](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)   
 [Übersicht über das ComboBox\-Steuerelement](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)   
 [Übersicht über das CheckedListBox\-Steuerelement](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)   
 [Steuerelemente in Windows Forms zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)   
 [Gewusst wie: Erstellen einer Suchtabelle für ComboBox\-, ListBox\- oder CheckedListBox\-Steuerelemente in Windows Forms](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)