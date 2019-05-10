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
ms.openlocfilehash: c2252ccf1c8fec0dcaba634e6da093ab976ce1f6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614765"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="d4ef2-102">Vorgehensweise: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4ef2-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="d4ef2-103">Die Windows-Formulare <xref:System.Windows.Forms.MonthCalendar> Steuerelement kann bis zu 12 Monate lang zu einem Zeitpunkt anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="d4ef2-104">Wird standardmäßig das Steuerelement zeigt nur einen Monat, aber Sie können angeben, wie viele Monate angezeigt werden und wie sie innerhalb des Steuerelements angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="d4ef2-105">Wenn Sie die Größe des Kalenders ändern, die Größe des Steuerelements wird geändert, daher sicher, dass genügend Speicherplatz vorhanden ist, auf dem Formular für die neuen Dimension.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="d4ef2-106">Um mehrere Monate anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-106">To display multiple months</span></span>  
  
- <span data-ttu-id="d4ef2-107">Legen Sie die <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> Eigenschaft, um die Anzahl der Monate horizontal und vertikal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d4ef2-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4ef2-108">See also</span></span>

- [<span data-ttu-id="d4ef2-109">MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d4ef2-109">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="d4ef2-110">Vorgehensweise: Auswählen eines Datumsbereichs in das Windows Forms-MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d4ef2-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="d4ef2-111">Vorgehensweise: Ändern Sie die Windows Forms MonthCalendar Darstellung des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="d4ef2-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
