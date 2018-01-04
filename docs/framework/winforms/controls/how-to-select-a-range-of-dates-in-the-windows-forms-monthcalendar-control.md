---
title: "Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms"
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
- dates [Windows Forms], selecting range in calendar controls
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], selecting date range
- MonthCalendar control [Windows Forms], selecting date range
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32555097c25a23ca1de6e20308a420d3ec70caf9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a>Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms
Ein wichtiges Feature von Windows Forms <xref:System.Windows.Forms.MonthCalendar> Steuerelement ist, dass der Benutzer einen Datumsbereich auswählen kann. Diese Funktion ist eine Verbesserung gegenüber der Datumsauswahl Funktion von der <xref:System.Windows.Forms.DateTimePicker> -Steuerelement, das nur die Benutzer in einer einzelnen Datums-/Uhrzeitwert auswählen kann. Sie können einen Datumsbereich festlegen oder Abrufen einer vom Benutzer festgelegt werden, mithilfe der Eigenschaften des Auswahlbereichs der <xref:System.Windows.Forms.MonthCalendar> Steuerelement. Im folgenden Codebeispiel wird veranschaulicht, wie einen Auswahlbereich festgelegt wird.  
  
### <a name="to-select-a-range-of-dates"></a>Um einen Datumsbereich auszuwählen.  
  
1.  Erstellen Sie <xref:System.DateTime> Objekte, die die erste und letzte Datum in einem Bereich darstellen.  
  
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
  
2.  Legen Sie die <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>-Eigenschaft fest.  
  
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
 [MonthCalendar-Steuerelement](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [Gewusst wie: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)  
 [Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 [Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
