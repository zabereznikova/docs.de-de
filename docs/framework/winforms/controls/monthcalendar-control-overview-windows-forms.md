---
title: "&#220;bersicht &#252;ber das MonthCalendar-Steuerelement (Windows Forms) | Microsoft Docs"
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
  - "MonthCalendar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Calendar-Steuerelemente, Windows Forms"
  - "Kalender, Windows Forms-Steuerelemente"
  - "MonthCalendar-Steuerelement [Windows Forms], Festlegen des ersten Tages der Woche"
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber das MonthCalendar-Steuerelement (Windows Forms)
Das <xref:System.Windows.Forms.MonthCalendar>\-Steuerelement in Windows Forms bietet eine intuitive grafische Oberfläche, mit der Benutzer Datumsinformationen anzeigen und festlegen können.  Das Steuerelement zeigt einen Kalender an: ein Datenblatt mit den nummerierten Tagen des Monats, die unter den Wochentagen in Spalten angeordnet sind. Der ausgewählte Datumsbereich ist hervorgehoben.  Sie können einen anderen Monat auswählen, indem Sie auf die Pfeilschaltflächen links und rechts von der Monatsbeschriftung klicken.  Im Gegensatz zum ähnlichen <xref:System.Windows.Forms.DateTimePicker>\-Steuerelement können Sie mit diesem Steuerelement mehrere Daten auswählen.  Weitere Informationen über das <xref:System.Windows.Forms.DateTimePicker>\-Steuerelement finden Sie unter [DateTimePicker\-Steuerelement](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md).  
  
## Konfigurieren des MonthCalendar\-Steuerelements  
 Die Darstellung des <xref:System.Windows.Forms.MonthCalendar>\-Steuerelements kann auf viele verschiedene Weisen konfiguriert werden.  Standardmäßig wird das aktuelle Datum in einem Kreis und zusätzlich am unteren Ende des Datenblattes angezeigt.  Sie können dieses Feature ändern, indem Sie die <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A>\-Eigenschaft und die <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A>\-Eigenschaft auf `false` festlegen.  Sie können auch Wochenzahlen zum Kalender hinzufügen, indem Sie die <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A>\-Eigenschaft auf `true` festlegen.  Wenn Sie die <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>\-Eigenschaft festlegen, können Sie mehrere Monate horizontal und vertikal anzeigen lassen.  Standardmäßig wird der Sonntag als erster Tag der Woche angezeigt. Mit der <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A>\-Eigenschaft kann aber auch jeder andere Tag als erster Tag festgelegt werden.  
  
 Sie können auch festlegen, dass bestimmte Daten fett angezeigt werden, und zwar entweder einmalig, jährlich oder monatlich, indem Sie <xref:System.DateTime>\-Objekte zu den Eigenschaften <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> und <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> hinzufügen.  Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md).  
  
 Die Schlüsseleigenschaft des <xref:System.Windows.Forms.MonthCalendar>\-Steuerelements ist <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, die den im Steuerelement ausgewählten Datumsbereich angibt.  Der <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>\-Wert darf die Höchstzahl der auswählbaren Tage nicht überschreiten, die in der <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A>\-Eigenschaft festgelegt ist.  Das früheste und das späteste Datum, das vom Benutzer ausgewählt werden kann, wird mit der <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A>\-Eigenschaft und der <xref:System.Windows.Forms.MonthCalendar.MinDate%2A>\-Eigenschaft bestimmt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.MonthCalendar>   
 [MonthCalendar\-Steuerelement](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)