---
title: ComboBox und ListBox
description: Erfahren Sie, wie Sie Windows Forms ComboBox und Windows Forms ListBox verwenden, und erfahren Sie, wie Sie erkennen, wenn eine oder die andere besser für eine Aufgabe geeignet ist.
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
ms.openlocfilehash: ca6ad6bec2dbc30128ea09808af2806687b17a8c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174418"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?
Das <xref:System.Windows.Forms.ComboBox> -Steuerelement und das-Steuerelement <xref:System.Windows.Forms.ListBox> weisen ähnliche Verhalten auf, und in manchen Fällen kann es austauschbar sein. Es gibt jedoch Zeiten, in denen eine oder die andere für eine Aufgabe besser geeignet ist.  
  
 Im Allgemeinen ist ein Kombinations Feld geeignet, wenn eine Liste der vorgeschlagenen Optionen vorliegt, und ein Listenfeld ist geeignet, wenn Sie die Eingabe auf die Liste der Listen beschränken möchten. Ein Kombinations Feld enthält ein Textfeld Feld, sodass die Auswahl nicht in der Liste eingegeben werden kann. Die Ausnahme ist, wenn die- <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> Eigenschaft auf festgelegt ist <xref:System.Windows.Forms.ComboBoxStyle.DropDownList> . In diesem Fall wählt das Steuerelement ein Element aus, wenn Sie seinen ersten Buchstaben eingeben.  
  
 Außerdem sparen Kombinations Felder Platz auf einem Formular. Da die vollständige Liste erst angezeigt wird, wenn der Benutzer auf den Pfeil nach unten klickt, kann ein Kombinations Feld problemlos in einen kleinen Bereich passen, in dem ein Listenfeld nicht passt. Eine Ausnahme ist, wenn die- <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> Eigenschaft auf festgelegt ist <xref:System.Windows.Forms.ComboBoxStyle.Simple> : die vollständige Liste wird angezeigt, und das Kombinations Feld benötigt mehr Platz als ein Listenfeld.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Vorgehensweise: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Steuerelemente in Windows Forms zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
