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
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="71983-102">Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71983-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="71983-103">Windows Forms <xref:System.Windows.Forms.MonthCalendar> -Steuerelement kann bis zu 12 Monaten zu einem Zeitpunkt anzeigen.</span><span class="sxs-lookup"><span data-stu-id="71983-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="71983-104">Wird standardmäßig das Steuerelement zeigt nur einen Monat, aber Sie können angeben, wie viele Monate angezeigt werden und wie sie innerhalb des Steuerelements angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="71983-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="71983-105">Wenn Sie die Größe des Kalenders ändern, wird das Steuerelement angepasst, seien Sie sicher, dass genügend Speicherplatz auf dem Formular für die neuen Dimensionen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="71983-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="71983-106">Mehrere Monate angezeigt.</span><span class="sxs-lookup"><span data-stu-id="71983-106">To display multiple months</span></span>  
  
-   <span data-ttu-id="71983-107">Legen Sie die <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> Eigenschaft, um die Anzahl der Monate horizontal und vertikal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="71983-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="71983-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71983-108">See Also</span></span>  
 [<span data-ttu-id="71983-109">MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="71983-109">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [<span data-ttu-id="71983-110">Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71983-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [<span data-ttu-id="71983-111">Gewusst wie: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71983-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
