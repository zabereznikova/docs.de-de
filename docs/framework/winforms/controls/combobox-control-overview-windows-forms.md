---
title: Übersicht über das ComboBox-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
ms.openlocfilehash: 80056771744c9b97828a024adf32638e545a839e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956168"
---
# <a name="combobox-control-overview-windows-forms"></a>Übersicht über das ComboBox-Steuerelement (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.ComboBox> Steuerelement zur Anzeige von Daten in einem Dropdown-Kombinationsfeld verwendet wird. In der Standardeinstellung die <xref:System.Windows.Forms.ComboBox> Steuerelement angezeigt wird, in zwei Teilen: der obere Bereich ist das Textfeld, das dem Benutzer ermöglicht, geben Sie ein Listenelement. Der zweite Teil ist ein Listenfeld, das eine Liste von Elementen anzeigt, in dem der Benutzer eine auswählen kann. Weitere Informationen zu anderen Arten des Kombinationsfelds, finden Sie unter [verwenden eine Windows Forms "ComboBox" Instead Of eines Listenfelds](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 Die <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Eigenschaft gibt einen ganzzahligen Wert, der auf dem ausgewählten Element zurück. Sie können das ausgewählte Element programmgesteuert ändern, durch Ändern der <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Wert im Code, wird das entsprechende Element in der Liste im Textfeldbereich des Kombinationsfelds angezeigt. Wenn kein Element ausgewählt ist, die <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Wert ist 1. Wenn das erste Element in der Liste ausgewählt ist, und klicken Sie dann die <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Wert ist 0. Die <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> Eigenschaft ähnelt <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> , aber gibt das Element selbst, in der Regel einen Zeichenfolgenwert zurück. Die <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> Eigenschaft spiegelt wider, die Anzahl der Elemente in der Liste, und der Wert des der <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> Eigenschaft ist immer einer mehr als der größtmögliche <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> bewertet werden, da <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> ist nullbasiert.  
  
 Hinzufügen oder Löschen von Elementen in einem <xref:System.Windows.Forms.ComboBox> steuern, verwenden Sie die <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> oder <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A> Methode. Sie können auch Elemente der Liste hinzufügen, mit der <xref:System.Windows.Forms.ComboBox.Items%2A> Eigenschaft im Designer.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ComboBox>
- [Übersicht über das ListBox-Steuerelement](listbox-control-overview-windows-forms.md)
- [Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen aus einer Windows Forms, ComboBox-, ListBox- oder CheckedListBox-Steuerelement](add-and-remove-items-from-a-wf-combobox.md)
- [Vorgehensweise: Sortieren des Inhalts einer Windows Forms-ComboBox-, ListBox- oder CheckedListBox-Steuerelement](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Vorgehensweise: Zugreifen auf spezifische Elemente in einer Windows Forms, ComboBox-, ListBox- oder CheckedListBox-Steuerelement](access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)
- [Vorgehensweise: Binden eines Windows Forms-Kombinationsfeld oder das ListBox-Steuerelement an Daten](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
- [Vorgehensweise: Erstellen einer Nachschlagetabelle für eine Windows-ComboBox-, ListBox- oder CheckedListBox-Steuerelement Forms](create-a-lookup-table-for-a-wf-combobox-listbox.md)
