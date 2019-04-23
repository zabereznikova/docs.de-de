---
title: Übersicht über das MonthCalendar-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
ms.openlocfilehash: 8928a78735392920d893661c70554bd35eba2886
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106235"
---
# <a name="monthcalendar-control-overview-windows-forms"></a>Übersicht über das MonthCalendar-Steuerelement (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.MonthCalendar> Steuerelement stellt eine intuitive grafische Benutzeroberfläche für Benutzer anzeigen und Festlegen von Datumsinformationen. Das Steuerelement zeigt einen Kalender: ein Raster mit die nummerierten Tage des Monats, um unter den Tagen der Woche mit den ausgewählten Datumsbereich hervorgehoben in Spalten angeordnet. Sie können einen anderen Monat auswählen, indem Sie auf die Pfeilschaltflächen auf beiden Seiten der Monat Beschriftung. Anders als die ähnliche <xref:System.Windows.Forms.DateTimePicker> -Steuerelement, können Sie mehr als ein Datum mit diesem Steuerelement auswählen. Weitere Informationen zu den <xref:System.Windows.Forms.DateTimePicker> steuern, finden Sie unter [DateTimePicker-Steuerelement](datetimepicker-control-windows-forms.md).  
  
## <a name="configuring-the-monthcalendar-control"></a>Konfigurieren des MonthCalendar-Steuerelements  
 Die <xref:System.Windows.Forms.MonthCalendar> Darstellung des Steuerelements ist hochgradig konfigurierbar. In der Standardeinstellung des heutigen Datums wird angezeigt, wie markiert, und finden Sie auch am unteren Rand des Rasters. Sie können dieses Feature ändern, durch Festlegen der <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> und <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> Eigenschaften `false`. Sie können auch Wochennummern zum Kalender hinzufügen, durch Festlegen der <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> Eigenschaft `true`. Durch Festlegen der <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> -Eigenschaft, dass mehrere Monate horizontal und vertikal. Standardmäßig ist Sonntag als erster Tag der Woche angezeigt, aber jeden Tag kann festgelegt werden, mithilfe der <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> Eigenschaft.  
  
 Sie können bestimmte Daten angezeigt werden auch einmalig, monatlich oder jährlich fett festlegen, durch Hinzufügen von <xref:System.DateTime> Objekte die <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>, und <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> Eigenschaften. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen einzelner Tage in mit dem Windows Fettschrift Forms-MonthCalendar-Steuerelement](display-specific-days-in-bold-with-wf-monthcalendar-control.md).  
  
 Die wichtigste Eigenschaft von der <xref:System.Windows.Forms.MonthCalendar> Steuerelement <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, den Datumsbereich, der im Steuerelement ausgewählt. Die <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> Wert darf nicht, überschreiten die maximale Anzahl von Tagen an, die ausgewählt werden können, legen Sie in der <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> Eigenschaft. Die frühesten und späteste Datumsangaben, die der Benutzer auswählen kann, hängen von der <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> und <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> Eigenschaften.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.MonthCalendar>
- [MonthCalendar-Steuerelement](monthcalendar-control-windows-forms.md)
