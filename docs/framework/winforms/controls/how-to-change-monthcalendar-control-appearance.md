---
title: 'Vorgehensweise: Ändern Sie die Windows Forms MonthCalendar Darstellung des Steuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: b7f321c1557bc7ea19213f2fc67767fe56328cf4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258920"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a>Vorgehensweise: Ändern Sie die Windows Forms MonthCalendar Darstellung des Steuerelements
Die Windows-Formulare <xref:System.Windows.Forms.MonthCalendar> Steuerelement ermöglicht es Ihnen, zum Anpassen der Darstellung des Kalenders in vielerlei Hinsicht. Sie können z. B. das Farbschema festlegen und anzeigen oder ausblenden Wochennummern und dem aktuellen Datum.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>Der im Monatskalender Farbschema ändern  
  
-   Legen Sie Eigenschaften wie z. B. <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> und <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>. Die <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> -Eigenschaft bestimmt auch die Schriftfarbe für die Tage der Woche. Die <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> -Eigenschaft bestimmt die Farbe der Datumsangaben, die vor und nach den angezeigten Monat oder Monaten.  
  
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
    >  Beginnen mit Windows Vista und das Design, wird durch Festlegen von einige Eigenschaften möglicherweise nicht die Darstellung des Kalenders geändert. Wenn Windows festgelegt ist, verwenden Sie die Aero-Design, z. B. Festlegen der <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, oder <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> Eigenschaften hat keine Auswirkungen. Das liegt eine aktualisierte Version des Kalenders mit einer Darstellung gerendert wird, das zur Laufzeit aus dem aktuellen Betriebssystem Design abgeleitet wird. Wenn Sie diese Eigenschaften verwenden, und aktivieren Sie die frühere Version des Kalenders möchten, können Sie visuelle Stile für Ihre Anwendung deaktivieren. Deaktivieren von visuellen Stilen kann die Darstellung und das Verhalten anderer Steuerelemente in Ihrer Anwendung beeinträchtigen. Klicken Sie zum Deaktivieren von visuellen Stilen in Visual Basic den Projekt-Designer zu öffnen, und deaktivieren Sie die **XP visual-Stile aktivieren** Kontrollkästchen. Klicken Sie zum Deaktivieren von visuellen Stilen in C#-Datei "Program.cs" öffnen, und kommentieren Sie `Application.EnableVisualStyles();`. Weitere Informationen zu visuellen Stilen finden Sie unter [Vorgehensweise: Aktivieren von visuellen Windows XP-Stile](https://msdn.microsoft.com/library/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>Das aktuelle Datum am unteren Rand des Steuerelements angezeigt.  
  
-   Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> -Eigenschaft auf `true`fest. Das folgende Beispiel schaltet zwischen der Anzeige und das Auslassen des heutigen Datums, wenn das Formular doppelgeklickt wird.  
  
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
  
     (Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>Wochennummern angezeigt.  
  
-   Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> -Eigenschaft auf `true`fest. Sie können diese Eigenschaft im Code oder im Fenster Eigenschaften festlegen.  
  
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
- [MonthCalendar-Steuerelement](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
- [Vorgehensweise: Auswählen eines Datumsbereichs in das Windows Forms-MonthCalendar-Steuerelement](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Vorgehensweise: Anzeige bestimmte Tage im mit der Windows Bold Forms-MonthCalendar-Steuerelement](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [Vorgehensweise: Anzeigen von mehr als einen Monat in der Windows Forms-MonthCalendar-Steuerelement](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
