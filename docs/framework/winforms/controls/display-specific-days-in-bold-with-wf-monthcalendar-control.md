---
title: Anzeigen bestimmter Tage in Fett Schrift mit dem MonthCalendar-Steuerelement
ms.date: 03/30/2017
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
ms.openlocfilehash: 377eb76f562fff20aae2136ddb7130516d2d76f7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745880"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="220bc-102">Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="220bc-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="220bc-103">Das Windows Forms <xref:System.Windows.Forms.MonthCalendar>-Steuerelement kann Tage in fettem Typ anzeigen, entweder als einzelne Datumsangaben oder wiederholt.</span><span class="sxs-lookup"><span data-stu-id="220bc-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="220bc-104">Dies kann dazu führen, dass besondere Datumsangaben, z. b. Feiertage und Wochenenden, berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="220bc-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="220bc-105">Diese Funktion wird von drei Eigenschaften gesteuert.</span><span class="sxs-lookup"><span data-stu-id="220bc-105">Three properties control this feature.</span></span> <span data-ttu-id="220bc-106">Die <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>-Eigenschaft enthält einzelne Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="220bc-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="220bc-107">Die <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>-Eigenschaft enthält Datumsangaben, die jedes Jahr fett formatiert angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="220bc-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="220bc-108">Die <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A>-Eigenschaft enthält Datumsangaben, die jeden Monat fett formatiert angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="220bc-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="220bc-109">Jede dieser Eigenschaften enthält ein Array von <xref:System.DateTime>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="220bc-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="220bc-110">Wenn Sie ein Datum aus einer dieser Listen hinzufügen oder entfernen möchten, müssen Sie ein <xref:System.DateTime> Objekt hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="220bc-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="220bc-111">So geben Sie ein Datum als fett formatierten Typ an</span><span class="sxs-lookup"><span data-stu-id="220bc-111">To make a date appear in bold type</span></span>  
  
1. <span data-ttu-id="220bc-112">Erstellen Sie die <xref:System.DateTime>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="220bc-112">Create the <xref:System.DateTime> objects.</span></span>  
  
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
  
2. <span data-ttu-id="220bc-113">Erstellen Sie ein einzelnes Datum fett, indem Sie die <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>-, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>-oder <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A>-Methode des <xref:System.Windows.Forms.MonthCalendar> Steuer Elements aufrufen.</span><span class="sxs-lookup"><span data-stu-id="220bc-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
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
  
     <span data-ttu-id="220bc-114">– oder –</span><span class="sxs-lookup"><span data-stu-id="220bc-114">–or–</span></span>  
  
     <span data-ttu-id="220bc-115">Legen Sie alle Daten auf einmal fett formatiert, indem Sie ein Array von <xref:System.DateTime> Objekten erstellen und es einer der Eigenschaften zuweisen.</span><span class="sxs-lookup"><span data-stu-id="220bc-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
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
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="220bc-116">So geben Sie ein Datum in der regulären Schriftart an</span><span class="sxs-lookup"><span data-stu-id="220bc-116">To make a date appear in the regular font</span></span>  
  
1. <span data-ttu-id="220bc-117">Erstellen Sie ein einzelnes fett formatierten Datum in der regulären Schriftart, indem Sie die <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>-, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>-oder <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="220bc-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
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
  
     <span data-ttu-id="220bc-118">– oder –</span><span class="sxs-lookup"><span data-stu-id="220bc-118">–or–</span></span>  
  
     <span data-ttu-id="220bc-119">Entfernen Sie alle fett formatierten Datumsangaben aus einer der drei Listen, indem Sie die <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>-, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>-oder <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="220bc-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. <span data-ttu-id="220bc-120">Aktualisieren Sie die Darstellung der Schriftart, indem Sie die <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="220bc-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="220bc-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="220bc-121">See also</span></span>

- [<span data-ttu-id="220bc-122">MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="220bc-122">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="220bc-123">Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="220bc-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="220bc-124">Gewusst wie: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="220bc-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="220bc-125">Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="220bc-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
