---
title: "&#220;bersicht &#252;ber das ComboBox-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
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
  - "ComboBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kombinationsfelder, Informationen über Kombinationsfelder"
  - "ComboBox-Steuerelement [Windows Forms], Informationen über das ComboBox-Steuerelement"
  - "Dropdownlisten, ComboBox-Steuerelement"
  - "Dropdownlisten, Windows Forms"
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# &#220;bersicht &#252;ber das ComboBox-Steuerelement (Windows&#160;Forms)
Das <xref:System.Windows.Forms.ComboBox>\-Steuerelement wird in Windows Forms zum Anzeigen von Daten in einem Dropdown\-Kombinationsfeld verwendet.  In der Standardeinstellung wird das <xref:System.Windows.Forms.ComboBox>\-Steuerelement in zwei Teilen angezeigt: Der obere Bereich ist ein Textfeld, in das der Benutzer ein Listenelement eingeben kann.  Der zweite Bereich ist ein Listenfeld mit einer Liste von Elementen, aus denen der Benutzer eines auswählen kann.  Weitere Informationen über andere Arten von Kombinationsfeldern finden Sie unter [Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 Die <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>\-Eigenschaft gibt einen ganzzahligen Wert zurück, der dem ausgewählten Listenelement entspricht.  Sie können das ausgewählte Element programmgesteuert ändern, indem Sie den <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>\-Wert im Code modifizieren. Das entsprechende Listenelement wird im Textfeldbereich des Kombinationsfelds angezeigt.  Wenn kein Element ausgewählt ist, lautet der <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>\-Wert \-1.  Wenn das erste Listenelement ausgewählt ist, lautet der <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>\-Wert 0.  Die <xref:System.Windows.Forms.ComboBox.SelectedItem%2A>\-Eigenschaft ist mit <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> vergleichbar. Sie gibt jedoch das Element selbst zurück, normalerweise einen Zeichenfolgenwert.  Die <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A>\-Eigenschaft gibt die Anzahl der Listenelemente an. Der Wert der <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A>\-Eigenschaft ist immer um eins größer als der größtmöglichte <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>\-Wert, da <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> nullbasiert ist.  
  
 Verwenden Sie zum Hinzufügen oder zum Löschen von Elementen in einem <xref:System.Windows.Forms.ComboBox>\-Steuerelement die Methoden <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> oder <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A>.  Alternativ können Sie Listenelemente auch im Designer mithilfe der <xref:System.Windows.Forms.ComboBox.Items%2A>\-Eigenschaft hinzufügen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ComboBox>   
 [Übersicht über das ListBox\-Steuerelement](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)   
 [Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)   
 [Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox\-, ListBox\- oder CheckedListBox\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [Gewusst wie: Sortieren des Inhalts eines ComboBox\-, ListBox\- oder CheckedListBox\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [Gewusst wie: Zugreifen auf spezifische Elemente in ComboBox\-, ListBox\- oder CheckedListBox\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)   
 [Gewusst wie: Binden eines ComboBox\-Steuerelements oder ListBox\-Steuerelements in Windows Forms an Daten](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)   
 [Steuerelemente in Windows Forms zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)   
 [Gewusst wie: Erstellen einer Suchtabelle für ComboBox\-, ListBox\- oder CheckedListBox\-Steuerelemente in Windows Forms](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)