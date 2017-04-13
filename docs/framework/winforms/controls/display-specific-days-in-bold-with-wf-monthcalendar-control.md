---
title: "Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kalender, Anzeigen von Daten in Fettschrift"
  - "Beispiele [Windows Forms], Calendar-Steuerelemente"
  - "GetDayBold-Ereignis"
  - "MonthCalendar-Steuerelement [Windows Forms], Datumsangaben fett angezeigt"
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows&#160;Forms
Mit dem <xref:System.Windows.Forms.MonthCalendar>\-Steuerelement von Windows Forms können Tage in Fettschrift angezeigt werden, und zwar als einzelnes Datum oder wiederholend.  Auf diese Weise können Sie bestimmte Datumsangaben wie Feiertage und Wochenenden hervorheben.  
  
 Dieses Feature basiert auf drei Eigenschaften.  Die <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>\-Eigenschaft enthält einzelne Datumsangaben.  Die <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>\-Eigenschaft enthält Datumsangaben, die jedes Jahr in Fettschrift angezeigt werden.  Die <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A>\-Eigenschaft enthält Datumsangaben, die jeden Monat in Fettschrift angezeigt werden.  Jede dieser Eigenschaften enthält ein Array von <xref:System.DateTime>\-Objekten.  Um diesen Listen ein Datum hinzuzufügen bzw. ein Datum daraus zu entfernen, müssen Sie ein <xref:System.DateTime>\-Objekt hinzufügen bzw. entfernen.  
  
### So lassen Sie ein Datum in Fettschrift anzeigen  
  
1.  Erstellen Sie die <xref:System.DateTime>\-Objekte.  
  
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
  
2.  Formatieren Sie ein einzelnes Datum fett, indem Sie die Methode <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A> oder <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> des <xref:System.Windows.Forms.MonthCalendar>\-Steuerelements aufrufen.  
  
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
  
     – oder –  
  
     Erstellen Sie ein Array von <xref:System.DateTime>\-Objekten, und weisen Sie es einer der Eigenschaften zu, um mehrere Datumsangaben in Fettschrift anzuzeigen.  
  
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
  
### So lassen Sie ein Datum in normaler Schrift anzeigen  
  
1.  Lassen Sie ein einzelnes fett formatiertes Datum in normaler Schrift anzeigen, indem Sie die Methode <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A> oder <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> aufrufen.  
  
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
  
     – oder –  
  
     Entfernen Sie alle fett formatierten Datumsangaben aus einer der drei Listen, indem Sie die Methode <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A> oder <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> aufrufen.  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2.  Aktualisieren Sie die Darstellung der Schriftart, indem Sie die <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A>\-Methode aufrufen.  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## Siehe auch  
 [MonthCalendar\-Steuerelement](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)   
 [Gewusst wie: Ändern der Darstellung des MonthCalendar\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)   
 [Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)