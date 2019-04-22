---
title: Kalender
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
ms.openlocfilehash: 9a64c6cd6fc1cc53383f2617f7a7a78959e87c4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124786"
---
# <a name="calendar"></a>Kalender
Ein Kalender kann einen Benutzer unter Verwendung einer visuellen Kalenderansicht ein Datum auswählen.  
  
 Ein <xref:System.Windows.Controls.Calendar> -Steuerelement kann allein oder als Teil des Dropdown-Liste verwendet werden, wenn eine <xref:System.Windows.Controls.DatePicker> Steuerelement. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.DatePicker>.  
  
 Die folgende Abbildung zeigt zwei <xref:System.Windows.Controls.Calendar> Steuerelemente, eine Auswahl mit gesperrten Tage und eine ohne.  
  
 ![Monatskalender-Steuerelementen](./media/ndp-calendarcontrols.png "NDP_CalendarControls")  
Calendar-Steuerelemente  
  
 Die folgende Tabelle enthält Informationen zu Aufgaben, die in der Regel zugeordnet sind. die <xref:System.Windows.Controls.Calendar>.  
  
|Aufgabe|Implementierung|  
|----------|--------------------|  
|Geben Sie die Datumsangaben, die nicht ausgewählt werden können.|Verwenden Sie die <xref:System.Windows.Controls.Calendar.BlackoutDates%2A>-Eigenschaft.|  
|Haben die <xref:System.Windows.Controls.Calendar> werden einen Monat, ein ganzes Jahr oder ein Jahrzehnt lang.|Legen Sie die <xref:System.Windows.Controls.Calendar.DisplayMode%2A> Eigenschaft, um Monat, Jahr oder Jahrzehnt.|  
|Geben Sie gibt an, ob der Benutzer ein Datum auswählen kann, einen Datumsbereich oder mehrere Datumsbereiche an.|Verwenden der <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.|  
|Geben Sie den Bereich der Datumsangaben, die die <xref:System.Windows.Controls.Calendar> angezeigt.|Verwenden Sie die <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A>-Eigenschaft und die <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A>-Eigenschaft.|  
|Geben Sie an, ob das aktuelle Datum markiert wird.|Verwenden Sie die <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>-Eigenschaft. In der Standardeinstellung <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> ist `true`.|  
|Ändern der Größe der <xref:System.Windows.Controls.Calendar>.|Verwenden einer <xref:System.Windows.Controls.Viewbox> oder Festlegen der <xref:System.Windows.FrameworkElement.LayoutTransform%2A> Eigenschaft, um eine <xref:System.Windows.Media.ScaleTransform>. Beachten Sie, dass Sie festlegen, die <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften eine <xref:System.Windows.Controls.Calendar>, der tatsächliche Kalender ändert sich nicht auf seine Größe.|  
  
 Die <xref:System.Windows.Controls.Calendar> Steuerelement bietet die Grundlagen zur Navigation mithilfe der Maus oder Tastatur. Die folgende Tabelle enthält die Navigation per Tastatur.  
  
|Tastenkombination|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|Aktion|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|PFEIL|<xref:System.Windows.Controls.CalendarMode.Month>|Änderungen der <xref:System.Windows.Controls.Calendar.SelectedDate%2A> Eigenschaft Wenn die <xref:System.Windows.Controls.Calendar.SelectionMode%2A> Eigenschaft ist nicht festgelegt, um <xref:System.Windows.Controls.CalendarSelectionMode.None>.|  
|PFEIL|<xref:System.Windows.Controls.CalendarMode.Year>|Ändert den Monat des der <xref:System.Windows.Controls.Calendar.DisplayDate%2A> Eigenschaft. Beachten Sie, dass die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> wird nicht geändert.|  
|PFEIL|<xref:System.Windows.Controls.CalendarMode.Decade>|Ändert das Jahr des der <xref:System.Windows.Controls.Calendar.DisplayDate%2A>. Beachten Sie, dass die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> wird nicht geändert.|  
|UMSCHALTTASTE + PFEILTASTE|<xref:System.Windows.Controls.CalendarMode.Month>|Wenn <xref:System.Windows.Controls.Calendar.SelectionMode%2A> ist nicht festgelegt, um <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> oder <xref:System.Windows.Controls.CalendarSelectionMode.None>, den ausgewählten Datumsbereich erstreckt.|  
|START|<xref:System.Windows.Controls.CalendarMode.Month>|Änderungen der <xref:System.Windows.Controls.Calendar.SelectedDate%2A> auf den ersten Tag des aktuellen Monats.|  
|START|<xref:System.Windows.Controls.CalendarMode.Year>|Ändert den Monat des der <xref:System.Windows.Controls.Calendar.DisplayDate%2A> zum ersten Monat des Jahres. Die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> wird nicht geändert.|  
|START|<xref:System.Windows.Controls.CalendarMode.Decade>|Ändert das Jahr des der <xref:System.Windows.Controls.Calendar.DisplayDate%2A> des ersten Jahres von den zehn Jahren. Die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> wird nicht geändert.|  
|ENDE|<xref:System.Windows.Controls.CalendarMode.Month>|Änderungen der <xref:System.Windows.Controls.Calendar.SelectedDate%2A> bis zum letzten Tag des aktuellen Monats.|  
|ENDE|<xref:System.Windows.Controls.CalendarMode.Year>|Ändert den Monat des der <xref:System.Windows.Controls.Calendar.DisplayDate%2A> in den letzten Monat des Jahres. Die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> wird nicht geändert.|  
|ENDE|<xref:System.Windows.Controls.CalendarMode.Decade>|Ändert das Jahr des der <xref:System.Windows.Controls.Calendar.DisplayDate%2A> auf das letzte Jahr von den zehn Jahren. Die <xref:System.Windows.Controls.Calendar.SelectedDate%2A> wird nicht geändert.|  
|STRG+NACH-OBEN|Beliebig|Wechselt zum nächsten größeren <xref:System.Windows.Controls.Calendar.DisplayMode%2A>. Wenn <xref:System.Windows.Controls.Calendar.DisplayMode%2A> bereits <xref:System.Windows.Controls.CalendarMode.Decade>, keine Aktion.|  
|STRG+NACH-UNTEN|Beliebig|Wechselt zum nächsten kleineren <xref:System.Windows.Controls.Calendar.DisplayMode%2A>. Wenn <xref:System.Windows.Controls.Calendar.DisplayMode%2A> bereits <xref:System.Windows.Controls.CalendarMode.Month>, keine Aktion.|  
|LEERTASTE oder EINGABETASTE|<xref:System.Windows.Controls.CalendarMode.Year> oder <xref:System.Windows.Controls.CalendarMode.Decade>|Switches <xref:System.Windows.Controls.Calendar.DisplayMode%2A> auf die <xref:System.Windows.Controls.CalendarMode.Month> oder <xref:System.Windows.Controls.CalendarMode.Year> durch das fokussierte Element dargestellt.|  
  
## <a name="see-also"></a>Siehe auch

- [Steuerelemente](index.md)
- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
