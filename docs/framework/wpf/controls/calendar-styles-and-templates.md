---
title: "Calendar-Stile und -Vorlagen | Microsoft Docs"
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
  - "Kalender [WPF], Stile und Vorlagen"
  - "ControlTemplate [WPF], Kalender"
  - "Bestandteile [WPF], Kalender"
  - "Zustände [WPF], Kalender"
  - "Formate [WPF], Kalender"
  - "Vorlagen [WPF], Kalender"
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Calendar-Stile und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Calendar>\-Steuerelement beschrieben.  Sie können die standardmäßige <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement ein individuelles Aussehen zu verleihen.  Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Calendar\-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Calendar>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|Bestandteil|Typ|Beschreibung|  
|PART\_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|Der aktuell angezeigte Monat oder das aktuell angezeigte Jahr im <xref:System.Windows.Controls.Calendar>.|  
|PART\_Root|<xref:System.Windows.Controls.Panel>|Der Bereich, der das <xref:System.Windows.Controls.Primitives.CalendarItem> enthält.|  
  
## Calendar\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.Calendar>\-Steuerelement aufgelistet.  
  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|-----------------------|----------------------------|------------------|  
|Valid|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation>\-Klasse, und die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement den Fokus.|  
|InvalidUnfocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement nicht den Fokus.|  
  
## CalendarItem\-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Primitives.CalendarItem>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|Bestandteil|Typ|Beschreibung|  
|PART\_Root|<xref:System.Windows.FrameworkElement>|Der Stamm des Steuerelements.|  
|PART\_PreviousButton|<xref:System.Windows.Controls.Button>|Die Schaltfläche, die die vorherige Seite des Kalenders anzeigt, wenn darauf geklickt wird.|  
|PART\_NextButton|<xref:System.Windows.Controls.Button>|Die Schaltfläche, die die nächste Seite des Kalenders anzeigt, wenn darauf geklickt wird.|  
|PART\_HeaderButton|<xref:System.Windows.Controls.Button>|Die Schaltfläche, die die Umschaltung zwischen Monatsmodus, Jahresmodus und Jahrzehntmodus ermöglicht.|  
|PART\_MonthView|<xref:System.Windows.Controls.Grid>|Hostet den Inhalt im Monatsmodus.|  
|PART\_YearView|<xref:System.Windows.Controls.Grid>|Hostet den Inhalt im Jahres\- oder Jahrzehntmodus.|  
|PART\_DisabledVisual|<xref:System.Windows.FrameworkElement>|Das Overlay für den deaktivierten Zustand.|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|Die <xref:System.Windows.DataTemplate>, die die visuelle Struktur beschreibt.|  
  
## CalendarItem\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.CalendarItem>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Normal|CommonStates|Der Standardzustand.|  
|Disabled|CommonStates|Der Zustand des Kalenders, wenn die <xref:System.Windows.UIElement.IsEnabled%2A>\-Eigenschaft auf `false` festgelegt ist.|  
|Valid|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation>\-Klasse, und die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement den Fokus.|  
|InvalidUnfocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement nicht den Fokus.|  
|Valid|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation>\-Klasse, und die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement den Fokus.|  
|InvalidUnfocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement nicht den Fokus.|  
  
## CalendarDayButton\-Teile  
 Das <xref:System.Windows.Controls.Primitives.CalendarDayButton>\-Steuerelement verfügt nicht über benannte Teile.  
  
## CalendarDayButton\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.CalendarDayButton>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Normal|CommonStates|Der Standardzustand.|  
|Disabled|CommonStates|Die <xref:System.Windows.Controls.Primitives.CalendarDayButton> ist deaktiviert.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über der <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Pressed|CommonStates|Die <xref:System.Windows.Controls.Primitives.CalendarDayButton> ist aktiviert.|  
|Ausgewählt|SelectionStates|Die Schaltfläche ist ausgewählt.|  
|Nicht ausgewählt|SelectionStates|Die Schaltfläche ist ausgewählt.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Die Schaltfläche besitzt den Fokus.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Die Schaltfläche besitzt den Fokus nicht.|  
|Focused|FocusStates|Die Schaltfläche besitzt den Fokus.|  
|Unfocused|FocusStates|Die Schaltfläche besitzt den Fokus nicht.|  
|Aktiv|ActiveStates|Die Schaltfläche ist aktiv.|  
|Inaktiv|ActiveStates|Die Schaltfläche ist inaktiv.|  
|RegularDay|DayStates|Die Schaltfläche stellt nicht <xref:System.DateTime.Today%2A?displayProperty=fullName> dar.|  
|Today|DayStates|Die Schaltfläche stellt <xref:System.DateTime.Today%2A?displayProperty=fullName> dar.|  
|NormalDay|BlackoutDayStates|Die Schaltfläche stellt einen Tag dar, der ausgewählt werden kann.|  
|BlackoutDay|BlackoutDayStates|Die Schaltfläche stellt einen Tag dar, der nicht ausgewählt werden kann.|  
|Valid|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation>\-Klasse, und die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement den Fokus.|  
|InvalidUnfocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement nicht den Fokus.|  
  
## CalendarButton\-Teile  
 Das <xref:System.Windows.Controls.Primitives.CalendarButton>\-Steuerelement verfügt nicht über benannte Teile.  
  
## CalendarButton\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.CalendarButton>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Normal|CommonStates|Der Standardzustand.|  
|Disabled|CommonStates|Die <xref:System.Windows.Controls.Primitives.CalendarButton> ist deaktiviert.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über der <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Pressed|CommonStates|Die <xref:System.Windows.Controls.Primitives.CalendarButton> ist aktiviert.|  
|Ausgewählt|SelectionStates|Die Schaltfläche ist ausgewählt.|  
|Nicht ausgewählt|SelectionStates|Die Schaltfläche ist ausgewählt.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Die Schaltfläche besitzt den Fokus.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Die Schaltfläche besitzt den Fokus nicht.|  
|Focused|FocusStates|Die Schaltfläche besitzt den Fokus.|  
|Unfocused|FocusStates|Die Schaltfläche besitzt den Fokus nicht.|  
|Aktiv|ActiveStates|Die Schaltfläche ist aktiv.|  
|Inaktiv|ActiveStates|Die Schaltfläche ist inaktiv.|  
|Valid|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation>\-Klasse, und die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement den Fokus.|  
|InvalidUnfocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement nicht den Fokus.|  
  
## Beispiel für eine Calendar\-ControlTemplate  
 Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Calendar>\-Steuerelement und zugehörige Typen definiert wird.  
  
 [!code-xml[ControlTemplateExamples#Calendar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
 Im vorherigen Beispiel werden eine oder mehrere der folgenden Ressourcen verwendet.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter          [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041) .  
  
## Siehe auch  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Steuerelementformate und \-vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)