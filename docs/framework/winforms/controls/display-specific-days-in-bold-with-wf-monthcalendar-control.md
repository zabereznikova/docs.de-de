---
title: "Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], displaying dates in bold
- examples [Windows Forms], calendar controls
- GetDayBold event
- MonthCalendar control [Windows Forms], dates displayed in bold
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 141d943c4f4dfc3976e66e13e7c0975aba3f1687
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="a05ff-102">Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a05ff-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="a05ff-103">Windows Forms <xref:System.Windows.Forms.MonthCalendar> -Steuerelement kann Tage in Fettschrift, anzeigen, als singular Datumsangaben oder wiederholte regelmäßig.</span><span class="sxs-lookup"><span data-stu-id="a05ff-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="a05ff-104">Sie können diese Option, um die Aufmerksamkeit auf spezielle Datumsangaben, z. B. Feiertage und Wochenenden zu lenken vornehmen.</span><span class="sxs-lookup"><span data-stu-id="a05ff-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="a05ff-105">Drei Eigenschaften steuern, diese Funktion.</span><span class="sxs-lookup"><span data-stu-id="a05ff-105">Three properties control this feature.</span></span> <span data-ttu-id="a05ff-106">Die <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> -Eigenschaft enthält einzelne Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="a05ff-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="a05ff-107">Die <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> Eigenschaft enthält die Datumsangaben, die jedes Jahr fett formatiert sein.</span><span class="sxs-lookup"><span data-stu-id="a05ff-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="a05ff-108">Die <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> Eigenschaft enthält die Datumsangaben, die jeden Monat fett formatiert sein.</span><span class="sxs-lookup"><span data-stu-id="a05ff-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="a05ff-109">Jede dieser Eigenschaften enthält ein Array von <xref:System.DateTime> Objekte.</span><span class="sxs-lookup"><span data-stu-id="a05ff-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="a05ff-110">Zum Hinzufügen oder entfernen Sie ein Datum aus einer dieser Listen, müssen Sie hinzufügen oder Entfernen einer <xref:System.DateTime> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a05ff-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="a05ff-111">Ein Datum in Fettschrift angezeigt werden soll</span><span class="sxs-lookup"><span data-stu-id="a05ff-111">To make a date appear in bold type</span></span>  
  
1.  <span data-ttu-id="a05ff-112">Erstellen der <xref:System.DateTime> Objekte.</span><span class="sxs-lookup"><span data-stu-id="a05ff-112">Create the <xref:System.DateTime> objects.</span></span>  
  
    ```vb  
    Dim myVacation1 As Date = New DateTime(2001, 6, 10)  
    Dim myVacation2 As Date = New DateTime(2001, 6, 17)  
    ```  
  
    ```csharp  
    DateTime myVacation1 = new DateTime(2001, 6, 10);  
    DateTime myVacation2 = new DateTime(2001, 6, 17);  
    ```  
  
    ```cpp  
    DateTime myVacation1 = DateTime(2001, 6, 10);  
    DateTime myVacation2 = DateTime(2001, 6, 17);  
    ```  
  
2.  <span data-ttu-id="a05ff-113">Ein einzelnes Datum fett durch Aufrufen der <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, oder <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> Methode der <xref:System.Windows.Forms.MonthCalendar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a05ff-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
    ```vb  
    MonthCalendar1.AddBoldedDate(myVacation1)  
    MonthCalendar1.AddBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.AddBoldedDate(myVacation1);  
    monthCalendar1.AddBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->AddBoldedDate(myVacation1);  
    monthCalendar1->AddBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="a05ff-114">– oder –</span><span class="sxs-lookup"><span data-stu-id="a05ff-114">–or–</span></span>  
  
     <span data-ttu-id="a05ff-115">Formatieren Sie einen Satz mit Datumsangaben fett alle auf einmal durch Erstellen eines Arrays von <xref:System.DateTime> Objekte und eine der Eigenschaften zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a05ff-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
    ```vb  
    Dim VacationDates As DateTime() = {myVacation1, myVacation2}  
    MonthCalendar1.BoldedDates = VacationDates  
    ```  
  
    ```csharp  
    DateTime[] VacationDates = {myVacation1, myVacation2};  
    monthCalendar1.BoldedDates = VacationDates;  
    ```  
  
    ```cpp  
    Array<DateTime>^ VacationDates = {myVacation1, myVacation2};  
    monthCalendar1->BoldedDates = VacationDates;  
    ```  
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="a05ff-116">Ein Datum in normaler Schrift angezeigt werden soll</span><span class="sxs-lookup"><span data-stu-id="a05ff-116">To make a date appear in the regular font</span></span>  
  
1.  <span data-ttu-id="a05ff-117">Stellen Sie ein einzelnes fett formatiertes Datum in normaler Schrift angezeigt werden, durch den Aufruf der <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, oder <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="a05ff-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveBoldedDate(myVacation1)  
    MonthCalendar1.RemoveBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveBoldedDate(myVacation1);  
    monthCalendar1.RemoveBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveBoldedDate(myVacation1);  
    monthCalendar1->RemoveBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="a05ff-118">– oder –</span><span class="sxs-lookup"><span data-stu-id="a05ff-118">–or–</span></span>  
  
     <span data-ttu-id="a05ff-119">Entfernen Sie alle fett formatierten Datumsangaben aus einer der drei Listen durch Aufrufen der <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, oder <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="a05ff-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2.  <span data-ttu-id="a05ff-120">Aktualisieren Sie die Darstellung der Schriftart durch Aufrufen der <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="a05ff-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a05ff-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a05ff-121">See Also</span></span>  
 [<span data-ttu-id="a05ff-122">MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a05ff-122">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [<span data-ttu-id="a05ff-123">Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a05ff-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [<span data-ttu-id="a05ff-124">Gewusst wie: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a05ff-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)  
 [<span data-ttu-id="a05ff-125">Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a05ff-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
