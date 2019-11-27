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
ms.openlocfilehash: 64cb62a3459a3eeea6aa5e91b433a58a88ab08ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283557"
---
# <a name="calendar-styles-and-templates"></a>Calendar-Stile und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Calendar>-Steuerelement beschrieben. Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen. Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.  
  
## <a name="calendar-parts"></a>Kalender Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Calendar>-Steuerelement aufgelistet.  
  
|-Komponente|Typ|Beschreibung|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|Der derzeit auf dem <xref:System.Windows.Controls.Calendar>angezeigte Monat oder Jahr.|  
|PART_Root|<xref:System.Windows.Controls.Panel>|Der Bereich, der die <xref:System.Windows.Controls.Primitives.CalendarItem>enthält.|  
  
## <a name="calendar-states"></a>Kalender Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Calendar>-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
  
## <a name="calendaritem-parts"></a>CalendarItem-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Primitives.CalendarItem>-Steuerelement aufgelistet.  
  
|-Komponente|Typ|Beschreibung|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|Der Stamm des Steuer Elements.|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|Die Schaltfläche, die die vorherige Seite des Kalenders anzeigt, wenn darauf geklickt wird.|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|Die Schaltfläche, die die nächste Seite des Kalenders anzeigt, wenn darauf geklickt wird.|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|Die Schaltfläche, die das Wechseln zwischen Monats Modus, Jahr Modus und Jahrzehnt Modus ermöglicht.|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|Hostet den Inhalt im Monats Modus.|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|Hostet den Inhalt im Jahr-oder Jahrzehnten-Modus.|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|Das Overlay für den deaktivierten Zustand.|  
|Daytitletemplate|<xref:System.Windows.DataTemplate>|Der <xref:System.Windows.DataTemplate>, der die visuelle Struktur beschreibt.|  
  
## <a name="calendaritem-states"></a>CalendarItem-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.CalendarItem>-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normaler Zustand|CommonStates|Der Standardstatus.|  
|Deaktivierter Zustand|CommonStates|Der Status des Kalenders, wenn die <xref:System.Windows.UIElement.IsEnabled%2A>-Eigenschaft `false`ist.|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
  
## <a name="calendardaybutton-parts"></a>CalendarDayButton-Teile  
 Das <xref:System.Windows.Controls.Primitives.CalendarDayButton>-Steuerelement verfügt über keine benannten Teile.  
  
## <a name="calendardaybutton-states"></a>CalendarDayButton-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.CalendarDayButton>-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardstatus.|  
|Deaktiviert|CommonStates|Der <xref:System.Windows.Controls.Primitives.CalendarDayButton> ist deaktiviert.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über dem <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Gedrückt|CommonStates|Der <xref:System.Windows.Controls.Primitives.CalendarDayButton> wird gedrückt.|  
|Ausgewählt|SelectionStates|Die Schaltfläche ist ausgewählt.|  
|Nicht markiert|SelectionStates|Die Schaltfläche ist nicht ausgewählt.|  
|Calendarbuttonfokussierte|CalendarButtonFocusStates|Die Schaltfläche hat den Fokus.|  
|Calendarbuttonunfokussiert|CalendarButtonFocusStates|Die Schaltfläche hat keinen Fokus.|  
|Mit Fokus|FocusStates|Die Schaltfläche hat den Fokus.|  
|Ohne Fokus|FocusStates|Die Schaltfläche hat keinen Fokus.|  
|Aktiv|Activestates|Die Schaltfläche ist aktiv.|  
|Inactive|Activestates|Die Schaltfläche ist inaktiv.|  
|Regularday|Daystates|Die Schaltfläche stellt <xref:System.DateTime.Today%2A?displayProperty=nameWithType>nicht dar.|  
|Heute|Daystates|Die Schaltfläche stellt <xref:System.DateTime.Today%2A?displayProperty=nameWithType>dar.|  
|NormalDay|BlackoutDayStates|Die Schaltfläche stellt einen Tag dar, der ausgewählt werden kann.|  
|BlackoutDay|BlackoutDayStates|Die Schaltfläche stellt einen Tag dar, der nicht ausgewählt werden kann.|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
  
## <a name="calendarbutton-parts"></a>CalendarButton-Teile  
 Das <xref:System.Windows.Controls.Primitives.CalendarButton>-Steuerelement verfügt über keine benannten Teile.  
  
## <a name="calendarbutton-states"></a>CalendarButton-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.CalendarButton>-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardstatus.|  
|Deaktiviert|CommonStates|Der <xref:System.Windows.Controls.Primitives.CalendarButton> ist deaktiviert.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über dem <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Gedrückt|CommonStates|Der <xref:System.Windows.Controls.Primitives.CalendarButton> wird gedrückt.|  
|Ausgewählt|SelectionStates|Die Schaltfläche ist ausgewählt.|  
|Nicht markiert|SelectionStates|Die Schaltfläche ist nicht ausgewählt.|  
|Calendarbuttonfokussierte|CalendarButtonFocusStates|Die Schaltfläche hat den Fokus.|  
|Calendarbuttonunfokussiert|CalendarButtonFocusStates|Die Schaltfläche hat keinen Fokus.|  
|Mit Fokus|FocusStates|Die Schaltfläche hat den Fokus.|  
|Ohne Fokus|FocusStates|Die Schaltfläche hat keinen Fokus.|  
|Aktiv|Activestates|Die Schaltfläche ist aktiv.|  
|Inactive|Activestates|Die Schaltfläche ist inaktiv.|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
  
## <a name="calendar-controltemplate-example"></a>Beispiel für Calendar ControlTemplate  
 Im folgenden Beispiel wird gezeigt, wie Sie eine <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Calendar> Steuerelement und die zugehörigen Typen definieren.  
  
 [!code-xaml[ControlTemplateExamples#Calendar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
 Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Steuerelementformate und -vorlagen](control-styles-and-templates.md)
- [Anpassung von Steuerelementen](control-customization.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Erstellen einer Vorlage für ein Steuerelement](../../../desktop-wpf/themes/how-to-create-apply-template.md)
