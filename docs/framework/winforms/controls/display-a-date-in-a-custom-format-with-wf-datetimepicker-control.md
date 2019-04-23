---
title: 'Vorgehensweise: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 08d5a505229cd434dbf82e8ae4624bb418efd379
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335939"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>Vorgehensweise: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.DateTimePicker> Control bietet Ihnen die Flexibilität bei der Formatierung der Anzeige von Datumsangaben und Uhrzeiten in das Steuerelement. Die <xref:System.Windows.Forms.DateTimePicker.Format%2A> Eigenschaft ermöglicht Ihnen die Auswahl aus vordefinierten Formaten, aufgeführt der <xref:System.Windows.Forms.DateTimePickerFormat>. Wenn keines dieser für Ihre Zwecke angemessen ist, können Sie erstellen Ihre eigenen Formatstil Formatzeichen in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.  
  
### <a name="to-display-a-custom-format"></a>Um ein benutzerdefiniertes Format anzuzeigen.  
  
1. Legen Sie die <xref:System.Windows.Forms.DateTimePicker.Format%2A> -Eigenschaft auf `DateTimePickerFormat.Custom`fest.  
  
2. Legen Sie die <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> Eigenschaft an eine Formatzeichenfolge.  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a>Hinzufügen von Text zu den formatierten Wert  
  
1. Einfache Anführungszeichen verwenden, um alle Zeichen, die nicht Formatzeichen wie "M" oder Trennzeichen wie ist ":". Die Formatzeichenfolge unten zeigt z. B. das aktuelle Datum im Format "heute ist: 05:30:31 Freitag März 02, 2012" in der Kultur Englisch (USA).  
  
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
  
     Abhängig von der kultureinstellung, darf keine Zeichen, die nicht in einfache Anführungszeichen eingeschlossen geändert werden. Die Formatzeichenfolge, die oben genannten zeigt z. B. das aktuelle Datum im Format "heute ist: 05:30:31 Freitag März 02, 2012" in der Kultur Englisch (USA). Beachten Sie, dass es sich bei der erste Doppelpunkt in einfache Anführungszeichen eingeschlossen ist, da sie ein Trennzeichen sein, wie es in "hh: mm:" ist nicht vorgesehen ist. In einer anderen Kultur, scheinen sich das Format als "aktuell sind: 05.30.31 Freitag März 02, 2012".  
  
## <a name="see-also"></a>Siehe auch

- [DateTimePicker-Steuerelement](datetimepicker-control-windows-forms.md)
- [Vorgehensweise: Festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker-Steuerelement in Windows Forms](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
