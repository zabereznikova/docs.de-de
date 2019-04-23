---
title: 'Vorgehensweise: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], selecting range in calendar controls
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], selecting date range
- MonthCalendar control [Windows Forms], selecting date range
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
ms.openlocfilehash: 82d0499cb40f79a3110b8432fbee66774bcc14a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332234"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="d5c6e-102">Vorgehensweise: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5c6e-102">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="d5c6e-103">Eine wichtige Funktion von der Windows Forms <xref:System.Windows.Forms.MonthCalendar> Steuerelement ist, dass der Benutzer einen Bereich von Datumswerten auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-103">An important feature of the Windows Forms <xref:System.Windows.Forms.MonthCalendar> control is that the user can select a range of dates.</span></span> <span data-ttu-id="d5c6e-104">Diese Funktion ist eine Verbesserung gegenüber der Auswahl des dem <xref:System.Windows.Forms.DateTimePicker> -Steuerelement, das nur der Benutzer einen einzelnes Datum/Uhrzeit-Wert auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-104">This feature is an improvement over the date-selection feature of the <xref:System.Windows.Forms.DateTimePicker> control, which only enables the user to select a single date/time value.</span></span> <span data-ttu-id="d5c6e-105">Sie können einen Datumsbereich festlegen oder einen Auswahlbereich, die vom Benutzer festgelegt werden, mithilfe von Eigenschaften zu erhalten die <xref:System.Windows.Forms.MonthCalendar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-105">You can set a range of dates or get a selection range set by the user by using properties of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span> <span data-ttu-id="d5c6e-106">Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Auswahlbereich festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-106">The following code example demonstrates how to set a selection range.</span></span>  
  
### <a name="to-select-a-range-of-dates"></a><span data-ttu-id="d5c6e-107">Um einen Datumsbereich auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-107">To select a range of dates</span></span>  
  
1. <span data-ttu-id="d5c6e-108">Erstellen Sie <xref:System.DateTime> Objekte, die das erste und letzte Datum in einem Bereich darstellen.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-108">Create <xref:System.DateTime> objects that represent the first and last dates in a range.</span></span>  
  
    ```vb  
    Dim projectStart As Date = New DateTime(2001, 2, 13)  
    Dim projectEnd As Date = New DateTime(2001, 2, 28)  
    ```  
  
    ```csharp  
    DateTime projectStart = new DateTime(2001, 2, 13);  
    DateTime projectEnd = new DateTime(2001, 2, 28);  
    ```  
  
    ```cpp  
    DateTime projectStart = DateTime(2001, 2, 13);  
    DateTime projectEnd = DateTime(2001, 2, 28);  
    ```  
  
2. <span data-ttu-id="d5c6e-109">Legen Sie die <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-109">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> property.</span></span>  
  
    ```vb  
    MonthCalendar1.SelectionRange = New SelectionRange(projectStart, projectEnd)  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionRange = new SelectionRange(projectStart, projectEnd);  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionRange = gcnew  
       SelectionRange(projectStart, projectEnd);  
    ```  
  
     <span data-ttu-id="d5c6e-110">– oder –</span><span class="sxs-lookup"><span data-stu-id="d5c6e-110">–or–</span></span>  
  
     <span data-ttu-id="d5c6e-111">Legen Sie für die Eigenschaften <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> und <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="d5c6e-111">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> and <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> properties.</span></span>  
  
    ```vb  
    MonthCalendar1.SelectionStart = projectStart  
    MonthCalendar1.SelectionEnd = projectEnd  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionStart = projectStart;  
    monthCalendar1.SelectionEnd = projectEnd;  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionStart = projectStart;  
    monthCalendar1->SelectionEnd = projectEnd;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d5c6e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5c6e-112">See also</span></span>

- [<span data-ttu-id="d5c6e-113">MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d5c6e-113">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="d5c6e-114">Vorgehensweise: Ändern Sie die Windows Forms MonthCalendar Darstellung des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="d5c6e-114">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="d5c6e-115">Vorgehensweise: Anzeige bestimmte Tage im mit der Windows Bold Forms-MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d5c6e-115">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="d5c6e-116">Vorgehensweise: Anzeigen von mehr als einen Monat in der Windows Forms-MonthCalendar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d5c6e-116">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
