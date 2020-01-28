---
title: Übersicht über das ListBox-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: 1abf8bea5c786f2ce326631370fa294ada09a92c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745178"
---
# <a name="listbox-control-overview-windows-forms"></a>Übersicht über das ListBox-Steuerelement (Windows Forms)
Ein Windows Forms <xref:System.Windows.Forms.ListBox>-Steuerelement zeigt eine Liste an, aus der der Benutzer ein oder mehrere Elemente auswählen kann. Wenn die Gesamtanzahl der Elemente die angezeigte Anzahl überschreitet, wird dem <xref:System.Windows.Forms.ListBox> Steuerelement automatisch eine Schiebe Leiste hinzugefügt. Wenn die <xref:System.Windows.Forms.ListBox.MultiColumn%2A>-Eigenschaft auf `true`festgelegt ist, werden im Listenfeld Elemente in mehreren Spalten angezeigt, und eine horizontale Schiebe Leiste wird angezeigt. Wenn die <xref:System.Windows.Forms.ListBox.MultiColumn%2A>-Eigenschaft auf `false`festgelegt ist, werden im Listenfeld Elemente in einer einzelnen Spalte angezeigt, und eine vertikale Schiebe Leiste wird angezeigt. Wenn <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> auf `true`festgelegt ist, wird die Scrollleiste unabhängig von der Anzahl der Elemente angezeigt. Die <xref:System.Windows.Forms.ListBox.SelectionMode%2A>-Eigenschaft bestimmt, wie viele Listenelemente gleichzeitig ausgewählt werden können.  
  
## <a name="ways-to-change-the-listbox-control"></a>Möglichkeiten zum Ändern des ListBox-Steuer Elements  
 Die <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>-Eigenschaft gibt einen ganzzahligen Wert zurück, der dem ersten ausgewählten Element im Listenfeld entspricht. Sie können das ausgewählte Element Programm gesteuert ändern, indem Sie den <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Wert im Code ändern. das entsprechende Element in der Liste wird im Windows Form hervorgehoben angezeigt. Wenn kein Element ausgewählt ist, ist der <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Wert-1. Wenn das erste Element in der Liste ausgewählt ist, ist der <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Wert 0 (null). Wenn mehrere Elemente ausgewählt sind, gibt der <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Wert das ausgewählte Element wieder, das zuerst in der Liste angezeigt wird. Die <xref:System.Windows.Forms.ListBox.SelectedItem%2A>-Eigenschaft ähnelt <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, gibt jedoch in der Regel einen Zeichen folgen Wert zurück. Die <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A>-Eigenschaft gibt die Anzahl der Elemente in der Liste an, und der Wert der <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A>-Eigenschaft ist immer größer als der größtmögliche <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Wert, da <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Null basiert ist.  
  
 Um Elemente in einem <xref:System.Windows.Forms.ListBox>-Steuerelement hinzuzufügen oder zu löschen, verwenden Sie die Methode <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> oder <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A>. Alternativ können Sie der Liste Elemente hinzufügen, indem Sie zur Entwurfszeit die <xref:System.Windows.Forms.ListBox.Items%2A>-Eigenschaft verwenden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListBox>
- [Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Gewusst wie: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Übersicht über das ComboBox-Steuerelement](combobox-control-overview-windows-forms.md)
- [Übersicht über das CheckedListBox-Steuerelement](checkedlistbox-control-overview-windows-forms.md)
- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
- [Gewusst wie: Erstellen einer Suchtabelle für ComboBox-, ListBox- oder CheckedListBox-Steuerelemente in Windows Forms](create-a-lookup-table-for-a-wf-combobox-listbox.md)
