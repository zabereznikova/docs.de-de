---
title: "ListBox-Stile und -Vorlagen | Microsoft Docs"
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
  - "ControlTemplate [WPF], ListBox"
  - "ListBox [WPF], Stile und Vorlagen"
  - "Bestandteile [WPF], ListBox"
  - "Zustände [WPF], ListBox"
  - "Formate [WPF], ListBox"
  - "Vorlagen [WPF], ListBox"
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# ListBox-Stile und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.ListBox>\-Steuerelement beschrieben.  Sie können die standardmäßige <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement ein individuelles Aussehen zu verleihen.  Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## ListBox\-Teile  
 Das <xref:System.Windows.Controls.ListBox>\-Steuerelement verfügt nicht über benannte Teile.  
  
 Wenn Sie eine <xref:System.Windows.Controls.ControlTemplate> für ein <xref:System.Windows.Controls.ListBox> erstellen, kann die Vorlage einen <xref:System.Windows.Controls.ItemsPresenter> in einem <xref:System.Windows.Controls.ScrollViewer> enthalten.  \(Der <xref:System.Windows.Controls.ItemsPresenter> zeigt jedes Element im <xref:System.Windows.Controls.ListBox> an. Der <xref:System.Windows.Controls.ScrollViewer> ermöglicht einen Bildlauf im Steuerelement\).  Wenn der <xref:System.Windows.Controls.ItemsPresenter> kein direkt untergeordnetes Element des <xref:System.Windows.Controls.ScrollViewer> ist, müssen Sie dem <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter` zuweisen.  
  
## ListBox\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.ListBox>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Valid|ValidationStates|Das Steuerelement ist gültig.|  
|InvalidFocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt den Fokus.|  
|InvalidUnfocused|ValidationStates|Das Steuerelement ist nicht gültig und besitzt keinen Fokus.|  
  
## ListBoxItem\-Teile  
 Das <xref:System.Windows.Controls.ListBoxItem>\-Steuerelement verfügt über keine benannten Teile.  
  
## ListBoxItem\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.ListBox>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Normal|CommonStates|Der Standardzustand.|  
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|  
|Disabled|CommonStates|Das Element ist deaktiviert.|  
|Focused|FocusStates|Das Element besitzt den Fokus.|  
|Unfocused|FocusStates|Das Element besitzt den Fokus nicht.|  
|Nicht ausgewählt|SelectionStates|Das Element ist derzeit ausgewählt.|  
|Ausgewählt|SelectionStates|Das Element ist nicht ausgewählt.|  
|SelectedUnfocused|SelectionStates|Das Element ist ausgewählt, besitzt aber den Fokus nicht.|  
|Valid|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation>\-Klasse, und die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement den Fokus.|  
|InvalidUnfocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement nicht den Fokus.|  
  
## Beispiel für ein ListBox\-ControlTemplate  
 Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ListBox>\- und <xref:System.Windows.Controls.ListBoxItem>\-Steuerelemente definiert wird.  
  
 [!code-xml[ControlTemplateExamples#ListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
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