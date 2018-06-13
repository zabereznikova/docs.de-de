---
title: 'Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], formatting display
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], multiple months
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d197caa2-38a5-4cb4-acc3-562130c2ace3
ms.openlocfilehash: a71f85af2d51faf37160aba7fa89a8421b4523d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524872"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms
Windows Forms <xref:System.Windows.Forms.MonthCalendar> -Steuerelement kann bis zu 12 Monaten zu einem Zeitpunkt anzeigen. Wird standardmäßig das Steuerelement zeigt nur einen Monat, aber Sie können angeben, wie viele Monate angezeigt werden und wie sie innerhalb des Steuerelements angeordnet sind. Wenn Sie die Größe des Kalenders ändern, wird das Steuerelement angepasst, seien Sie sicher, dass genügend Speicherplatz auf dem Formular für die neuen Dimensionen vorhanden ist.  
  
### <a name="to-display-multiple-months"></a>Mehrere Monate angezeigt.  
  
-   Legen Sie die <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> Eigenschaft, um die Anzahl der Monate horizontal und vertikal angezeigt.  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [MonthCalendar-Steuerelement](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [Gewusst wie: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
