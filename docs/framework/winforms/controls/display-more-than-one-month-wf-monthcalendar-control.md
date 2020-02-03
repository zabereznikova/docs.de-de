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
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="c20c6-102">Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c20c6-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="c20c6-103">Die Windows Forms <xref:System.Windows.Forms.MonthCalendar>-Steuerelement kann bis zu 12 Monate lang angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c20c6-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="c20c6-104">Standardmäßig zeigt das Steuerelement nur einen Monat an, Sie können jedoch angeben, wie viele Monate angezeigt werden und wie diese im Steuerelement angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c20c6-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="c20c6-105">Wenn Sie die Kalender Dimensionen ändern, ändert sich die Größe des Steuer Elements. Stellen Sie also sicher, dass genügend Platz auf dem Formular für die neuen Dimensionen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c20c6-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="c20c6-106">So zeigen Sie mehrere Monate an</span><span class="sxs-lookup"><span data-stu-id="c20c6-106">To display multiple months</span></span>  
  
- <span data-ttu-id="c20c6-107">Legen Sie die <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>-Eigenschaft auf die Anzahl von Monaten fest, die horizontal und vertikal angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c20c6-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c20c6-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c20c6-108">See also</span></span>

- [<span data-ttu-id="c20c6-109">MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c20c6-109">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="c20c6-110">Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c20c6-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="c20c6-111">Gewusst wie: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c20c6-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
