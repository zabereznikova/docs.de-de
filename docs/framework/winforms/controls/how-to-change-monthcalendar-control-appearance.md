---
title: 'Vorgehensweise: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: 5582624d881b2d8039bcd5e8ac45e548c7b38f57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929045"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a>Vorgehensweise: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms
Mit dem <xref:System.Windows.Forms.MonthCalendar> Windows Forms-Steuerelement können Sie die Darstellung des Kalenders in vielerlei Hinsicht anpassen. Beispielsweise können Sie das Farbschema festlegen und angeben, ob Wochen Nummern und das aktuelle Datum angezeigt oder ausgeblendet werden sollen.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>So ändern Sie das Farbschema des Monats Kalenders  
  
- Legen Sie Eigenschaften wie <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> und <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>fest. Die <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> -Eigenschaft bestimmt auch die Schriftfarbe für die Wochentage. Die <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> -Eigenschaft bestimmt die Farbe der Datumsangaben, die vorangestellt sind, und folgt den angezeigten Monaten oder Monaten.  
  
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
    > Beginnend mit Windows Vista und abhängig vom Design wird durch das Festlegen einiger Eigenschaften möglicherweise nicht die Darstellung des Kalenders geändert. Wenn Windows z. b. für die Verwendung des Aero-Designs festgelegt <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>ist, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>hat das <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> Festlegen der Eigenschaften, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, oder keine Auswirkungen. Dies liegt daran, dass eine aktualisierte Version des Kalenders mit einer Darstellung gerendert wird, die zur Laufzeit aus dem aktuellen Betriebssystemdesign abgeleitet wird. Wenn Sie diese Eigenschaften verwenden und die frühere Version des Kalenders aktivieren möchten, können Sie visuelle Stile für die Anwendung deaktivieren. Das Deaktivieren von visuellen Stilen kann sich auf die Darstellung und das Verhalten anderer Steuerelemente in der Anwendung auswirken. Um visuelle Stile in Visual Basic zu deaktivieren, öffnen Sie den Projekt-Designer, und deaktivieren Sie das Kontrollkästchen **Visual XP-Stile aktivieren** . Um visuelle Stile in C#zu deaktivieren, öffnen Sie Program.cs, `Application.EnableVisualStyles();`und kommentieren Sie aus. Weitere Informationen zu visuellen Stilen finden Sie unter [Aktivieren von visuellen Stilen](/windows/desktop/controls/cookbook-overview).  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>So zeigen Sie das aktuelle Datum am unteren Rand des Steuer Elements an  
  
- Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> -Eigenschaft auf `true`fest. Das folgende Beispiel wechselt zwischen dem anzeigen und Weglassen des aktuellen Datums, wenn auf das Formular Doppel geklickt wird.  
  
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
  
     (Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>So zeigen Sie Wochen Nummern an  
  
- Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> -Eigenschaft auf `true`fest. Sie können diese Eigenschaft entweder im Code oder im Eigenschaftenfenster festlegen.  
  
     Wochen Nummern werden in einer separaten Spalte auf der linken Seite des ersten Tags der Woche angezeigt.  
  
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

- [MonthCalendar-Steuerelement](monthcalendar-control-windows-forms.md)
- [Vorgehensweise: Wählen Sie einen Datumsbereich im Windows Forms MonthCalendar-Steuerelement aus.](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Vorgehensweise: Anzeigen bestimmter Tage in Fett Schrift mit dem Windows Forms MonthCalendar-Steuerelement](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [Vorgehensweise: Mehr als einen Monat im Windows Forms MonthCalendar-Steuerelement anzeigen](display-more-than-one-month-wf-monthcalendar-control.md)
