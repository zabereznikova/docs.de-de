---
title: Calendar-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Calendar
- templates [WPF], Calendar
- states [WPF], Calendar
- parts [WPF], Calendar
- Calendar [WPF], styles and templates
- ControlTemplate [WPF], Calendar
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
ms.openlocfilehash: beba15f12b0ae2b819c641de9af8485767ad1a78
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373412"
---
# <a name="calendar-styles-and-templates"></a>Calendar-Stile und -Vorlagen
In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Calendar> Steuerelement. Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="calendar-parts"></a>Calendar-Teile  
 Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.Calendar> Steuerelement.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|Der derzeit angezeigten Monat oder Jahr auf der <xref:System.Windows.Controls.Calendar>.|  
|PART_Root|<xref:System.Windows.Controls.Panel>|Der Bereich, enthält die <xref:System.Windows.Controls.Primitives.CalendarItem>.|  
  
## <a name="calendar-states"></a>Calendar-Zustände  
 Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Calendar> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.|  
  
## <a name="calendaritem-parts"></a>CalendarItem-Teile  
 Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.Primitives.CalendarItem> Steuerelement.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|Der Stamm des Steuerelements.|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|Die Schaltfläche, die die vorherige Seite des Kalenders anzeigt, wenn darauf geklickt wird.|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|Die Schaltfläche, die die nächste Seite des Kalenders anzeigt, wenn darauf geklickt wird.|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|Die Schaltfläche, die zwischen Monat, Jahresmodus, und Jahrzehntmodus wechseln kann.|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|Hostet den Inhalt im Monatsmodus.|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|Hostet den Inhalt im Jahr oder Jahrzehnt-Modus.|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|Das Overlay für den deaktivierten Zustand.|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|Die <xref:System.Windows.DataTemplate> , die die visuelle Struktur beschreibt.|  
  
## <a name="calendaritem-states"></a>CalendarItem-Zustände  
 Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Primitives.CalendarItem> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal-Status|CommonStates|Der Standardzustand|  
|Zustand "deaktiviert"|CommonStates|Der Status des Kalenders, wenn die <xref:System.Windows.UIElement.IsEnabled%2A> -Eigenschaft ist `false`.|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.|  
  
## <a name="calendardaybutton-parts"></a>CalendarDayButton-Teile  
 Die <xref:System.Windows.Controls.Primitives.CalendarDayButton> Steuerelement enthält keine benannten Teile.  
  
## <a name="calendardaybutton-states"></a>CalendarDayButton-Zustände  
 Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Primitives.CalendarDayButton> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|Deaktiviert|CommonStates|Die <xref:System.Windows.Controls.Primitives.CalendarDayButton> ist deaktiviert.|  
|MouseOver|CommonStates|Befindet sich der Mauszeiger über die <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Gedrückt|CommonStates|Die <xref:System.Windows.Controls.Primitives.CalendarDayButton> gedrückt wird.|  
|Ausgewählt|SelectionStates|Die Schaltfläche ausgewählt ist.|  
|Nicht markiert|SelectionStates|Die Schaltfläche ist nicht ausgewählt.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Die Schaltfläche mit der besitzt Fokus.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Die Schaltfläche mit der keinen Fokus.|  
|Focused|FocusStates|Die Schaltfläche mit der besitzt Fokus.|  
|Ohne Fokus|FocusStates|Die Schaltfläche mit der keinen Fokus.|  
|Aktiv|ActiveStates|Die Schaltfläche ist aktiviert.|  
|inaktiv|ActiveStates|Die Schaltfläche ist inaktiv.|  
|RegularDay|DayStates|Die Schaltfläche mit der stellt keinen dar <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|Heute|DayStates|Stellt die Schaltfläche mit der <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|NormalDay|BlackoutDayStates|Die Schaltfläche darstellt, einen Tag, der ausgewählt werden kann.|  
|BlackoutDay|BlackoutDayStates|Die Schaltfläche darstellt, einen Tag, der nicht ausgewählt werden kann.|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.|  
  
## <a name="calendarbutton-parts"></a>CalendarButton-Teile  
 Die <xref:System.Windows.Controls.Primitives.CalendarButton> Steuerelement enthält keine benannten Teile.  
  
## <a name="calendarbutton-states"></a>CalendarButton-Zustände  
 Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Primitives.CalendarButton> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|Deaktiviert|CommonStates|Die <xref:System.Windows.Controls.Primitives.CalendarButton> ist deaktiviert.|  
|MouseOver|CommonStates|Befindet sich der Mauszeiger über die <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Gedrückt|CommonStates|Die <xref:System.Windows.Controls.Primitives.CalendarButton> gedrückt wird.|  
|Ausgewählt|SelectionStates|Die Schaltfläche ausgewählt ist.|  
|Nicht markiert|SelectionStates|Die Schaltfläche ist nicht ausgewählt.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Die Schaltfläche mit der besitzt Fokus.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Die Schaltfläche mit der keinen Fokus.|  
|Focused|FocusStates|Die Schaltfläche mit der besitzt Fokus.|  
|Ohne Fokus|FocusStates|Die Schaltfläche mit der keinen Fokus.|  
|Aktiv|ActiveStates|Die Schaltfläche ist aktiviert.|  
|inaktiv|ActiveStates|Die Schaltfläche ist inaktiv.|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.|  
  
## <a name="calendar-controltemplate-example"></a>Kalender-ControlTemplate-Beispiel  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Calendar> Steuerelement und die zugehörigen Typen.  
  
 [!code-xaml[ControlTemplateExamples#Calendar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
 Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Steuerelementformate und -vorlagen](control-styles-and-templates.md)
- [Anpassung von Steuerelementen](control-customization.md)
- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
- [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
