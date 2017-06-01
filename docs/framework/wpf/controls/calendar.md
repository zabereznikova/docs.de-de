---
title: "Kalender | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Calendar-Steuerelement [WPF]"
  - "Steuerelemente [WPF], Calendar"
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Kalender
Ein Kalender ermöglicht es einem Benutzer, ein Datum anhand einer visuellen Kalenderanzeige auszuwählen.  
  
 Ein <xref:System.Windows.Controls.Calendar>\-Steuerelement kann allein oder als Dropdownteil eines <xref:System.Windows.Controls.DatePicker>\-Steuerelements verwendet werden.  Weitere Informationen finden Sie unter <xref:System.Windows.Controls.DatePicker>.  
  
 Die folgende Abbildung zeigt zwei <xref:System.Windows.Controls.Calendar>\-Steuerelemente, eines mit Auswahlen und Datumsangaben der Stromausfälle und eines ohne.  
  
 ![Calendar&#45;Steuerelemente](../../../../docs/framework/wpf/controls/media/ndp-calendarcontrols.png "NDP\_CalendarControls")  
Kalendersteuerelemente  
  
 Die folgende Tabelle enthält Informationen zu Aufgaben, die dem <xref:System.Windows.Controls.Calendar> in der Regel zugeordnet sind.  
  
|Aufgabe|Implementierung|  
|-------------|---------------------|  
|Geben Sie Daten an, die nicht ausgewählt werden können.|Verwenden Sie die <xref:System.Windows.Controls.Calendar.BlackoutDates%2A>\-Eigenschaft.|  
|Lassen Sie den <xref:System.Windows.Controls.Calendar> einen Monat, ein ganzes Jahr oder ein Jahrzehnt anzeigen.|Legen Sie den Wert der <xref:System.Windows.Controls.Calendar.DisplayMode%2A>\-Eigenschaft auf Monat, Jahr oder Jahrzehnt fest.|  
|Geben Sie an, ob der Benutzer ein Datum, einen Datumsbereich oder mehrere Datumsbereiche auswählen kann.|Verwenden Sie den <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.|  
|Geben Sie den Datumsbereich an, den der <xref:System.Windows.Controls.Calendar> anzeigt.|Verwenden Sie die <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A>\-Eigenschaft und die <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A>\-Eigenschaft.|  
|Geben Sie an, ob das aktuelle Datum hervorgehoben wird.|Verwenden Sie die <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>\-Eigenschaft.  Standardmäßig ist <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> auf `true` festgelegt.|  
|Ändern Sie die Größe des <xref:System.Windows.Controls.Calendar>.|Verwenden Sie ein <xref:System.Windows.Controls.Viewbox>, oder legen Sie die <xref:System.Windows.FrameworkElement.LayoutTransform%2A>\-Eigenschaft auf eine <xref:System.Windows.Media.ScaleTransform> fest.  Beachten Sie, dass der tatsächliche Kalender seine Größe nicht ändert, wenn Sie die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft und die <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft eines <xref:System.Windows.Controls.Calendar> festlegen.|  
  
 Das <xref:System.Windows.Controls.Calendar>\-Steuerelement stellt die grundlegende Navigation per Maus oder Tastatur bereit.  In der folgenden Tabelle wird die Tastaturnavigation zusammengefasst.  
  
|Tastenkombination|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|Aktion|  
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|PFEIL|<xref:System.Windows.Controls.CalendarMode>|Ändert die <xref:System.Windows.Controls.Calendar.SelectedDate%2A>\-Eigenschaft, wenn die <xref:System.Windows.Controls.Calendar.SelectionMode%2A>\-Eigenschaft nicht auf <xref:System.Windows.Controls.CalendarSelectionMode> festgelegt ist.|  
|PFEIL|<xref:System.Windows.Controls.CalendarMode>|Ändert den Monat der <xref:System.Windows.Controls.Calendar.DisplayDate%2A>\-Eigenschaft.  Beachten Sie, dass sich <xref:System.Windows.Controls.Calendar.SelectedDate%2A> nicht ändert.|  
|PFEIL|<xref:System.Windows.Controls.CalendarMode>|Ändert das Jahr des <xref:System.Windows.Controls.Calendar.DisplayDate%2A>.  Beachten Sie, dass sich <xref:System.Windows.Controls.Calendar.SelectedDate%2A> nicht ändert.|  
|UMSCHALT\+PFEIL|<xref:System.Windows.Controls.CalendarMode>|Wenn <xref:System.Windows.Controls.Calendar.SelectionMode%2A> nicht auf <xref:System.Windows.Controls.CalendarSelectionMode> oder <xref:System.Windows.Controls.CalendarSelectionMode> festgelegt ist, wird der Bereich der ausgewählten Datumsangaben erweitert.|  
|POS1|<xref:System.Windows.Controls.CalendarMode>|Ändert das <xref:System.Windows.Controls.Calendar.SelectedDate%2A> in den ersten Tag des aktuellen Monats.|  
|POS1|<xref:System.Windows.Controls.CalendarMode>|Ändert den Monat des <xref:System.Windows.Controls.Calendar.DisplayDate%2A> in den ersten Monat des Jahrs.  Das <xref:System.Windows.Controls.Calendar.SelectedDate%2A> ändert sich nicht.|  
|POS1|<xref:System.Windows.Controls.CalendarMode>|Ändert das Jahr des <xref:System.Windows.Controls.Calendar.DisplayDate%2A> in das erste Jahr des Jahrzehnts.  Das <xref:System.Windows.Controls.Calendar.SelectedDate%2A> ändert sich nicht.|  
|ENDE|<xref:System.Windows.Controls.CalendarMode>|Ändert das <xref:System.Windows.Controls.Calendar.SelectedDate%2A> in den letzten Tag des aktuellen Monats.|  
|ENDE|<xref:System.Windows.Controls.CalendarMode>|Ändert den Monat des <xref:System.Windows.Controls.Calendar.DisplayDate%2A> in den letzten Monat des Jahrs.  Das <xref:System.Windows.Controls.Calendar.SelectedDate%2A> ändert sich nicht.|  
|ENDE|<xref:System.Windows.Controls.CalendarMode>|Ändert das Jahr des <xref:System.Windows.Controls.Calendar.DisplayDate%2A> in das letzte Jahr des Jahrzehnts.  Das <xref:System.Windows.Controls.Calendar.SelectedDate%2A> ändert sich nicht.|  
|STRG\+NACH\-OBEN|Irgendein|Wechselt zum nächstgrößeren <xref:System.Windows.Controls.Calendar.DisplayMode%2A>.  Wenn <xref:System.Windows.Controls.Calendar.DisplayMode%2A> bereits auf <xref:System.Windows.Controls.CalendarMode> festgelegt ist, wird keine Aktion ausgeführt.|  
|STRG\+NACH\-UNTEN|Irgendein|Wechselt zum nächstkleineren <xref:System.Windows.Controls.Calendar.DisplayMode%2A>.  Wenn <xref:System.Windows.Controls.Calendar.DisplayMode%2A> bereits auf <xref:System.Windows.Controls.CalendarMode> festgelegt ist, wird keine Aktion ausgeführt.|  
|LEERTASTE oder EINGABETASTE|<xref:System.Windows.Controls.CalendarMode> oder <xref:System.Windows.Controls.CalendarMode>|Ändert den <xref:System.Windows.Controls.Calendar.DisplayMode%2A> in <xref:System.Windows.Controls.CalendarMode> oder <xref:System.Windows.Controls.CalendarMode>, dargestellt durch das fokussierte Element.|  
  
## Siehe auch  
 [Steuerelemente](../../../../docs/framework/wpf/controls/index.md)   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)