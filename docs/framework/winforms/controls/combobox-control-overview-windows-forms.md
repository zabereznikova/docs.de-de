---
title: "Übersicht über das ComboBox-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 979a410020ab6e3a1f2c15dcee52b062eb00c1ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="combobox-control-overview-windows-forms"></a>Übersicht über das ComboBox-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.ComboBox> Steuerelement wird verwendet, um Daten aus einem Dropdown-Kombinationsfeld angezeigt. Wird standardmäßig die <xref:System.Windows.Forms.ComboBox> Steuerelement wird in zwei Teilen: der obere Bereich ist ein Textfeld, das dem Benutzer ermöglicht, geben Sie ein Listenelement. Der zweite Teil ist ein Listenfeld, in dem eine Liste von Elementen angezeigt, in dem der Benutzer eine auswählen kann. Weitere Informationen zu anderen Formaten des Kombinationsfelds finden Sie unter [verwenden Sie eine Windows Forms ComboBox Instead Of ' ListBox '](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 Die <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Eigenschaft gibt einen ganzzahligen Wert, der zum ausgewählten Listenelement erfolgt. Sie können das ausgewählte Element programmgesteuert ändern, durch Ändern der <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> im Code-Wert; das entsprechende Element in der Liste in den Textfeldbereich des Kombinationsfelds angezeigt wird. Wenn kein Element ausgewählt ist, die <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Wert ist 1. Wenn das erste Element in der Liste ausgewählt ist, und klicken Sie dann die <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Wert ist 0. Die <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> Eigenschaft ähnelt <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> , aber gibt das Element selbst, in der Regel einen Zeichenfolgenwert zurück. Die <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> Eigenschaft zeigt die Anzahl der Elemente in der Liste, und der Wert von der <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> Eigenschaft ist immer eine mehr als der größtmögliche <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> bewertet werden, da <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> ist nullbasiert.  
  
 Hinzufügen oder Löschen von Elementen in einem <xref:System.Windows.Forms.ComboBox> steuern, verwenden Sie die <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> oder <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A> Methode. Sie können auch Elemente zur Liste hinzufügen, mit der <xref:System.Windows.Forms.ComboBox.Items%2A> Eigenschaft im Designer.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ComboBox>  
 [Übersicht über das ListBox-Steuerelement](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [Gewusst wie: Zugreifen auf spezifische Elemente in ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)  
 [Gewusst wie: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [Windows Forms-Steuerelemente zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [Gewusst wie: Erstellen einer Suchtabelle für ComboBox-, ListBox- oder CheckedListBox-Steuerelemente in Windows Forms](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)
