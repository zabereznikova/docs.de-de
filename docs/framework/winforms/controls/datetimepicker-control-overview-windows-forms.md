---
title: "&#220;bersicht &#252;ber das DateTimePicker-Steuerelement (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DateTimePicker"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Datums- und Zeitauswahlsteuerelemente"
  - "DateTimePicker-Steuerelement [Windows Forms], Informationen über"
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# &#220;bersicht &#252;ber das DateTimePicker-Steuerelement (Windows Forms)
Das <xref:System.Windows.Forms.DateTimePicker>\-Steuerelement in Windows Forms ermöglicht es Benutzern, ein einzelnes Element aus einer Liste mit Datums\- oder Zeitangaben auszuwählen.  Für die Datumsdarstellung besteht es aus zwei Teilen: einer Dropdownliste mit einer Datumsangabe, die als Text dargestellt wird, und einem Datenblatt, das angezeigt wird, wenn Sie auf den Abwärtspfeil neben der Liste klicken.  Das Raster sieht wie das <xref:System.Windows.Forms.MonthCalendar>\-Steuerelement aus, das zur Auswahl mehrerer Datumsangaben verwendet werden kann.  Weitere Informationen zum <xref:System.Windows.Forms.MonthCalendar>\-Steuerelement finden Sie unter [Übersicht über das MonthCalendar\-Steuerelement](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md).  
  
## Haupteigenschaften  
 Wenn <xref:System.Windows.Forms.DateTimePicker> als Steuerelement zur Auswahl oder Bearbeitung von Uhrzeiten anstelle von Daten angezeigt werden soll, legen Sie die <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A>\-Eigenschaft auf `true` und die <xref:System.Windows.Forms.DateTimePicker.Format%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DateTimePickerFormat> fest.  Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen der Zeit mithilfe des DateTimePicker\-Steuerelements](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).  
  
 Wenn für die <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A>\-Eigenschaft `true` festgelegt ist, wird im Steuerelement neben dem ausgewählten Datum ein Kontrollkästchen angezeigt.  Wenn das Kontrollkästchen aktiviert ist, kann der ausgewählte Wert für Datum\/Uhrzeit aktualisiert werden.  Wenn das Kontrollkästchen leer ist, ist der Wert nicht verfügbar.  
  
 Die <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DateTimePicker.MinDate%2A>\-Eigenschaft des Steuerelements bestimmen den Bereich für Datum und Uhrzeit.  Die <xref:System.Windows.Forms.DateTimePicker.Value%2A>\-Eigenschaft enthält das aktuelle Datum und die aktuelle Uhrzeit, auf das bzw. die das Steuerelement festgelegt ist.  Ausführlichere Informationen finden Sie unter [Gewusst wie: Festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md).  Die Werte können in vier Formaten angezeigt werden, die von der <xref:System.Windows.Forms.DateTimePicker.Format%2A>\-Eigenschaft festgelegt werden: <xref:System.Windows.Forms.DateTimePickerFormat>, <xref:System.Windows.Forms.DateTimePickerFormat>, <xref:System.Windows.Forms.DateTimePickerFormat> oder <xref:System.Windows.Forms.DateTimePickerFormat>.  Wenn ein benutzerdefiniertes Format ausgewählt wird, müssen Sie die <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>\-Eigenschaft auf eine geeignete Zeichenfolge festlegen.  Ausführlichere Informationen finden Sie unter [Gewusst wie: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## Siehe auch  
 [Gewusst wie: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)   
 [Gewusst wie: Festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)