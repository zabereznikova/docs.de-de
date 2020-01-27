---
title: Anzeigen eines Datums in einem benutzerdefinierten Format mit dem DateTimePicker-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
ms.openlocfilehash: a27dbe737b81af86c0ac50b791bcd87bafe05b4f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745937"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>Gewusst wie: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms
Das Windows Forms <xref:System.Windows.Forms.DateTimePicker>-Steuerelement bietet Ihnen Flexibilität beim Formatieren der Anzeige von Datums-und Uhrzeitangaben im-Steuerelement. Die <xref:System.Windows.Forms.DateTimePicker.Format%2A>-Eigenschaft ermöglicht es Ihnen, aus vordefinierten Formaten auszuwählen, die in der <xref:System.Windows.Forms.DateTimePickerFormat>aufgelistet sind. Wenn keines dieser Funktionen für Ihre Zwecke geeignet ist, können Sie einen eigenen Format Stil mithilfe der in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>aufgeführten Formatzeichen erstellen.  
  
### <a name="to-display-a-custom-format"></a>Anzeigen eines benutzerdefinierten Formats  
  
1. Legen Sie die <xref:System.Windows.Forms.DateTimePicker.Format%2A> -Eigenschaft auf `DateTimePickerFormat.Custom`fest.  
  
2. Legen Sie die <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>-Eigenschaft auf eine Format Zeichenfolge fest.  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### <a name="to-add-text-to-the-formatted-value"></a>So fügen Sie dem formatierten Wert Text hinzu  
  
1. Verwenden Sie einfache Anführungszeichen, um ein beliebiges Zeichen, das kein Formatzeichen wie "M" ist, oder ein Trennzeichen wie ":" einzuschließen. Die Format Zeichenfolge unten zeigt z. b. das aktuelle Datum mit dem Format "Today is: 05:30:31 Friday March 02, 2012" in der Kultur Englisch (USA) an.  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     Abhängig von der Kultur Einstellung können alle Zeichen, die nicht in einfache Anführungszeichen eingeschlossen sind, geändert werden. Die obige Format Zeichenfolge zeigt z. b. das aktuelle Datum mit dem Format "Today is: 05:30:31 Friday March 02, 2012" in der Kultur Englisch (USA) an. Beachten Sie, dass der erste Doppelpunkt in einfache Anführungszeichen eingeschlossen ist, da er nicht als Trennzeichen verwendet werden soll, da er sich in "hh: mm: SS" befindet. In einer anderen Kultur wird das Format möglicherweise als "heute ist: 05.30.31 Freitag, 02, 2012" angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- [DateTimePicker-Steuerelement](datetimepicker-control-windows-forms.md)
- [Gewusst wie: Festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker-Steuerelement in Windows Forms](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
