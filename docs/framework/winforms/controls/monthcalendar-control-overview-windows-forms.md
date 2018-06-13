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
ms.openlocfilehash: 7ed917afe2640fe2ffef4904a3795c5f0e84ded9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537407"
---
# <a name="monthcalendar-control-overview-windows-forms"></a>Übersicht über das MonthCalendar-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.MonthCalendar> Steuerelement verfügt über eine intuitive grafische Oberfläche für Benutzer anzeigen und Festlegen von Datumsinformationen. Das Steuerelement zeigt einen Kalender: ein Raster mit die nummerierten Tage des Monats, in den Spalten unterhalb der Tage der Woche, mit dem ausgewählten Bereich der Datumsangaben hervorgehoben angeordnet sind. Sie können einen anderen Monat auswählen, durch Klicken auf die Pfeilschaltflächen auf beiden Seiten der Überschrift für den Monat. Im Gegensatz zu ähnlichen <xref:System.Windows.Forms.DateTimePicker> -Steuerelement, Sie können mehr als ein Datum mit diesem Steuerelement auswählen. Weitere Informationen zu den <xref:System.Windows.Forms.DateTimePicker> steuern, finden Sie unter [DateTimePicker-Steuerelement](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md).  
  
## <a name="configuring-the-monthcalendar-control"></a>Konfigurieren des MonthCalendar-Steuerelements  
 Die <xref:System.Windows.Forms.MonthCalendar> Darstellung des Steuerelements ist hochgradig konfigurierbar. Standardmäßig des heutigen Datums wird angezeigt, wie markiert und wird auch im unteren Bereich des Rasters aufgeführt. Sie können diese Funktion ändern, durch Festlegen der <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> und <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> Eigenschaften `false`. Sie können auch Wochennummern auf den Kalender hinzufügen, indem Sie festlegen der <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> Eigenschaft `true`. Durch Festlegen der <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> -Eigenschaft, können Sie mehrere Monate horizontal und vertikal angezeigt haben. Standardmäßig ist Sonntag als erster Tag der Woche angezeigt, aber einem beliebigen Tag kann gekennzeichnet werden, mithilfe der <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> Eigenschaft.  
  
 Sie können bestimmte Datumsangaben angezeigt werden auch einmalig, monatlich oder jährlich fett festlegen, durch Hinzufügen von <xref:System.DateTime> -Objekte und die <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>, und <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> Eigenschaften. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md).  
  
 Die wichtigste Eigenschaft die <xref:System.Windows.Forms.MonthCalendar> Steuerelement <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, den Datumsbereich, der im Steuerelement ausgewählt. Die <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> Wert darf nicht, überschreiten die maximale Anzahl von Tagen, die ausgewählt werden können, legen Sie in der <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> Eigenschaft. Die früheste und die neuesten Daten, die der Benutzer auswählen kann gemäß den <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> und <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> Eigenschaften.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MonthCalendar>  
 [MonthCalendar-Steuerelement](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
