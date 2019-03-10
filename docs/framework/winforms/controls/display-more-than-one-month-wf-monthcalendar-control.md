---
title: 'Vorgehensweise: Anzeigen von mehr als einen Monat in der Windows Forms-MonthCalendar-Steuerelement'
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
ms.openlocfilehash: febed820bae460f51bb19f08caa6027011abd55d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715346"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>Vorgehensweise: Anzeigen von mehr als einen Monat in der Windows Forms-MonthCalendar-Steuerelement
Die Windows-Formulare <xref:System.Windows.Forms.MonthCalendar> Steuerelement kann bis zu 12 Monate lang zu einem Zeitpunkt anzeigen. Wird standardmäßig das Steuerelement zeigt nur einen Monat, aber Sie können angeben, wie viele Monate angezeigt werden und wie sie innerhalb des Steuerelements angeordnet sind. Wenn Sie die Größe des Kalenders ändern, die Größe des Steuerelements wird geändert, daher sicher, dass genügend Speicherplatz vorhanden ist, auf dem Formular für die neuen Dimension.  
  
### <a name="to-display-multiple-months"></a>Um mehrere Monate anzuzeigen.  
  
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
- [MonthCalendar-Steuerelement](monthcalendar-control-windows-forms.md)
- [Vorgehensweise: Auswählen eines Datumsbereichs in das Windows Forms-MonthCalendar-Steuerelement](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Vorgehensweise: Ändern Sie die Windows Forms MonthCalendar Darstellung des Steuerelements](how-to-change-monthcalendar-control-appearance.md)
