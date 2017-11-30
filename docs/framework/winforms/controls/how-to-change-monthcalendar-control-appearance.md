---
title: "Vorgehensweise: Ändern der MonthCalendar-Steuerelement in Windows Forms &#39; s Darstellung"
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
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 38cddb4222077c21d72828371a8fe025184c4f75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-windows-forms-monthcalendar-control39s-appearance"></a>Vorgehensweise: Ändern der MonthCalendar-Steuerelement in Windows Forms &#39; s Darstellung
Windows Forms <xref:System.Windows.Forms.MonthCalendar> Steuerelement ermöglicht es Ihnen, zum Anpassen der Darstellung des Kalenders in vielerlei Hinsicht. Sie können z. B. das Farbschema festlegen und Wochennummern und das aktuelle Datum ein- oder ausgeblendet werden sollen.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>So ändern Sie den Monatskalender Farbschema  
  
-   Legen Sie Eigenschaften wie z. B. <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> und <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>. Die <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> -Eigenschaft bestimmt auch die Schriftfarbe für die Tage der Woche. Die <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> Eigenschaft bestimmt die Farbe der Datumsangaben, die vor und nach der angezeigten oder mehrere Monate.  
  
    ```vb  
    MonthCalendar1.TitleBackColor = System.Drawing.Color.Blue  
    MonthCalendar1.TrailingForeColor = System.Drawing.Color.Red  
    MonthCalendar1.TitleForeColor = System.Drawing.Color.Yellow  
    ```  
  
    ```csharp  
    monthCalendar1.TitleBackColor = System.Drawing.Color.Blue;  
    monthCalendar1.TrailingForeColor = System.Drawing.Color.Red;  
    monthCalendar1.TitleForeColor = System.Drawing.Color.Yellow;  
    ```  
  
    ```cpp  
    monthCalendar1->TitleBackColor = System::Drawing::Color::Blue;  
    monthCalendar1->TrailingForeColor = System::Drawing::Color::Red;  
    monthCalendar1->TitleForeColor = System::Drawing::Color::Yellow;  
    ```  
  
    > [!NOTE]
    >  Beginnen mit Windows Vista und je nach das Design, wird durch Festlegen einiger Eigenschaften möglicherweise nicht die Darstellung des Kalenders ändern. Wenn Windows Aero Design verwenden festgelegt ist, z. B. durch Festlegen der <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, oder <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> Eigenschaften hat keine Auswirkungen. Dies ist, da eine aktualisierte Version des Kalenders mit einer Darstellung gerendert wird, die zur Laufzeit aus dem aktuellen Design des Betriebssystems abgeleitet wird. Wenn Sie diese Eigenschaften verwenden und die frühere Version des Kalenders aktivieren möchten, können Sie visuelle Stile für die Anwendung deaktivieren. Deaktivieren von visuellen Stilen beeinträchtigt das Aussehen und Verhalten anderer Steuerelemente in Ihrer Anwendung. Um visuelle Stile in Visual Basic zu deaktivieren, öffnen Sie den Projekt-Designer, und deaktivieren Sie die **XP aktiviert visuelle Stile** Kontrollkästchen. Um visuelle Stile in c# zu deaktivieren, öffnen Sie die Datei "Program.cs", und kommentieren Sie `Application.EnableVisualStyles();`. Weitere Informationen zu visuellen Stilen finden Sie unter [Vorgehensweise: Aktivieren Sie visuelle Stile in Windows XP](http://msdn.microsoft.com/en-us/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>Das aktuelle Datum am unteren Rand des Steuerelements anzeigen  
  
-   Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A>-Eigenschaft auf `true` fest. Das folgende Beispiel schaltet zwischen der Anzeige und das Auslassen des heutigen Datums, wenn das Formular doppelgeklickt wird.  
  
    ```vb  
    Private Sub Form1_DoubleClick(ByVal sender As Object, _  
    ByVal e As System.EventArgs) Handles MyBase.DoubleClick  
       ' Toggle between True and False.  
       MonthCalendar1.ShowToday = Not MonthCalendar1.ShowToday  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_DoubleClick(object sender, System.EventArgs e)  
    {  
       // Toggle between True and False.  
       monthCalendar1.ShowToday = !monthCalendar1.ShowToday;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void Form1_DoubleClick(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // Toggle between True and False.  
          monthCalendar1->ShowToday = !monthCalendar1->ShowToday;  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Fügen Sie den folgenden Code in den Konstruktor der Form ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>Wochennummern angezeigt.  
  
-   Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A>-Eigenschaft auf `true` fest. Sie können diese Eigenschaft im Code oder im Eigenschaftenfenster festlegen.  
  
     Wochennummern angezeigt werden, in einer separaten Spalte auf der linken Seite des ersten Tages der Woche.  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [MonthCalendar-Steuerelement](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 [Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
