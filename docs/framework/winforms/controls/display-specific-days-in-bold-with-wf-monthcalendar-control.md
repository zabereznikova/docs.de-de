---
title: 'Vorgehensweise: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 27b19e47d108b9af43a6d8882264d62c726ffe56
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343264"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a>Vorgehensweise: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.MonthCalendar> Steuerelement kann Tage in Fettschrift, anzeigen, entweder als einzelne Datumsangaben oder einer wiederholten Basis. Diese Option, um die Aufmerksamkeit auf spezielle Datumsangaben, z. B. Feiertage und für Wochenenden empfiehlt sich.  
  
 Drei Eigenschaften steuern, diese Funktion. Die <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> Eigenschaft enthält die einzelne Datumsangaben. Die <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> Eigenschaft enthält die Datumsangaben, die jedes Jahr fett formatiert sein. Die <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> Eigenschaft enthält die Datumsangaben, die jeden Monat fett formatiert sein. Jede dieser Eigenschaften enthält ein Array von <xref:System.DateTime> Objekte. Zum Hinzufügen oder entfernen ein Datum aus diesen Listen, müssen Sie hinzufügen oder Entfernen einer <xref:System.DateTime> Objekt.  
  
### <a name="to-make-a-date-appear-in-bold-type"></a>Um ein Datum in Fettschrift anzeigen  
  
1. Erstellen der <xref:System.DateTime> Objekte.  
  
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
  
2. Ein einzelnes Datum fett formatieren, durch den Aufruf der <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, oder <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> Methode der <xref:System.Windows.Forms.MonthCalendar> Steuerelement.  
  
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
  
     Formatieren Sie einen Satz mit Datumsangaben fett gleichzeitig durch Erstellen eines Arrays von <xref:System.DateTime> Objekte und auf eine der Eigenschaften zuweisen.  
  
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
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a>Um ein Datum in normaler Schrift anzeigen  
  
1. Stellen Sie ein einzelnes fett formatiertes Datum in normaler Schrift angezeigt werden, durch den Aufruf der <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, oder <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> Methode.  
  
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
  
     Entfernen Sie alle fett formatierten Datumsangaben aus einem der drei Listen durch Aufrufen der <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, oder <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> Methode.  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. Aktualisieren Sie die Darstellung der Schriftart durch Aufrufen der <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> Methode.  
  
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
- [Vorgehensweise: Auswählen eines Datumsbereichs in das Windows Forms-MonthCalendar-Steuerelement](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Vorgehensweise: Ändern Sie die Windows Forms MonthCalendar Darstellung des Steuerelements](how-to-change-monthcalendar-control-appearance.md)
- [Vorgehensweise: Anzeigen von mehr als einen Monat in der Windows Forms-MonthCalendar-Steuerelement](display-more-than-one-month-wf-monthcalendar-control.md)
