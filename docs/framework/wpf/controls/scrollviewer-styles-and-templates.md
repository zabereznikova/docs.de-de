---
title: "ScrollViewer-Stile und -Vorlagen | Microsoft Docs"
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
  - "ControlTemplate [WPF], ScrollViewer"
  - "Bestandteile [WPF], ScrollViewer"
  - "ScrollViewer [WPF], Stile und Vorlagen"
  - "Zustände [WPF], ScrollViewer"
  - "Formate [WPF], ScrollViewer"
  - "Vorlagen [WPF], ScrollViewer"
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# ScrollViewer-Stile und -Vorlagen
In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement beschrieben.  Sie können die standardmäßige <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement ein individuelles Aussehen zu verleihen.  Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## ScrollViewer\-Teile  
 In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|Bestandteil|Typ|Beschreibung|  
|PART\_ScrollContentPresenter|<xref:System.Windows.Controls.ScrollContentPresenter>|Der Platzhalter für Inhalt im <xref:System.Windows.Controls.ScrollViewer>.|  
|PART\_HorizontalScrollBar|<xref:System.Windows.Controls.Primitives.ScrollBar>|Die <xref:System.Windows.Controls.Primitives.ScrollBar>, die verwendet wird, um einen horizontalen Bildlauf des Inhalts durchzuführen.|  
|PART\_VerticalScrollBar|<xref:System.Windows.Controls.Primitives.ScrollBar>|Die <xref:System.Windows.Controls.Primitives.ScrollBar>, die verwendet wird, um einen vertikalen Bildlauf des Inhalts durchzuführen.|  
  
## ScrollViewer\-Zustände  
 In der folgenden Tabelle sind die visuellen Zustände für das <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement aufgelistet.  
  
||||  
|-|-|-|  
|VisualState\-Name|VisualStateGroup\-Name|Beschreibung|  
|Valid|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation>\-Klasse, und die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft ist `false`.|  
|InvalidFocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement den Fokus.|  
|InvalidUnfocused|ValidationStates|Wenn die angefügte <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>\-Eigenschaft `true` ist, hat das Steuerelement nicht den Fokus.|  
  
## Beispiel für ein ScrollViewer\-ControlTemplate  
 Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement definiert wird.  
  
 [!code-xml[ControlTemplateExamples#ScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 Im vorherigen Beispiel werden eine oder mehrere der folgenden Ressourcen verwendet.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## Siehe auch  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Steuerelementformate und \-vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)