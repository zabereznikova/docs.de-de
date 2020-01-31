---
title: Übersicht über das ComboBox-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
ms.openlocfilehash: 9fb270d7787902872a32a87c140316f756bd48aa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743849"
---
# <a name="combobox-control-overview-windows-forms"></a>Übersicht über das ComboBox-Steuerelement (Windows Forms)
Das Windows Forms <xref:System.Windows.Forms.ComboBox>-Steuerelement wird zum Anzeigen von Daten in einem Dropdown-Kombinations Feld verwendet. Standardmäßig wird das <xref:System.Windows.Forms.ComboBox> Steuerelement in zwei Teilen angezeigt: der obere Teil ist ein Textfeld, in dem der Benutzer ein Listenelement eingeben kann. Der zweite Teil ist ein Listenfeld, in dem eine Liste von Elementen angezeigt wird, aus denen der Benutzer eine Auswahl wählen kann. Weitere Informationen zu anderen Formaten von Kombinations Feldern finden Sie unter [When to use a Windows Forms ComboBox anstelle eines ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)-Steuer Felds.  
  
 Die <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>-Eigenschaft gibt einen ganzzahligen Wert zurück, der dem ausgewählten Listenelement entspricht. Sie können das ausgewählte Element Programm gesteuert ändern, indem Sie den <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Wert im Code ändern. das entsprechende Element in der Liste wird im Textfeld Teil des Kombinations Felds angezeigt. Wenn kein Element ausgewählt ist, ist der <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Wert-1. Wenn das erste Element in der Liste ausgewählt ist, wird der <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Wert auf 0 (null). Die <xref:System.Windows.Forms.ComboBox.SelectedItem%2A>-Eigenschaft ähnelt <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>, gibt jedoch in der Regel einen Zeichen folgen Wert zurück. Die <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A>-Eigenschaft gibt die Anzahl der Elemente in der Liste an, und der Wert der <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A>-Eigenschaft ist immer größer als der größtmögliche <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Wert, da <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Null basiert ist.  
  
 Um Elemente in einem <xref:System.Windows.Forms.ComboBox>-Steuerelement hinzuzufügen oder zu löschen, verwenden Sie die Methode <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> oder <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A>. Alternativ können Sie der Liste Elemente hinzufügen, indem Sie die <xref:System.Windows.Forms.ComboBox.Items%2A>-Eigenschaft im-Designer verwenden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ComboBox>
- [Übersicht über das ListBox-Steuerelement](listbox-control-overview-windows-forms.md)
- [Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Gewusst wie: Zugreifen auf spezifische Elemente in ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms](access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)
- [Gewusst wie: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
- [Gewusst wie: Erstellen einer Suchtabelle für ComboBox-, ListBox- oder CheckedListBox-Steuerelemente in Windows Forms](create-a-lookup-table-for-a-wf-combobox-listbox.md)
