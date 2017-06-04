---
title: "DataGrid-Stile und -Vorlagen | Microsoft Docs"
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
  - "ControlTemplate [WPF], DataGrid"
  - "DataGrid [WPF], Stile und Vorlagen"
  - "Bestandteile [WPF], DataGrid"
  - "Zustände [WPF], DataGrid"
  - "Formate [WPF], DataGrid"
  - "Vorlagen [WPF], DataGrid"
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# DataGrid-Stile und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.DataGrid>\-Steuerelement beschrieben.  Sie können die standardmäßige <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement ein individuelles Aussehen zu verleihen.  Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## DataGrid\-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.DataGrid>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|Bestandteil|Typ|Beschreibung|  
|PART\_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|Die Zeile, die die Spaltenüberschriften enthält.|  
  
 Wenn Sie eine <xref:System.Windows.Controls.ControlTemplate> für ein <xref:System.Windows.Controls.DataGrid> erstellen, kann die Vorlage einen <xref:System.Windows.Controls.ItemsPresenter> in einem <xref:System.Windows.Controls.ScrollViewer> enthalten.  \(Der <xref:System.Windows.Controls.ItemsPresenter> zeigt jedes Element im <xref:System.Windows.Controls.DataGrid> an. Der <xref:System.Windows.Controls.ScrollViewer> ermöglicht einen Bildlauf im Steuerelement\).  Wenn der <xref:System.Windows.Controls.ItemsPresenter> kein direkt untergeordnetes Element des <xref:System.Windows.Controls.ScrollViewer> ist, müssen Sie dem <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter` zuweisen.  
  
 Die Standardvorlage für das <xref:System.Windows.Controls.DataGrid> enthält ein <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement.  Weitere Informationen zu den vom <xref:System.Windows.Controls.ScrollViewer> definierten Teilen finden Sie unter [ScrollViewer\-Stile und \-Vorlagen](../../../../docs/framework/wpf/controls/scrollviewer-styles-and-templates.md).  
  
## DataGrid\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.DataGrid>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Normal|CommonStates|Der Standardzustand.|  
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|  
|InvalidFocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt den Fokus.|  
|InvalidUnfocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt keinen Fokus.|  
|Valid|ValidationStates|Das Steuerelement ist gültig.|  
  
## DataGridCell\-Teile  
 Das <xref:System.Windows.Controls.DataGridCell>\-Element verfügt über keine benannten Teile.  
  
## DataGridCell\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.DataGridCell>\-Element aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Normal|CommonStates|Der Standardzustand.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über der Zelle.|  
|Focused|FocusStates|Die Zelle hat den Fokus.|  
|Unfocused|FocusStates|Die Zelle hat nicht den Fokus.|  
|Aktuell|CurrentStates|Die Zelle ist die aktive Zelle.|  
|Regulär|CurrentStates|Die Zelle ist nicht die aktive Zelle.|  
|Anzeige|InteractionStates|Die Zelle ist im Anzeigemodus.|  
|Bearbeiten|InteractionStates|Die Zelle ist im Bearbeitungsmodus.|  
|Ausgewählt|SelectionStates|Die Zelle ist ausgewählt.|  
|Nicht ausgewählt|SelectionStates|Die Zelle ist nicht ausgewählt.|  
|InvalidFocused|ValidationStates|Die Zelle ist ungültig und hat den Fokus.|  
|InvalidUnfocused|ValidationStates|Die Zelle ist ungültig und hat nicht den Fokus.|  
|Valid|ValidationStates|Die Zelle ist gültig.|  
  
## DataGridRow\-Teile  
 Das <xref:System.Windows.Controls.DataGridRow>\-Element verfügt über keine benannten Teile.  
  
## DataGridRow\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.DataGridRow>\-Element aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Normal|CommonStates|Der Standardzustand.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über der Zeile.|  
|MouseOver\_Editing|CommonStates|Der Mauszeiger befindet sich über der Zeile, und die Zeile ist im Bearbeitungsmodus.|  
|MouseOver\_Selected|CommonStates|Der Mauszeiger befindet sich über der Zeile, und die Zeile ist ausgewählt.|  
|MouseOver\_Unfocused\_Editing|CommonStates|Der Mauszeiger befindet sich über der Zeile, die Zeile ist im Bearbeitungsmodus und hat nicht den Fokus.|  
|MouseOver\_Unfocused\_Selected|CommonStates|Der Mauszeiger befindet sich über der Zeile, die Zeile ist ausgewählt und hat nicht den Fokus.|  
|Normal\_AlternatingRow|CommonStates|Die Zeile ist eine abwechselnde Zeile.|  
|Normal\_Editing|CommonStates|Die Zeile ist im Bearbeitungsmodus.|  
|Normal\_Selected|CommonStates|Die Zeile ist ausgewählt.|  
|Unfocused\_Editing|CommonStates|Die Zeile ist im Bearbeitungsmodus und hat nicht den Fokus.|  
|Unfocused\_Selected|CommonStates|Die Zeile ist ausgewählt und hat nicht den Fokus.|  
|InvalidFocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt den Fokus.|  
|InvalidUnfocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt keinen Fokus.|  
|Valid|ValidationStates|Das Steuerelement ist gültig.|  
  
## DataGridRowHeader\-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Primitives.DataGridRowHeader>\-Element aufgelistet.  
  
||||  
|-|-|-|  
|Bestandteil|Typ|Beschreibung|  
|PART\_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Das Element, das verwendet wird, um die Größe der Zeilenüberschrift von oben zu ändern.|  
|PART\_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Das Element, das verwendet wird, um die Größe der Zeilenüberschrift von unten zu ändern.|  
  
## DataGridRowHeader\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.DataGridRowHeader>\-Element aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Normal|CommonStates|Der Standardzustand.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über der Zeile.|  
|MouseOver\_CurrentRow|CommonStates|Der Mauszeiger befindet sich über der Zeile, und die Zeile ist die aktive Zeile.|  
|MouseOver\_CurrentRow\_Selected|CommonStates|Der Mauszeiger befindet sich über der Zeile, die Zeile ist die aktive Zeile und ist ausgewählt.|  
|MouseOver\_EditingRow|CommonStates|Der Mauszeiger befindet sich über der Zeile, und die Zeile ist im Bearbeitungsmodus.|  
|MouseOver\_Selected|CommonStates|Der Mauszeiger befindet sich über der Zeile, und die Zeile ist ausgewählt.|  
|MouseOver\_Unfocused\_CurrentRow\_Selected|CommonStates|Der Mauszeiger befindet sich über der Zeile, die Zeile ist die aktive Zeile, ist ausgewählt und hat nicht den Fokus.|  
|MouseOver\_Unfocused\_EditingRow|CommonStates|Der Mauszeiger befindet sich über der Zeile, die Zeile ist im Bearbeitungsmodus und hat nicht den Fokus.|  
|MouseOver\_Unfocused\_Selected|CommonStates|Der Mauszeiger befindet sich über der Zeile, die Zeile ist ausgewählt und hat nicht den Fokus.|  
|Normal\_CurrentRow|CommonStates|Die Zeile ist die aktive Zeile.|  
|Normal\_CurrentRow\_Selected|CommonStates|Die Zeile ist die aktive Zeile und ist ausgewählt.|  
|Normal\_EditingRow|CommonStates|Die Zeile ist im Bearbeitungsmodus.|  
|Normal\_Selected|CommonStates|Die Zeile ist ausgewählt.|  
|Unfocused\_CurrentRow\_Selected|CommonStates|Die Zeile ist die aktive Zeile, ist ausgewählt und hat nicht den Fokus.|  
|Unfocused\_EditingRow|CommonStates|Die Zeile ist im Bearbeitungsmodus und hat nicht den Fokus.|  
|Unfocused\_Selected|CommonStates|Die Zeile ist ausgewählt und hat nicht den Fokus.|  
|InvalidFocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt den Fokus.|  
|InvalidUnfocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt keinen Fokus.|  
|Valid|ValidationStates|Das Steuerelement ist gültig.|  
  
## DataGridColumnHeadersPresenter\-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>\-Element aufgelistet.  
  
||||  
|-|-|-|  
|Bestandteil|Typ|Beschreibung|  
|PART\_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|Der Platzhalter für Spaltenheader.|  
  
## DataGridColumnHeadersPresenter\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>\-Element aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|InvalidFocused|ValidationStates|Die Zelle ist ungültig und hat den Fokus.|  
|InvalidUnfocused|ValidationStates|Die Zelle ist ungültig und hat nicht den Fokus.|  
|Valid|ValidationStates|Die Zelle ist gültig.|  
  
## DataGridColumnHeader\-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>\-Element aufgelistet.  
  
||||  
|-|-|-|  
|Bestandteil|Typ|Beschreibung|  
|PART\_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Das Element, das verwendet wird, um die Größe der Spaltenüberschrift von links zu ändern.|  
|PART\_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Das Element, das verwendet wird, um die Größe der Spaltenüberschrift von rechts zu ändern.|  
  
## DataGridColumnHeader\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>\-Element aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Normal|CommonStates|Der Standardzustand.|  
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|  
|Pressed|CommonStates|Das Steuerelement wird gedrückt.|  
|SortAscending|SortStates|Die Spalte ist in aufsteigender Reihenfolge sortiert.|  
|SortDescending|SortStates|Die Spalte ist in absteigender Reihenfolge sortiert.|  
|Unsorted|SortStates|Die Spalte ist nicht sortiert.|  
|InvalidFocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt den Fokus.|  
|InvalidUnfocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt keinen Fokus.|  
|Valid|ValidationStates|Das Steuerelement ist gültig.|  
  
## Beispiel für eine DataGrid\-ControlTemplate  
 Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.DataGrid>\-Steuerelement und die zugehörigen Typen definiert wird.  
  
 [!code-xml[ControlTemplateExamples#DataGrid](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
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