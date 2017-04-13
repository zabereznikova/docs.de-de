---
title: "TreeView-Format und -Vorlagen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ControlTemplate [WPF], TreeView"
  - "Bestandteile [WPF], TreeView"
  - "Zustände [WPF], TreeView"
  - "Formate [WPF], TreeView"
  - "Vorlagen [WPF], TreeView"
  - "TreeView [WPF], Stile und Vorlagen"
ms.assetid: a49adb77-0202-4caa-b94a-8bb110d7fa9a
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# TreeView-Format und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.TreeView>\-Steuerelement beschrieben.  Sie können die standardmäßige <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement ein individuelles Aussehen zu verleihen.  Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## TreeView\-Teile  
 Das <xref:System.Windows.Controls.TreeView>\-Steuerelement verfügt nicht über benannte Teile.  
  
 Wenn Sie eine <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.TreeView> erstellen, kann die Vorlage einen <xref:System.Windows.Controls.ItemsPresenter> in einem <xref:System.Windows.Controls.ScrollViewer> enthalten.  \(Der <xref:System.Windows.Controls.ItemsPresenter> zeigt jedes Element im <xref:System.Windows.Controls.TreeView> an. Der <xref:System.Windows.Controls.ScrollViewer> ermöglicht einen Bildlauf im Steuerelement\).  Wenn der <xref:System.Windows.Controls.ItemsPresenter> kein direkt untergeordnetes Element des <xref:System.Windows.Controls.ScrollViewer> ist, müssen Sie dem <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter` zuweisen.  
  
## TreeView\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.TreeView>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Valid|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation>\-Klasse, und die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement den Fokus.|  
|InvalidUnfocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement nicht den Fokus.|  
  
## TreeViewItem\-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement aufgelistet.  
  
|Bestandteil|Typ|Beschreibung|  
|-----------------|---------|------------------|  
|PART\_Header|<xref:System.Windows.FrameworkElement>|Ein visuelles Element, das den Überschriftsinhalt des <xref:System.Windows.Controls.TreeView>\-Steuerelements enthält.|  
  
## TreeViewItem\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement aufgelistet.  
  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|-----------------------|----------------------------|------------------|  
|Normal|CommonStates|Der Standardzustand.|  
|MouseOver|CommonStates|Der Mauszeiger befindet sich über dem <xref:System.Windows.Controls.TreeViewItem>.|  
|Disabled|CommonStates|Das <xref:System.Windows.Controls.TreeViewItem> ist deaktiviert.|  
|Focused|FocusStates|Das <xref:System.Windows.Controls.TreeViewItem> hat den Fokus.|  
|Unfocused|FocusStates|Das <xref:System.Windows.Controls.TreeViewItem> hat nicht den Fokus.|  
|Erweitert|ExpansionStates|Das <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement ist erweitert.|  
|Collapsed|ExpansionStates|Das <xref:System.Windows.Controls.TreeViewItem>\-Steuerelement ist reduziert.|  
|HasItems|HasItemsStates|Das <xref:System.Windows.Controls.TreeViewItem> verfügt über Elemente.|  
|NoItems|HasItemsStates|Das <xref:System.Windows.Controls.TreeViewItem> verfügt nicht über Elemente.|  
|Ausgewählt|SelectionStates|Das <xref:System.Windows.Controls.TreeViewItem> ist ausgewählt.|  
|SelectedInactive|SelectionStates|Das <xref:System.Windows.Controls.TreeViewItem> ist ausgewählt, aber nicht aktiv.|  
|Nicht ausgewählt|SelectionStates|Das <xref:System.Windows.Controls.TreeViewItem> ist nicht ausgewählt.|  
|Valid|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation>\-Klasse, und die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement den Fokus.|  
|InvalidUnfocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement nicht den Fokus.|  
  
## Beispiel für ein TreeView\-ControlTemplate  
 Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.TreeView>\-Steuerelement und die zugehörigen Typen definiert wird.  
  
 [!code-xml[ControlTemplateExamples#TreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
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