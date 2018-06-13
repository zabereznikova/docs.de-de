---
title: Kalender
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
ms.openlocfilehash: b706ec6236b7e3e10865eee9fd32c2eb5a5e7db2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557705"
---
# <a name="calendar"></a>Kalender
Ein Kalender ermöglicht einem Benutzer ein Datum mit einer Kalenderanzeige visual auswählen.  
  
 Ein <xref:System.Windows.Controls.Calendar> -Steuerelement kann allein oder als Teil einer Dropdownliste verwendet werden, wenn ein <xref:System.Windows.Controls.DatePicker> Steuerelement. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.DatePicker>.  
  
 Die folgende Abbildung zeigt zwei <xref:System.Windows.Controls.Calendar> Steuerelemente, die mit der Auswahl und Datumsangaben der Stromausfälle und eines ohne.  
  
 ![Monatskalender-Steuerelementen](../../../../docs/framework/wpf/controls/media/ndp-calendarcontrols.png "NDP_CalendarControls")  
Calendar-Steuerelemente  
  
 Die folgende Tabelle enthält Informationen zu Aufgaben, die in der Regel zugeordnet sind die <xref:System.Windows.Controls.Calendar>.  
  
|Aufgabe|Implementierung|  
|----------|--------------------|  
|Geben Sie die Datumsangaben, die nicht ausgewählt werden können.|Verwenden Sie die <xref:System.Windows.Controls.Calendar.BlackoutDates%2A>-Eigenschaft.|  
|Haben die <xref:System.Windows.Controls.Calendar> einen Monat, ein ganzes Jahr oder ein Jahrzehnt anzeigen.|Legen Sie die <xref:System.Windows.Controls.Calendar.DisplayMode%2A> Eigenschaft, um Monat, Jahr oder Jahrzehnt.|  
|Geben Sie, ob der Benutzer ein Datum auswählen kann, einen Datumsbereich oder mehrere Datumsbereiche.|Verwenden der <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.|  
|Geben Sie den Bereich der Datumsangaben, die die <xref:System.Windows.Controls.Calendar> angezeigt.|Verwenden Sie die <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A>-Eigenschaft und die <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A>-Eigenschaft.|  
|Geben Sie an, ob das aktuelle Datum hervorgehoben ist.|Verwenden Sie die <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>-Eigenschaft. Standardmäßig <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> ist `true`.|  
|Ändern der Größe der <xref:System.Windows.Controls.Calendar>.|Verwenden einer <xref:System.Windows.Controls.Viewbox> oder Festlegen der <xref:System.Windows.FrameworkElement.LayoutTransform%2A> Eigenschaft, um eine <xref:System.Windows.Media.ScaleTransform>. Beachten Sie, dass, wenn Sie festlegen, die <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften eine <xref:System.Windows.Controls.Calendar>, der tatsächliche Kalender ändert seine Größe nicht.|  
  
 Die <xref:System.Windows.Controls.Calendar> Steuerelement stellt grundlegende Navigation per Maus oder Tastatur. In der folgenden Tabelle werden die Tastaturnavigation zusammengefasst.  
  
|Tastenkombination|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|Aktion|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|PFEIL|<xref:System.Windows.Controls.CalendarMode.Month>|Ändert die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> Eigenschaft Wenn die <xref:System.Windows.Controls.Calendar.SelectionMode%2A> Eigenschaft nicht festgelegt ist, um <xref:System.Windows.Controls.CalendarSelectionMode.None>.|  
|PFEIL|<xref:System.Windows.Controls.CalendarMode.Year>|Ändert den Monat des der <xref:System.Windows.Controls.Calendar.DisplayDate%2A> Eigenschaft. Beachten Sie, dass die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> ändert sich nicht.|  
|PFEIL|<xref:System.Windows.Controls.CalendarMode.Decade>|Ändert das Jahr des der <xref:System.Windows.Controls.Calendar.DisplayDate%2A>. Beachten Sie, dass die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> ändert sich nicht.|  
|UMSCHALTTASTE + PFEILTASTE|<xref:System.Windows.Controls.CalendarMode.Month>|Wenn <xref:System.Windows.Controls.Calendar.SelectionMode%2A> nicht festgelegt ist, um <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> oder <xref:System.Windows.Controls.CalendarSelectionMode.None>, wird der Bereich der ausgewählten Datumsangaben erweitert.|  
|START|<xref:System.Windows.Controls.CalendarMode.Month>|Ändert die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> auf den ersten Tag des aktuellen Monats.|  
|START|<xref:System.Windows.Controls.CalendarMode.Year>|Ändert den Monat des der <xref:System.Windows.Controls.Calendar.DisplayDate%2A> zum ersten Monat des Jahres. Die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> ändert sich nicht.|  
|START|<xref:System.Windows.Controls.CalendarMode.Decade>|Ändert das Jahr des der <xref:System.Windows.Controls.Calendar.DisplayDate%2A> des ersten Jahres von den zehn Jahren. Die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> ändert sich nicht.|  
|ENDE|<xref:System.Windows.Controls.CalendarMode.Month>|Ändert die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> bis zum letzten Tag des aktuellen Monats.|  
|ENDE|<xref:System.Windows.Controls.CalendarMode.Year>|Ändert den Monat des der <xref:System.Windows.Controls.Calendar.DisplayDate%2A> in den letzten Monat des Jahres. Die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> ändert sich nicht.|  
|ENDE|<xref:System.Windows.Controls.CalendarMode.Decade>|Ändert das Jahr des der <xref:System.Windows.Controls.Calendar.DisplayDate%2A> auf das letzte Jahr von den zehn Jahren. Die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> ändert sich nicht.|  
|STRG+NACH-OBEN|Beliebig|Wechselt zum nächsten größeren <xref:System.Windows.Controls.Calendar.DisplayMode%2A>. Wenn <xref:System.Windows.Controls.Calendar.DisplayMode%2A> ist bereits <xref:System.Windows.Controls.CalendarMode.Decade>, keine Aktion.|  
|STRG+NACH-UNTEN|Beliebig|Wechselt zum nächsten kleinere <xref:System.Windows.Controls.Calendar.DisplayMode%2A>. Wenn <xref:System.Windows.Controls.Calendar.DisplayMode%2A> ist bereits <xref:System.Windows.Controls.CalendarMode.Month>, keine Aktion.|  
|LEERTASTE oder EINGABETASTE|<xref:System.Windows.Controls.CalendarMode.Year> oder <xref:System.Windows.Controls.CalendarMode.Decade>|Switches <xref:System.Windows.Controls.Calendar.DisplayMode%2A> auf die <xref:System.Windows.Controls.CalendarMode.Month> oder <xref:System.Windows.Controls.CalendarMode.Year> durch fokussierte Element dargestellt wird.|  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente](../../../../docs/framework/wpf/controls/index.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)
