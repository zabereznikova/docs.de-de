---
title: "Gewusst wie: Suchen von Elementen, die mit einer DataTemplate generiert wurden | Microsoft Docs"
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
  - "DataTemplate"
  - "Suchen von DataTemplate-Elementen"
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Suchen von Elementen, die mit einer DataTemplate generiert wurden
In diesem Beispiel wird gezeigt, wie Sie nach Elementen suchen, die von einer <xref:System.Windows.DataTemplate> generiert wurden.  
  
## Beispiel  
 In diesem Beispiel ist ein <xref:System.Windows.Controls.ListBox> an einige [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Daten gebunden:  
  
 [!code-xml[FindGeneratedItems#LB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 Das <xref:System.Windows.Controls.ListBox> verwendet die folgende <xref:System.Windows.DataTemplate>:  
  
 [!code-xml[FindGeneratedItems#DT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Wenn Sie das <xref:System.Windows.Controls.TextBlock>\-Element abrufen möchten, das von der <xref:System.Windows.DataTemplate> von einem bestimmten <xref:System.Windows.Controls.ListBoxItem> generiert wurde, müssen Sie das <xref:System.Windows.Controls.ListBoxItem> ermitteln, das <xref:System.Windows.Controls.ContentPresenter>\-Element in diesem <xref:System.Windows.Controls.ListBoxItem> suchen und dann <xref:System.Windows.FrameworkTemplate.FindName%2A> für die <xref:System.Windows.DataTemplate> aufrufen, die für dieses <xref:System.Windows.Controls.ContentPresenter>\-Element festgelegt ist.  Das folgende Beispiel zeigt, wie diese Schritte ausgeführt werden.  Zu Demonstrationszwecken wird im folgenden Beispiel ein Meldungsfeld erstellt, mit dem der Textinhalt des mit der <xref:System.Windows.DataTemplate> generierten Textblocks angezeigt wird.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Es folgt die Implementierung von `FindVisualChild`, die die <xref:System.Windows.Media.VisualTreeHelper>\-Methoden verwendet:  
  
 [!code-csharp[FindGeneratedItems#FVC](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## Siehe auch  
 [Gewusst wie: Suchen von Elementen, die mit einer ControlTemplate generiert wurden](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [WPF\-XAML\-Namescopes](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)   
 [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)