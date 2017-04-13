---
title: "Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Kalender, Formatieren der Anzeige"
  - "Kalender, Mehrere Monate"
  - "Beispiele [Windows Forms], Calendar-Steuerelemente"
  - "MonthCalendar-Steuerelement [Windows Forms], Formatieren der Anzeige"
ms.assetid: d197caa2-38a5-4cb4-acc3-562130c2ace3
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows&#160;Forms
Mit dem <xref:System.Windows.Forms.MonthCalendar>\-Steuerelement in Windows Forms können Sie bis zu 12 Monate gleichzeitig anzeigen.  Standardmäßig zeigt das Steuerelement nur einen Monat an. Sie können jedoch selbst festlegen, wie viele Monate angezeigt und wie diese im Steuerelement angeordnet werden.  Wenn Sie die Größe des Kalenders ändern, wird die Größe des Steuerelements angepasst. Daher müssen Sie sicherstellen, dass ausreichend Platz auf dem Formular vorhanden ist.  
  
### So zeigen Sie mehrere Monate an  
  
-   Legen Sie für die <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>\-Eigenschaft die Anzahl der horizontal und vertikal anzuzeigenden Monate fest.  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## Siehe auch  
 [MonthCalendar\-Steuerelement](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)   
 [Gewusst wie: Ändern der Darstellung des MonthCalendar\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)