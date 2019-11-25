---
title: DataGrid-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], DataGrid
- ControlTemplate [WPF], DataGrid
- DataGrid [WPF], styles and templates
- templates [WPF], DataGrid
- styles [WPF], DataGrid
- parts [WPF], DataGrid
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
ms.openlocfilehash: 066e8c9ce1112399be8128d0821498f0d56a3dc3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283806"
---
# <a name="datagrid-styles-and-templates"></a>DataGrid-Stile und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.DataGrid>-Steuerelement beschrieben. Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen. Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.  
  
## <a name="datagrid-parts"></a>DataGrid-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.DataGrid>-Steuerelement aufgelistet.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|Die Zeile, die die Spaltenheader enthält.|  
  
 Wenn Sie einen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.DataGrid>erstellen, enthält die Vorlage möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb eines <xref:System.Windows.Controls.ScrollViewer>. (Die <xref:System.Windows.Controls.ItemsPresenter> zeigt jedes Element in der <xref:System.Windows.Controls.DataGrid>an; das <xref:System.Windows.Controls.ScrollViewer> ermöglicht das Scrollen im Steuerelement).  Wenn das <xref:System.Windows.Controls.ItemsPresenter> nicht das direkt untergeordnete Element des <xref:System.Windows.Controls.ScrollViewer>ist, müssen Sie dem <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.  
  
 Die Standardvorlage für die <xref:System.Windows.Controls.DataGrid> enthält ein <xref:System.Windows.Controls.ScrollViewer>-Steuerelement. Weitere Informationen zu den von der <xref:System.Windows.Controls.ScrollViewer>definierten Teilen finden Sie unter [ScrollViewer-Stile und-Vorlagen](scrollviewer-styles-and-templates.md).  
  
## <a name="datagrid-states"></a>DataGrid-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.DataGrid>-Steuerelement aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|  
|InvalidFocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt den Fokus.|  
|InvalidUnfocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt keinen Fokus.|  
|Gültig|ValidationStates|Das Steuerelement ist gültig.|  
  
## <a name="datagridcell-parts"></a>DataGridCell-Teile  
 Das <xref:System.Windows.Controls.DataGridCell>-Element verfügt über keine benannten Teile.  
  
## <a name="datagridcell-states"></a>DataGridCell-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.DataGridCell>-Element aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|MouseOver|CommonStates|Der Mauszeiger wird auf der Zelle positioniert.|  
|Mit Fokus|FocusStates|Die Zelle hat den Fokus.|  
|Ohne Fokus|FocusStates|Die Zelle hat keinen Fokus.|  
|Aktuell|Currentstates|Die Zelle ist die aktuelle Zelle.|  
|Regulär|Currentstates|Die Zelle ist nicht die aktuelle Zelle.|  
|Anzeige|Interaktionstates|Die Zelle befindet sich im Anzeigemodus.|  
|Bearbeiten|Interaktionstates|Die Zelle befindet sich im Bearbeitungsmodus.|  
|Ausgewählt|SelectionStates|Die Zelle ist ausgewählt.|  
|Nicht markiert|SelectionStates|Die Zelle ist nicht ausgewählt.|  
|InvalidFocused|ValidationStates|Die Zelle ist ungültig und hat den Fokus.|  
|InvalidUnfocused|ValidationStates|Die Zelle ist ungültig und besitzt keinen Fokus.|  
|Gültig|ValidationStates|Die Zelle ist gültig.|  
  
## <a name="datagridrow-parts"></a>DataGridRow-Teile  
 Das <xref:System.Windows.Controls.DataGridRow>-Element verfügt über keine benannten Teile.  
  
## <a name="datagridrow-states"></a>DataGridRow-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.DataGridRow>-Element aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über der Zeile.|  
|MouseOver_Editing|CommonStates|Der Mauszeiger befindet sich über der Zeile, und die Zeile befindet sich im Bearbeitungsmodus.|  
|MouseOver_Selected|CommonStates|Der Mauszeiger befindet sich über der Zeile, und die Zeile wird ausgewählt.|  
|MouseOver_Unfocused_Editing|CommonStates|Der Mauszeiger befindet sich über der Zeile, die Zeile befindet sich im Bearbeitungsmodus und hat keinen Fokus.|  
|MouseOver_Unfocused_Selected|CommonStates|Der Mauszeiger befindet sich über der Zeile, die Zeile ist ausgewählt und hat keinen Fokus.|  
|Normal_AlternatingRow|CommonStates|Die Zeile ist eine abwechselnde Zeile.|  
|Normal_Editing|CommonStates|Die Zeile befindet sich im Bearbeitungsmodus.|  
|Normal_Selected|CommonStates|Die Zeile ist ausgewählt.|  
|Unfocused_Editing|CommonStates|Die Zeile befindet sich im Bearbeitungsmodus und besitzt keinen Fokus.|  
|Unfocused_Selected|CommonStates|Die Zeile ist ausgewählt und besitzt keinen Fokus.|  
|InvalidFocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt den Fokus.|  
|InvalidUnfocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt keinen Fokus.|  
|Gültig|ValidationStates|Das Steuerelement ist gültig.|  
  
