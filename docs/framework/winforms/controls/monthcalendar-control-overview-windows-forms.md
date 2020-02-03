---
title: Übersicht über das MonthCalendar-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
ms.openlocfilehash: a9b56164339d03b380a564b21855f6d94ec06af5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734939"
---
# <a name="monthcalendar-control-overview-windows-forms"></a>Übersicht über das MonthCalendar-Steuerelement (Windows Forms)
Das Windows Forms <xref:System.Windows.Forms.MonthCalendar>-Steuerelement stellt eine intuitive grafische Oberfläche für Benutzer dar, um Datumsinformationen anzuzeigen und festzulegen. Das-Steuerelement zeigt einen Kalender an: ein Raster mit den nummerierten Tagen des Monats, angeordnet in Spalten unterhalb der Wochentage, wobei der ausgewählte Bereich von Datumsangaben hervorgehoben ist. Sie können einen anderen Monat auswählen, indem Sie auf beiden Seiten der Monats Beschriftung auf die Pfeil Schaltflächen klicken. Im Gegensatz zum ähnlichen <xref:System.Windows.Forms.DateTimePicker> Steuerelement können Sie mit diesem Steuerelement mehr als ein Datum auswählen. Weitere Informationen zum <xref:System.Windows.Forms.DateTimePicker> Steuerelement finden Sie unter [DateTimePicker-Steuer](datetimepicker-control-windows-forms.md)Element.  
  
## <a name="configuring-the-monthcalendar-control"></a>Konfigurieren des MonthCalendar-Steuer Elements  
 Die Darstellung des <xref:System.Windows.Forms.MonthCalendar> Steuer Elements ist hochgradig konfigurierbar. Standardmäßig wird das heutige Datum als Kreis angezeigt und auch am unteren Ende des Rasters angegeben. Sie können diese Funktion ändern, indem Sie die Eigenschaften <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> und <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> auf `false`festlegen. Sie können dem Kalender auch Wochen Nummern hinzufügen, indem Sie die <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A>-Eigenschaft auf `true`festlegen. Wenn Sie die <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>-Eigenschaft festlegen, können mehrere Monate horizontal und vertikal angezeigt werden. Standardmäßig wird Sonntag als erster Tag der Woche angezeigt, aber jeder Tag kann mit der <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A>-Eigenschaft festgelegt werden.  
  
 Sie können auch festlegen, dass bestimmte Datumsangaben auf einmal, jährlich oder monatlich angezeigt werden, indem Sie <xref:System.DateTime> Objekte zu den Eigenschaften <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>und <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> hinzufügen. Weitere Informationen finden Sie unter Gewusst [wie: Anzeigen bestimmter Tage in Fett Schrift mit dem Windows Forms MonthCalendar-Steuer](display-specific-days-in-bold-with-wf-monthcalendar-control.md)Element.  
  
 Die Schlüsseleigenschaft des <xref:System.Windows.Forms.MonthCalendar> Steuer Elements ist <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, der Bereich der im Steuerelement ausgewählten Datumsangaben. Der <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> Wert darf die maximale Anzahl von Tagen, die ausgewählt werden können, nicht überschreiten, die in der <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A>-Eigenschaft festgelegt ist. Die frühesten und letzten Datumsangaben, die der Benutzer auswählen kann, werden durch die Eigenschaften <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> und <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> bestimmt.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.MonthCalendar>
- [MonthCalendar-Steuerelement](monthcalendar-control-windows-forms.md)
