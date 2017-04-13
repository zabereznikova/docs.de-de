---
title: "ComboBox-Stile und -Vorlagen | Microsoft Docs"
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
  - "ComboBox [WPF], Stile und Vorlagen"
  - "ControlTemplate [WPF], ComboBox"
  - "Bestandteile [WPF], ComboBox"
  - "Zustände [WPF], ComboBox"
  - "Formate [WPF], ComboBox"
  - "Vorlagen [WPF], ComboBox"
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# ComboBox-Stile und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.ComboBox>\-Steuerelement beschrieben.  Sie können die standardmäßige <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement ein individuelles Aussehen zu verleihen.  Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## ComboBox\-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.ComboBox>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|Bestandteil|Typ|Beschreibung|  
|PART\_EditableTextBox|<xref:System.Windows.Controls.TextBox>|Enthält den Text des <xref:System.Windows.Controls.ComboBox>.|  
|PART\_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Das Dropdownelement, das die Elemente des Kombinationsfelds enthält.|  
  
 Wenn Sie eine <xref:System.Windows.Controls.ControlTemplate> für ein <xref:System.Windows.Controls.ComboBox> erstellen, kann die Vorlage einen <xref:System.Windows.Controls.ItemsPresenter> in einem <xref:System.Windows.Controls.ScrollViewer> enthalten.  \(Der <xref:System.Windows.Controls.ItemsPresenter> zeigt jedes Element im <xref:System.Windows.Controls.ComboBox> an. Der <xref:System.Windows.Controls.ScrollViewer> ermöglicht einen Bildlauf im Steuerelement\).  Wenn der <xref:System.Windows.Controls.ItemsPresenter> kein direkt untergeordnetes Element des <xref:System.Windows.Controls.ScrollViewer> ist, müssen Sie dem <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter` zuweisen.  
  
## ComboBox\-Zustände  
 In der folgenden Tabelle sind die Zustände für das <xref:System.Windows.Controls.ComboBox>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Normal|CommonStates|Der Standardzustand.|  
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über dem <xref:System.Windows.Controls.ComboBox>\-Steuerelement.|  
|Focused|FocusStates|Das Steuerelement besitzt den Fokus.|  
|Unfocused|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
|FocusedDropDown|FocusStates|Das Dropdownelement für <xref:System.Windows.Controls.ComboBox> besitzt den Fokus.|  
|Valid|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation>\-Klasse, und die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement den Fokus.|  
|InvalidUnfocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement nicht den Fokus.|  
|Bearbeitbar|EditStates|Die <xref:System.Windows.Controls.ComboBox.IsEditable%2A>\-Eigenschaft ist `true`.|  
|Uneditable|EditStates|Die <xref:System.Windows.Controls.ComboBox.IsEditable%2A>\-Eigenschaft ist `false`.|  
  
## ComboBoxItem\-Teile  
 Das <xref:System.Windows.Controls.ComboBoxItem>\-Steuerelement verfügt nicht über benannte Teile.  
  
## ComboBoxItem\-Zustände  
 In der folgenden Tabelle sind die Zustände für das <xref:System.Windows.Controls.ComboBoxItem>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Normal|CommonStates|Der Standardzustand.|  
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über dem <xref:System.Windows.Controls.ComboBox>\-Steuerelement.|  
|Focused|FocusStates|Das Steuerelement besitzt den Fokus.|  
|Unfocused|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
|Ausgewählt|SelectionStates|Das Element ist derzeit ausgewählt.|  
|Nicht ausgewählt|SelectionStates|Das Element ist nicht ausgewählt.|  
|SelectedUnfocused|SelectionStates|Das Element ist ausgewählt, besitzt aber den Fokus nicht.|  
|Valid|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation>\-Klasse, und die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement den Fokus.|  
|InvalidUnfocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement nicht den Fokus.|  
  
## Beispiel für ein Kombinationsfeld\-ControlTemplate  
 Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.ComboBox>\-Steuerelement und zugehörige Typen definiert wird.  
  
 [!code-xml[ControlTemplateExamples#ComboBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
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