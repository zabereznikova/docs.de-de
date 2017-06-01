---
title: "Slider-Stile und -Vorlagen | Microsoft Docs"
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
  - "ControlTemplate [WPF], Slider"
  - "Bestandteile [WPF], Slider"
  - "Schieberegler [WPF], Stile und Vorlagen"
  - "Zustände [WPF], Slider"
  - "Formate [WPF], Slider"
  - "Vorlagen [WPF], Slider"
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Slider-Stile und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Slider>\-Steuerelement beschrieben.  Sie können die standardmäßige <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement ein individuelles Aussehen zu verleihen.  Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Slider\-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Slider>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|Bestandteil|Typ|Beschreibung|  
|PART\_Track|<xref:System.Windows.Controls.Primitives.Track>|Der Container für das Element, das die Position der <xref:System.Windows.Controls.Slider> angibt.|  
|PART\_SelectionRange|<xref:System.Windows.FrameworkElement>|Das Element, das einen Auswahlbereich für die <xref:System.Windows.Controls.Slider> anzeigt.  Der Auswahlbereich wird nur angezeigt, wenn die <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A>\-Eigenschaft `true` ist.|  
  
## Slider\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.Slider>\-Steuerelement aufgelistet.  
  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|-----------------------|----------------------------|------------------|  
|Normal|CommonStates|Der Standardzustand.|  
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|  
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|  
|Focused|FocusStates|Das Steuerelement besitzt den Fokus.|  
|Unfocused|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
|Valid|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation>\-Klasse, und die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement den Fokus.|  
|InvalidUnfocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement nicht den Fokus.|  
  
## Beispiel für ein Slider\-ControlTemplate  
 Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Slider>\-Steuerelement definiert wird.  
  
 [!code-xml[ControlTemplateExamples#Slider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
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