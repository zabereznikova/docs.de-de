---
title: "Gewusst wie: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms"
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
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5f5c7d856991ae8e0bf7caff656bf7010255628
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>Gewusst wie: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms
Windows Forms <xref:System.Windows.Forms.DateTimePicker> Steuerelement bietet Ihnen die Flexibilität beim Formatieren der Anzeige von Datums- und Uhrzeitangaben im Steuerelement. Die <xref:System.Windows.Forms.DateTimePicker.Format%2A> -Eigenschaft können Sie in aufgeführten vordefinierten Formate aus der <xref:System.Windows.Forms.DateTimePickerFormat>. Wenn keiner dieser für Ihre Zwecke angemessen ist, können Sie eigene Formatstil Formatieren von Zeichen in aufgeführt erstellen <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.  
  
### <a name="to-display-a-custom-format"></a>Um ein benutzerdefiniertes Format anzuzeigen.  
  
1.  Legen Sie die <xref:System.Windows.Forms.DateTimePicker.Format%2A>-Eigenschaft auf `DateTimePickerFormat.Custom` fest.  
  
2.  Legen Sie die <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> Eigenschaft auf eine Formatzeichenfolge.  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a>Der formatierte Wert Text hinzu  
  
1.  Verwenden Sie einfache Anführungszeichen zum Einschließen von einem beliebigen Zeichen, die nicht Formatzeichen wie "M" oder ein Trennzeichen wie ist ":". Die Formatzeichenfolge unten zeigt z. B. das aktuelle Datum im Format "heutzutage: 05:30:31 Freitag 02 März 2012" in der englischen (USA) Kultur.  
  
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
  
     Abhängig von der kultureinstellung darf keine Zeichen, die nicht in einfache Anführungszeichen eingeschlossen geändert werden. Die Formatzeichenfolge, die oben genannten zeigt z. B. das aktuelle Datum im Format "heutzutage: 05:30:31 Freitag 02 März 2012" in der englischen (USA) Kultur. Beachten Sie, dass es sich bei der erste Doppelpunkt in einfache Anführungszeichen eingeschlossen ist, da sie nicht dazu gedacht ist ein Trennzeichen ist, wie diese in "hh" sind. In einer anderen Kultur könnte das Format als angezeigt werden "heutzutage: 05.30.31 Freitag 02 März 2012".  
  
## <a name="see-also"></a>Siehe auch  
 [DateTimePicker-Steuerelement](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [Gewusst wie: Festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
