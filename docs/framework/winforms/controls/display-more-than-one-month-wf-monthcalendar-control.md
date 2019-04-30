---
title: 'Vorgehensweise: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 79100b52d8e0a5b651edb9d6555a4497287ed858
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972140"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>Vorgehensweise: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.MonthCalendar> Steuerelement kann bis zu 12 Monate lang zu einem Zeitpunkt anzeigen. Wird standardmäßig das Steuerelement zeigt nur einen Monat, aber Sie können angeben, wie viele Monate angezeigt werden und wie sie innerhalb des Steuerelements angeordnet sind. Wenn Sie die Größe des Kalenders ändern, die Größe des Steuerelements wird geändert, daher sicher, dass genügend Speicherplatz vorhanden ist, auf dem Formular für die neuen Dimension.  
  
### <a name="to-display-multiple-months"></a>Um mehrere Monate anzuzeigen.  
  
- Legen Sie die <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> Eigenschaft, um die Anzahl der Monate horizontal und vertikal angezeigt.  
  
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

- [MonthCalendar-Steuerelement](monthcalendar-control-windows-forms.md)
- [Vorgehensweise: Auswählen eines Datumsbereichs in das Windows Forms-MonthCalendar-Steuerelement](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Vorgehensweise: Ändern Sie die Windows Forms MonthCalendar Darstellung des Steuerelements](how-to-change-monthcalendar-control-appearance.md)