## <a name="datagridrowheader-parts"></a>DataGridRowHeader-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Primitives.DataGridRowHeader>-Element aufgelistet.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Das Element, das verwendet wird, um die Größe des Zeilen Headers vom oberen Rand zu ändern.|  
|PART_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Das Element, das verwendet wird, um die Größe des Zeilen Headers von unten zu ändern.|  
  
## <a name="datagridrowheader-states"></a>DataGridRowHeader-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.DataGridRowHeader>-Element aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über der Zeile.|  
|MouseOver_CurrentRow|CommonStates|Der Mauszeiger befindet sich über der Zeile, und die Zeile ist die aktuelle Zeile.|  
|MouseOver_CurrentRow_Selected|CommonStates|Der Mauszeiger befindet sich über der Zeile, und die Zeile ist aktuell und ausgewählt.|  
|MouseOver_EditingRow|CommonStates|Der Mauszeiger befindet sich über der Zeile, und die Zeile befindet sich im Bearbeitungsmodus.|  
|MouseOver_Selected|CommonStates|Der Mauszeiger befindet sich über der Zeile, und die Zeile wird ausgewählt.|  
|MouseOver_Unfocused_CurrentRow_Selected|CommonStates|Der Mauszeiger befindet sich über der Zeile, die Zeile ist aktuell und ist ausgewählt und besitzt keinen Fokus.|  
|MouseOver_Unfocused_EditingRow|CommonStates|Der Mauszeiger befindet sich über der Zeile, die Zeile befindet sich im Bearbeitungsmodus und hat keinen Fokus.|  
|MouseOver_Unfocused_Selected|CommonStates|Der Mauszeiger befindet sich über der Zeile, die Zeile ist ausgewählt und hat keinen Fokus.|  
|Normal_CurrentRow|CommonStates|Die Zeile ist die aktuelle Zeile.|  
|Normal_CurrentRow_Selected|CommonStates|Die Zeile ist die aktuelle Zeile und wird ausgewählt.|  
|Normal_EditingRow|CommonStates|Die Zeile befindet sich im Bearbeitungsmodus.|  
|Normal_Selected|CommonStates|Die Zeile ist ausgewählt.|  
|Unfocused_CurrentRow_Selected|CommonStates|Die Zeile ist die aktuelle Zeile, ist ausgewählt und besitzt keinen Fokus.|  
|Unfocused_EditingRow|CommonStates|Die Zeile befindet sich im Bearbeitungsmodus und besitzt keinen Fokus.|  
|Unfocused_Selected|CommonStates|Die Zeile ist ausgewählt und besitzt keinen Fokus.|  
|InvalidFocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt den Fokus.|  
|InvalidUnfocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt keinen Fokus.|  
|Gültig|ValidationStates|Das Steuerelement ist gültig.|  
  
## <a name="datagridcolumnheaderspresenter-parts"></a>Datagridcolumnheaderationsenter-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>-Element aufgelistet.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|Der Platzhalter für Spaltenüberschriften.|  
  
## <a name="datagridcolumnheaderspresenter-states"></a>Datagridcolumnheaderationsenter-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>-Element aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|InvalidFocused|ValidationStates|Die Zelle ist ungültig und hat den Fokus.|  
|InvalidUnfocused|ValidationStates|Die Zelle ist ungültig und besitzt keinen Fokus.|  
|Gültig|ValidationStates|Die Zelle ist gültig.|  
  
## <a name="datagridcolumnheader-parts"></a>DataGridColumnHeader-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>-Element aufgelistet.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Das Element, das verwendet wird, um die Größe des Spalten Headers von Links zu ändern.|  
|PART_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Das Element, das verwendet wird, um die Größe des Spalten Headers von rechts zu ändern.|  
  
## <a name="datagridcolumnheader-states"></a>DataGridColumnHeader-Zustände  
 In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>-Element aufgelistet.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|  
|Gedrückt|CommonStates|Das Steuerelement wird gedrückt.|  
|SortAscending|Sortstates|Die Spalte wird in aufsteigender Reihenfolge sortiert.|  
|Sortsteigend|Sortstates|Die Spalte wird in absteigender Reihenfolge sortiert.|  
|Unsortiert|Sortstates|Die Spalte ist nicht sortiert.|  
|InvalidFocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt den Fokus.|  
|InvalidUnfocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt keinen Fokus.|  
|Gültig|ValidationStates|Das Steuerelement ist gültig.|  
  
## <a name="datagrid-controltemplate-example"></a>DataGrid ControlTemplate-Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.DataGrid>-Steuerelement und die zugehörigen Typen definiert werden.  
  
 [!code-xaml[ControlTemplateExamples#DataGrid](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
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
