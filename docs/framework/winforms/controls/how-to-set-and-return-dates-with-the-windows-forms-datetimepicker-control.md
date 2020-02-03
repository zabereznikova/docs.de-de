---
title: Festlegen und Zurückgeben von Datumsangaben mit DateTimePicker-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], setting in DateTimePicker
- DateTimePicker control [Windows Forms], setting and returning dates
- examples [Windows Forms], DateTimePicker control
ms.assetid: a8a48d68-e4b5-426e-9764-51230fc9acd2
ms.openlocfilehash: 1e0aa58e98748ccde9411f0f4871adbae3a5f14d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747110"
---
# <a name="how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control"></a>Gewusst wie: Festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker-Steuerelement in Windows Forms
Die aktuell im <xref:System.Windows.Forms.DateTimePicker>-Steuerelement von Windows Forms ausgewählte Datumsangabe (Datum und Uhrzeit) ist durch die <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft bestimmt. Sie können die <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft festlegen, bevor das Steuerelement angezeigt wird (z. B. zur Entwurfszeit oder im <xref:System.Windows.Forms.Form.Load>-Ereignis des Formulars), um zu bestimmen, welches Datum zunächst im Steuerelement ausgewählt ist. Standardmäßig wird die <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft des Steuerelements auf das aktuelle Datum festgelegt. Wenn Sie die <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft des Steuerelements im Code ändern, wird das Steuerelement auf dem Formular automatisch entsprechend der neuen Einstellung aktualisiert.  
  
 Die <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft gibt eine <xref:System.DateTime>-Struktur als ihren Wert zurück. Es gibt verschiedene Eigenschaften der <xref:System.DateTime>-Struktur, die bestimmte Informationen zum angezeigten Datum zurückgeben. Mit diesen Eigenschaften können Werte nur zurückgegeben, aber nicht festgelegt werden.  
  
- Für Datumswerte geben die Eigenschaften <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A> und <xref:System.DateTime.Year%2A> Ganzzahlwerte für diese Zeiteinheiten des ausgewählten Datums zurück. Die <xref:System.DateTime.DayOfWeek%2A>-Eigenschaft gibt einen Wert zurück, der den ausgewählten Wochentag angibt (mögliche Werte sind in der <xref:System.DayOfWeek>-Enumeration aufgelistet).  
  
- Für Zeitwerte geben die Eigenschaften <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A> und <xref:System.DateTime.Millisecond%2A> Ganzzahlwerte für diese Zeiteinheiten zurück. Informationen zum Konfigurieren des Steuer Elements für die Anzeige von Zeiten finden Sie unter Gewusst [wie: Anzeigen der Zeit mit dem DateTimePicker-Steuer](how-to-display-time-with-the-datetimepicker-control.md)Element.  
  
### <a name="to-set-the-date-and-time-value-of-the-control"></a>So legen Sie das Datum und die Uhrzeit für das Steuerelement fest  
  
- Legen Sie die <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft auf einen Datums- oder Uhrzeitwert fest.  
  
    ```vb  
    DateTimePicker1.Value = New DateTime(2001, 10, 20)  
    ```  
  
    ```csharp  
    dateTimePicker1.Value = new DateTime(2001, 10, 20);  
    ```  
  
    ```cpp  
    dateTimePicker1->Value = DateTime(2001, 10, 20);  
    ```  
  
### <a name="to-return-the-date-and-time-value"></a>So geben Sie den Datums- und den Uhrzeitwert zurück  
  
- Rufen Sie die <xref:System.Windows.Forms.DateTimePicker.Text%2A>-Eigenschaft auf, um den gesamten Wert so zurückzugeben, wie er im Steuerelement formatiert ist, oder rufen Sie die entsprechende Methode der <xref:System.Windows.Forms.DateTimePicker.Value%2A>-Eigenschaft auf, um einen Teil des Werts zurückzugeben Verwenden Sie <xref:System.Windows.Forms.DateTimePicker.ToString%2A>, um die Informationen in eine Zeichenfolge zu konvertieren, die Benutzern angezeigt werden kann.  
  
    ```vb  
    MessageBox.Show("The selected value is ", DateTimePicker1.Text)  
    MessageBox.Show("The day of the week is ",   
       DateTimePicker1.Value.DayOfWeek.ToString)  
    MessageBox.Show("Millisecond is: ",   
       DateTimePicker1.Value.Millisecond.ToString)  
    ```  
  
    ```csharp  
    MessageBox.Show ("The selected value is " +   
       dateTimePicker1.Text);  
    MessageBox.Show ("The day of the week is " +   
       dateTimePicker1.Value.DayOfWeek.ToString());  
    MessageBox.Show("Millisecond is: " +   
       dateTimePicker1.Value.Millisecond.ToString());  
    ```  
  
    ```cpp  
    MessageBox::Show (String::Concat("The selected value is ",  
       dateTimePicker1->Text));  
    MessageBox::Show (String::Concat("The day of the week is ",  
       dateTimePicker1->Value.DayOfWeek.ToString()));  
    MessageBox::Show(String::Concat("Millisecond is: ",  
       dateTimePicker1->Value.Millisecond.ToString()));  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [DateTimePicker-Steuerelement](datetimepicker-control-windows-forms.md)
- [Gewusst wie: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
