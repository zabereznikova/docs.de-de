---
title: Mehr als einen Monat im MonthCalendar-Steuerelement anzeigen
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
ms.openlocfilehash: 5d3925bc19ddcd67742f0ab8b5b2e45530820f38
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745903"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms
Die Windows Forms <xref:System.Windows.Forms.MonthCalendar>-Steuerelement kann bis zu 12 Monate lang angezeigt werden. Standardmäßig zeigt das Steuerelement nur einen Monat an, Sie können jedoch angeben, wie viele Monate angezeigt werden und wie diese im Steuerelement angeordnet sind. Wenn Sie die Kalender Dimensionen ändern, ändert sich die Größe des Steuer Elements. Stellen Sie also sicher, dass genügend Platz auf dem Formular für die neuen Dimensionen vorhanden ist.  
  
### <a name="to-display-multiple-months"></a>So zeigen Sie mehrere Monate an  
  
- Legen Sie die <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>-Eigenschaft auf die Anzahl von Monaten fest, die horizontal und vertikal angezeigt werden soll.  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [MonthCalendar-Steuerelement](monthcalendar-control-windows-forms.md)
- [Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Gewusst wie: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms](how-to-change-monthcalendar-control-appearance.md)
