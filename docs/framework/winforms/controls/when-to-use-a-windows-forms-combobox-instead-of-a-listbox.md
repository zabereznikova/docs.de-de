---
title: ComboBox und ListBox
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: 7087760a393bb58d83d899c1741c745fb28585bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739925"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?
Die <xref:System.Windows.Forms.ComboBox>-und die <xref:System.Windows.Forms.ListBox>-Steuerelemente weisen ein ähnliches Verhalten auf, und in manchen Fällen ist es möglicherweise austauschbar. Es gibt jedoch Zeiten, in denen eine oder die andere für eine Aufgabe besser geeignet ist.  
  
 Im Allgemeinen ist ein Kombinations Feld geeignet, wenn eine Liste der vorgeschlagenen Optionen vorliegt, und ein Listenfeld ist geeignet, wenn Sie die Eingabe auf die Liste der Listen beschränken möchten. Ein Kombinations Feld enthält ein Textfeld Feld, sodass die Auswahl nicht in der Liste eingegeben werden kann. Die Ausnahme ist, wenn die <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A>-Eigenschaft auf <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>festgelegt ist. In diesem Fall wählt das Steuerelement ein Element aus, wenn Sie seinen ersten Buchstaben eingeben.  
  
 Außerdem sparen Kombinations Felder Platz auf einem Formular. Da die vollständige Liste erst angezeigt wird, wenn der Benutzer auf den Pfeil nach unten klickt, kann ein Kombinations Feld problemlos in einen kleinen Bereich passen, in dem ein Listenfeld nicht passt. Eine Ausnahme ist, wenn die <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A>-Eigenschaft auf <xref:System.Windows.Forms.ComboBoxStyle.Simple>festgelegt ist: die vollständige Liste wird angezeigt, und das Kombinations Feld benötigt mehr Platz als ein Listenfeld.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
