---
title: Zugreifen auf bestimmte Elemente in der ComboBox-, ListBox-oder CheckedListBox-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ComboBox control [Windows Forms], accessing items
- ListBox control [Windows Forms], returning item information
- list boxes [Windows Forms], accessing items
- ListBox control [Windows Forms], accessing items
- combo boxes [Windows Forms], accessing items
- CheckedListBox control [Windows Forms], accessing items
ms.assetid: 1216742f-bcf9-4ff8-8a62-d7c9053c2b96
ms.openlocfilehash: 67673ec7f136f1466d4fd091e691324c53e7de06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746327"
---
# <a name="how-to-access-specific-items-in-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Gewusst wie: Zugreifen auf spezifische Elemente in ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms
Der Zugriff auf bestimmte Elemente in einem Kombinations Feld (Windows Forms), einem Listenfeld oder einem aktivierten Listenfeld ist eine wesentliche Aufgabe. Mit dieser Option können Sie Programm gesteuert ermitteln, was in einer Liste an einer beliebigen Position vorhanden ist.  
  
### <a name="to-access-a-specific-item"></a>So greifen Sie auf ein bestimmtes Element zu  
  
1. Abfragen der `Items` Auflistung mit dem Index des jeweiligen Elements:  
  
    ```vb  
    Private Function GetItemText(i As Integer) As String  
       ' Return the text of the item using the index:  
       Return ComboBox1.Items(i).ToString  
    End Function  
    ```  
  
    ```csharp  
    private string GetItemText(int i)  
    {  
       // Return the text of the item using the index:  
       return (comboBox1.Items[i].ToString());  
    }  
    ```  
  
    ```cpp  
    private:  
       String^ GetItemText(int i)  
       {  
          // Return the text of the item using the index:  
          return (comboBox1->Items->Item[i]->ToString());  
       }  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
