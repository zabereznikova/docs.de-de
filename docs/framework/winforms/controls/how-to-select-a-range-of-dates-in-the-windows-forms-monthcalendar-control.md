---
title: "Gewusst wie: Ausw&#228;hlen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows&#160;Forms | Microsoft Docs"
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
  - "Kalender, Auswählen des Datumsbereichs"
  - "Datumsangaben, Auswählen des Bereichs in Calendar-Steuerelementen"
  - "Beispiele [Windows Forms], Calendar-Steuerelemente"
  - "MonthCalendar-Steuerelement [Windows Forms], Auswählen des Datumsbereichs"
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Ausw&#228;hlen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows&#160;Forms
Ein wichtige Feature des <xref:System.Windows.Forms.MonthCalendar>\-Steuerelements von Windows Forms besteht darin, dass der Benutzer einen Datumsbereich auswählen kann.  Dieses Feature stellt eine Verbesserung gegenüber der Datumsauswahlfunktion des <xref:System.Windows.Forms.DateTimePicker>\-Steuerelements dar, da diese lediglich die Auswahl eines einzelnen Datum\/Zeit\-Wertes durch den Benutzer zulässt.  Sie können einen Datumsbereich festlegen oder einen Auswahlbereich abrufen, den der Benutzer über die Eigenschaften des <xref:System.Windows.Forms.MonthCalendar>\-Steuerelements festgelegt hat.  Im folgenden Codebeispiel wird veranschaulicht, wie ein Auswahlbereich festgelegt wird.  
  
### So wählen Sie einen Datumsbereich aus  
  
1.  Erstellen Sie die <xref:System.DateTime>\-Objekte für das erste und das letzte Datum eines Bereichs.  
  
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
  
2.  Legen Sie die <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>\-Eigenschaft fest.  
  
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
  
     – oder –  
  
     Legen Sie die <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A>\-Eigenschaft und die <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A>\-Eigenschaft fest.  
  
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
  
## Siehe auch  
 [MonthCalendar\-Steuerelement](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [Gewusst wie: Ändern der Darstellung des MonthCalendar\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)   
 [Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)   
 [Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)