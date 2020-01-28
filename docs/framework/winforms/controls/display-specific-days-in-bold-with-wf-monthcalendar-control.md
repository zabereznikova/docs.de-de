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
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a>Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms
Das Windows Forms <xref:System.Windows.Forms.MonthCalendar>-Steuerelement kann Tage in fettem Typ anzeigen, entweder als einzelne Datumsangaben oder wiederholt. Dies kann dazu führen, dass besondere Datumsangaben, z. b. Feiertage und Wochenenden, berücksichtigt werden.  
  
 Diese Funktion wird von drei Eigenschaften gesteuert. Die <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>-Eigenschaft enthält einzelne Datumsangaben. Die <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>-Eigenschaft enthält Datumsangaben, die jedes Jahr fett formatiert angezeigt werden. Die <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A>-Eigenschaft enthält Datumsangaben, die jeden Monat fett formatiert angezeigt werden. Jede dieser Eigenschaften enthält ein Array von <xref:System.DateTime>-Objekten. Wenn Sie ein Datum aus einer dieser Listen hinzufügen oder entfernen möchten, müssen Sie ein <xref:System.DateTime> Objekt hinzufügen oder entfernen.  
  
### <a name="to-make-a-date-appear-in-bold-type"></a>So geben Sie ein Datum als fett formatierten Typ an  
  
1. Erstellen Sie die <xref:System.DateTime>-Objekte.  
  
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
  
2. Erstellen Sie ein einzelnes Datum fett, indem Sie die <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>-, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>-oder <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A>-Methode des <xref:System.Windows.Forms.MonthCalendar> Steuer Elements aufrufen.  
  
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
  
     – oder –  
  
     Legen Sie alle Daten auf einmal fett formatiert, indem Sie ein Array von <xref:System.DateTime> Objekten erstellen und es einer der Eigenschaften zuweisen.  
  
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
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a>So geben Sie ein Datum in der regulären Schriftart an  
  
1. Erstellen Sie ein einzelnes fett formatierten Datum in der regulären Schriftart, indem Sie die <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>-, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>-oder <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A>-Methode aufrufen.  
  
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
  
     – oder –  
  
     Entfernen Sie alle fett formatierten Datumsangaben aus einer der drei Listen, indem Sie die <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>-, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>-oder <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A>-Methode aufrufen.  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. Aktualisieren Sie die Darstellung der Schriftart, indem Sie die <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A>-Methode aufrufen.  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [MonthCalendar-Steuerelement](monthcalendar-control-windows-forms.md)
- [Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Gewusst wie: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms](how-to-change-monthcalendar-control-appearance.md)
- [Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms](display-more-than-one-month-wf-monthcalendar-control.md)
