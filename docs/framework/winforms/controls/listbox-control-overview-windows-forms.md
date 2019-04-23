---
title: Übersicht über das ListBox-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: f70246d4a4d158815ee9662036eca8edeb891d85
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104196"
---
# <a name="listbox-control-overview-windows-forms"></a>Übersicht über das ListBox-Steuerelement (Windows Forms)
Ein Windows Forms <xref:System.Windows.Forms.ListBox> -Steuerelement zeigt eine Liste von dem der Benutzer kann ein oder mehrere Elemente auswählen. Überschreitet die Gesamtzahl der Elemente für die Anzahl, die angezeigt werden können, eine Bildlaufleiste wird automatisch hinzugefügt der <xref:System.Windows.Forms.ListBox> Steuerelement. Wenn die <xref:System.Windows.Forms.ListBox.MultiColumn%2A> -Eigenschaftensatz auf `true`, das Listenfeld zeigt Elemente in mehreren Spalten und eine horizontale Bildlaufleiste angezeigt wird. Wenn die <xref:System.Windows.Forms.ListBox.MultiColumn%2A> -Eigenschaftensatz auf `false`, das Listenfeld zeigt Elemente in einer einzelnen Spalte und eine vertikale Bildlaufleiste angezeigt wird. Wenn <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> nastaven NA hodnotu `true`, die scrollleiste angezeigt wird, unabhängig von der Anzahl von Elementen. Die <xref:System.Windows.Forms.ListBox.SelectionMode%2A> Eigenschaft bestimmt, wie viele Elemente gleichzeitig ausgewählt werden können.  
  
## <a name="ways-to-change-the-listbox-control"></a>Möglichkeiten, das ListBox-Steuerelement zu ändern.  
 Die <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Eigenschaft gibt einen ganzzahligen Wert, der auf das erste ausgewählte Element im Listenfeld zurück. Sie können das ausgewählte Element programmgesteuert ändern, durch Ändern der <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Wert im Code; das entsprechende Element in der Liste hervorgehoben ist, auf dem Windows-Formular angezeigt wird. Wenn kein Element ausgewählt ist, die <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Wert ist 1. Wenn das erste Element in der Liste ausgewählt ist, die <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Wert ist 0. Wenn mehrere Elemente ausgewählt sind, die <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Wert entspricht dem ausgewählten Element, das zuerst in der Liste angezeigt wird. Die <xref:System.Windows.Forms.ListBox.SelectedItem%2A> Eigenschaft ähnelt <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, aber gibt das Element selbst, in der Regel einen Zeichenfolgenwert zurück. Die <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> Eigenschaft spiegelt wider, die Anzahl der Elemente in der Liste, und der Wert des der <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> Eigenschaft ist immer einer mehr als der größtmögliche <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> bewertet werden, da <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> ist nullbasiert.  
  
 Hinzufügen oder Löschen von Elementen in einem <xref:System.Windows.Forms.ListBox> steuern, verwenden Sie die <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> oder <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> Methode. Sie können auch Elemente der Liste hinzufügen, mit der <xref:System.Windows.Forms.ListBox.Items%2A> Eigenschaft zur Entwurfszeit.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListBox>
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen aus einer Windows Forms, ComboBox-, ListBox- oder CheckedListBox-Steuerelement](add-and-remove-items-from-a-wf-combobox.md)
- [Vorgehensweise: Sortieren des Inhalts einer Windows Forms-ComboBox-, ListBox- oder CheckedListBox-Steuerelement](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Vorgehensweise: Binden eines Windows Forms-Kombinationsfeld oder das ListBox-Steuerelement an Daten](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Übersicht über das ComboBox-Steuerelement](combobox-control-overview-windows-forms.md)
- [Übersicht über das CheckedListBox-Steuerelement](checkedlistbox-control-overview-windows-forms.md)
- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
- [Vorgehensweise: Erstellen einer Nachschlagetabelle für eine Windows-ComboBox-, ListBox- oder CheckedListBox-Steuerelement Forms](create-a-lookup-table-for-a-wf-combobox-listbox.md)
