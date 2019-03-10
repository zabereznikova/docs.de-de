---
title: 'Vorgehensweise: Sortieren des Inhalts einer Windows Forms-ComboBox-, ListBox- oder CheckedListBox-Steuerelement'
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: 4c00e853299c6eea2c97adb7f94cd7753ffa3d93
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705263"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Vorgehensweise: Sortieren des Inhalts einer Windows Forms-ComboBox-, ListBox- oder CheckedListBox-Steuerelement
Windows Forms-Steuerelemente werden nicht sortiert werden, wenn sie die Daten gebunden werden. Um sortierte Daten anzuzeigen, verwenden Sie eine Datenquelle, die das Sortieren unterstützt, und lassen Sie dann die Datenquelle sortiert das System. Datenquellen, die das Sortieren unterstützt, sind Ansichten, Data Manager anzuzeigen, und sortiert Sie Arrays.  
  
 Wenn das Steuerelement nicht datengebunden ist, können Sie sie sortieren.  
  
### <a name="to-sort-the-list"></a>Um die Liste sortieren  
  
1.  Legen Sie die `Sorted` -Eigenschaft auf `true`fest.  
  
     Diese Einstellung automatisch neu positioniert und alle vorhandenen Auflisten von Elementen in sortierter Reihenfolge.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Windows Forms-Datenbindung](../windows-forms-data-binding.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen aus einer Windows Forms, ComboBox-, ListBox- oder CheckedListBox-Steuerelement](add-and-remove-items-from-a-wf-combobox.md)
- [Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
