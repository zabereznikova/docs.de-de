---
title: "Übersicht über das ListBox-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0eadf9db9a952fdabe77100cb31501be1970e74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="listbox-control-overview-windows-forms"></a>Übersicht über das ListBox-Steuerelement (Windows Forms)
Eine Windows Forms <xref:System.Windows.Forms.ListBox> -Steuerelement zeigt eine Liste, in dem der Benutzer ein oder mehrere Elemente auswählen kann. Wenn die Gesamtanzahl der Elemente die Anzahl, die angezeigt werden können übersteigt, eine Bildlaufleiste angezeigt wird automatisch hinzugefügt der <xref:System.Windows.Forms.ListBox> Steuerelement. Wenn die <xref:System.Windows.Forms.ListBox.MultiColumn%2A> -Eigenschaftensatz auf `true`, das Listenfeld zeigt die Elemente in mehreren Spalten und eine horizontale Bildlaufleiste angezeigt wird. Wenn die <xref:System.Windows.Forms.ListBox.MultiColumn%2A> -Eigenschaftensatz auf `false`, das Listenfeld zeigt die Elemente in einer einzelnen Spalte und eine vertikale Bildlaufleiste angezeigt wird. Wenn <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> festgelegt ist, um `true`, die Bildlaufleiste angezeigt wird, unabhängig von der Anzahl von Elementen. Die <xref:System.Windows.Forms.ListBox.SelectionMode%2A> Eigenschaft bestimmt, wie viele Elemente gleichzeitig ausgewählt werden können.  
  
## <a name="ways-to-change-the-listbox-control"></a>Methoden zum Ändern der ListBox-Steuerelement  
 Die <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Eigenschaft gibt einen ganzzahligen Wert, der auf das erste ausgewählte Element im Listenfeld. Sie können das ausgewählte Element programmgesteuert ändern, durch Ändern der <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> im Code-Wert; das entsprechende Element in der Liste hervorgehoben ist, auf dem Windows Form angezeigt wird. Wenn kein Element ausgewählt ist, die <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Wert ist 1. Wenn das erste Element in der Liste ausgewählt ist, die <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Wert ist 0. Wenn mehrere Elemente ausgewählt sind, die <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Wert entspricht dem ausgewählten Element, das in der Liste an erster Stelle steht. Die <xref:System.Windows.Forms.ListBox.SelectedItem%2A> Eigenschaft ähnelt <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, aber gibt das Element selbst, in der Regel einen Zeichenfolgenwert zurück. Die <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> Eigenschaft zeigt die Anzahl der Elemente in der Liste, und der Wert von der <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> Eigenschaft ist immer eine mehr als der größtmögliche <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> bewertet werden, da <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> ist nullbasiert.  
  
 Hinzufügen oder Löschen von Elementen in einem <xref:System.Windows.Forms.ListBox> steuern, verwenden Sie die <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> oder <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> Methode. Sie können auch Elemente zur Liste hinzufügen, mit der <xref:System.Windows.Forms.ListBox.Items%2A> Eigenschaft zur Entwurfszeit.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ListBox>  
 [Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [Gewusst wie: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [Übersicht über das ComboBox-Steuerelement](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [Übersicht über das CheckedListBox-Steuerelement](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [Windows Forms-Steuerelemente zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [Gewusst wie: Erstellen einer Suchtabelle für ComboBox-, ListBox- oder CheckedListBox-Steuerelemente in Windows Forms](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)
