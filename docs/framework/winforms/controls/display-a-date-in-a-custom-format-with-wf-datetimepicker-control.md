---
title: "Gewusst wie: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Datumsangaben, Anzeigen in DateTimePicker-Steuerelementen"
  - "DateTimePicker-Steuerelement [Windows Forms], Anzeigestile"
  - "Beispiele [Windows Forms], DateTimePicker-Steuerelement"
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows&#160;Forms
Mit dem <xref:System.Windows.Forms.DateTimePicker>\-Steuerelement in Windows Forms können Sie die Datums\- und Zeitangaben im Steuerelement äußerst flexibel formatieren.  Die <xref:System.Windows.Forms.DateTimePicker.Format%2A>\-Eigenschaft ermöglicht es Ihnen, aus vordefinierten Formaten auszuwählen, die im <xref:System.Windows.Forms.DateTimePickerFormat> aufgelistet sind.  Wenn keines dieser Formate für Ihre Zwecke geeignet ist, können Sie einen eigenen Formatstil erstellen und dafür die in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> aufgeführten Formatzeichen verwenden.  
  
### So zeigen Sie ein benutzerdefiniertes Format an  
  
1.  Legen Sie die <xref:System.Windows.Forms.DateTimePicker.Format%2A>\-Eigenschaft auf `DateTimePickerFormat.Custom` fest.  
  
2.  Legen Sie für die <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>\-Eigenschaft eine Formatzeichenfolge fest.  
  
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
  
### So fügen Sie Text zum formatierten Wert hinzu  
  
1.  Setzen Sie einfache Anführungszeichen um alle Zeichen, die keine Formatzeichen wie "M" oder Trennzeichen wie ":" sind.  Mit der folgenden Formatzeichenfolge wird beispielsweise in der Kultur Englisch \(USA\) das aktuelle Datum im Format "Today is: 05:30:31 Friday March 02, 2012" angezeigt.  
  
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
  
     Je nach Kultureinstellungen können sämtliche Zeichen geändert werden, die nicht in einfache Anführungszeichen eingeschlossenen sind.  Mit der oben stehenden Formatzeichenfolge wird beispielsweise in der Kultur Englisch \(USA\) das aktuelle Datum im Format "Today is: 05:30:31 Friday March 02, 2012" angezeigt.  Beachten Sie, dass der erste Doppelpunkt in einfache Anführungszeichen eingeschlossen ist, da er, anders als in "hh:mm:ss", nicht als Trennzeichen gilt.  In einer anderen Kultur könnte das Format folgendermaßen angezeigt werden: "Today is: 05.30.31 Friday March 02, 2012".  
  
## Siehe auch  
 [DateTimePicker\-Steuerelement](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)   
 [Gewusst wie: Festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)