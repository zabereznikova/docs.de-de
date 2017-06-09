---
title: "Gewusst wie: &#196;ndern der Darstellung des MonthCalendar-Steuerelements in Windows&#160;Forms | Microsoft Docs"
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
  - "Beispiele [Windows Forms], Calendar-Steuerelemente"
  - "MonthBackColor-Eigenschaft"
  - "MonthCalendar-Steuerelement [Windows Forms], Formatieren der Anzeige"
  - "TitleBackColor-Eigenschaft"
  - "TitleForeColor-Eigenschaft"
  - "TrailingForeColor-Eigenschaft"
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: &#196;ndern der Darstellung des MonthCalendar-Steuerelements in Windows&#160;Forms
Mit dem <xref:System.Windows.Forms.MonthCalendar>\-Steuerelement in Windows Forms können Sie die Kalenderdarstellung auf verschiedene Weisen anpassen.  Beispielsweise können Sie das Farbschema festlegen und Wochennummern sowie das aktuelle Datum ein\- oder ausblenden.  
  
### So ändern Sie das Farbschema des Monatskalenders  
  
-   Legen Sie Eigenschaften wie <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> und <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> fest.  Mit der <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>\-Eigenschaft legen Sie auch die Schriftfarbe für die Wochentage fest.  Die <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>\-Eigenschaft bestimmt die Farbe für die Datumsangaben, die dem bzw. den angezeigten Monaten vorangehen oder folgen.  
  
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
    >  Ab Windows Vista und je nach Design wird durch Festlegen einiger Eigenschaften möglicherweise nicht die Darstellung des Kalenders geändert.  Wenn Windows z. B. für die Verwendung des Aero\-Designs festgelegt ist, besitzt das Festlegen der Eigenschaften <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> oder <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> keine Auswirkungen.  Dies liegt daran, dass eine aktualisierte Version des Kalenders mit einer Darstellung gerendert wird, die zur Laufzeit vom Design des aktuellen Betriebssystems abgeleitet wird.  Wenn Sie diese Eigenschaften verwenden und die frühere Version des Kalenders ermöglichen möchten, können Sie visuelle Stile für die Anwendung deaktivieren.  Das Deaktivieren visueller Stile kann sich auf die Darstellung und das Verhalten anderer Steuerelemente in der Anwendung auswirken.  Um visuelle Stile in Visual Basic zu deaktivieren, öffnen Sie den Projekt\-Designer, und deaktivieren Sie das Kontrollkästchen **Visuelle XP\-Stile aktivieren**.  Um visuelle Stile in C\# zu deaktivieren, öffnen Sie Program.cs und kommentieren Sie `Application.EnableVisualStyles();` aus.  Weitere Informationen zu visuellen Stilen finden Sie unter [How to: Enable Windows XP Visual Styles](http://msdn.microsoft.com/de-de/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).  
  
### So zeigen Sie das aktuelle Datum am unteren Rand des Steuerelements an  
  
-   Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A>\-Eigenschaft auf `true` fest.  Mit dem Beispiel unten wird das aktuelle Datum abwechselnd angezeigt oder ausgeblendet, wenn auf das Formular doppelgeklickt wird.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### So zeigen Sie Wochennummern an  
  
-   Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A>\-Eigenschaft auf `true` fest.  Sie können diese Eigenschaft entweder im Code oder im Eigenschaftenfenster festlegen.  
  
     Wochennummern werden in einer separaten Spalte links vom ersten Wochentag angezeigt.  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## Siehe auch  
 [MonthCalendar\-Steuerelement](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [Gewusst wie: Auswählen eines Datumsbereichs mithilfe des MonthCalendar\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)   
 [Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)   
 [Gewusst wie: Anzeigen mehrerer Monate mit dem MonthCalendar\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)