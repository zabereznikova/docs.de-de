---
title: ComboBox-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- ComboBox [WPF], styles and templates
- states [WPF], ComboBox
- ControlTemplate [WPF], ComboBox
- styles [WPF], ComboBox
- templates [WPF], ComboBox
- parts [WPF], ComboBox
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
ms.openlocfilehash: 92671001733f525188ba3c7bcf3ed3c55615e301
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283790"
---
# <a name="combobox-styles-and-templates"></a>ComboBox-Stile und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.ComboBox>-Steuerelement beschrieben. Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen. Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.  
  
## <a name="combobox-parts"></a>ComboBox-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.ComboBox>-Steuerelement aufgelistet.  
  
|Segment|Typ|Beschreibung|  
|-|-|-|  
|PART_EditableTextBox|<xref:System.Windows.Controls.TextBox>|Enthält den Text der <xref:System.Windows.Controls.ComboBox>.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Das Dropdown-Element, das die Elemente im Kombinations Feld enthält.|  
  
 Wenn Sie einen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ComboBox>erstellen, enthält die Vorlage möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb eines <xref:System.Windows.Controls.ScrollViewer>. (Die <xref:System.Windows.Controls.ItemsPresenter> zeigt jedes Element in der <xref:System.Windows.Controls.ComboBox>an; das <xref:System.Windows.Controls.ScrollViewer> ermöglicht das Scrollen im Steuerelement).  Wenn das <xref:System.Windows.Controls.ItemsPresenter> nicht das direkt untergeordnete Element des <xref:System.Windows.Controls.ScrollViewer>ist, müssen Sie dem <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.  
  
## <a name="combobox-states"></a>ComboBox-Zustände  
 In der folgenden Tabelle sind die Zustände für das <xref:System.Windows.Controls.ComboBox>-Steuerelement aufgeführt.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über dem <xref:System.Windows.Controls.ComboBox>-Steuerelement.|  
|Mit Fokus|FocusStates|Der Fokus liegt auf dem Steuerelement.|  
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
|FocusedDropDown|FocusStates|Der Dropdown-Vorgang für die <xref:System.Windows.Controls.ComboBox> hat den Fokus.|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
|Bearbeitet|Editstates|Die <xref:System.Windows.Controls.ComboBox.IsEditable%2A>-Eigenschaft ist `true`.|  
|Editierbar|Editstates|Die <xref:System.Windows.Controls.ComboBox.IsEditable%2A>-Eigenschaft ist `false`.|  
  
## <a name="comboboxitem-parts"></a>ComboBoxItem-Teile  
 Das <xref:System.Windows.Controls.ComboBoxItem>-Steuerelement verfügt über keine benannten Teile.  
  
## <a name="comboboxitem-states"></a>ComboBoxItem-Zustände  
 In der folgenden Tabelle sind die Zustände für das <xref:System.Windows.Controls.ComboBoxItem>-Steuerelement aufgeführt.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über dem <xref:System.Windows.Controls.ComboBox>-Steuerelement.|  
|Mit Fokus|FocusStates|Der Fokus liegt auf dem Steuerelement.|  
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
|Ausgewählt|SelectionStates|Das Element ist zurzeit ausgewählt.|  
|Nicht markiert|SelectionStates|Das Element ist nicht ausgewählt.|  
|SelectedUnfocused|SelectionStates|Das Element ist ausgewählt, besitzt jedoch keinen Fokus.|  
|Gültig|ValidationStates|Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.|  
  
## <a name="combobox-controltemplate-example"></a>ComboBox ControlTemplate-Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie eine <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.ComboBox> Steuerelement und die zugehörigen Typen definieren.  
  
 [!code-xaml[ControlTemplateExamples#ComboBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
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
