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
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332234"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a>Vorgehensweise: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms
Eine wichtige Funktion von der Windows Forms <xref:System.Windows.Forms.MonthCalendar> Steuerelement ist, dass der Benutzer einen Bereich von Datumswerten auswählen kann. Diese Funktion ist eine Verbesserung gegenüber der Auswahl des dem <xref:System.Windows.Forms.DateTimePicker> -Steuerelement, das nur der Benutzer einen einzelnes Datum/Uhrzeit-Wert auswählen kann. Sie können einen Datumsbereich festlegen oder einen Auswahlbereich, die vom Benutzer festgelegt werden, mithilfe von Eigenschaften zu erhalten die <xref:System.Windows.Forms.MonthCalendar> Steuerelement. Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Auswahlbereich festgelegt wird.  
  
### <a name="to-select-a-range-of-dates"></a>Um einen Datumsbereich auszuwählen.  
  
1. Erstellen Sie <xref:System.DateTime> Objekte, die das erste und letzte Datum in einem Bereich darstellen.  
  
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
  
2. Legen Sie die <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>-Eigenschaft fest.  
  
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
  
     – oder –  
  
     Legen Sie für die Eigenschaften <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> und <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> fest.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [MonthCalendar-Steuerelement](monthcalendar-control-windows-forms.md)
- [Vorgehensweise: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms](how-to-change-monthcalendar-control-appearance.md)
- [Vorgehensweise: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [Vorgehensweise: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms](display-more-than-one-month-wf-monthcalendar-control.md)
