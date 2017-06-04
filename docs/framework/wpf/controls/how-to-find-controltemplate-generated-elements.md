---
title: "Gewusst wie: Suchen von Elementen, die mit einer ControlTemplate generiert wurden | Microsoft Docs"
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
  - "ControlTemplates [WPF], Suchen von Elementen"
  - "Suchen von ControlTemplate-Elementen"
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Suchen von Elementen, die mit einer ControlTemplate generiert wurden
In diesem Beispiel wird gezeigt, wie Sie nach Elementen suchen, die von einer <xref:System.Windows.Controls.ControlTemplate> generiert wurden.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Stil veranschaulicht, der eine einfache <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Button>\-Klasse erstellt:  
  
 [!code-xml[FindGeneratedItems#CT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Um ein Element in der Vorlage zu suchen, nachdem die Vorlage angewendet wurde, können Sie die <xref:System.Windows.FrameworkTemplate.FindName%2A>\-Methode von der <xref:System.Windows.Controls.Control.Template%2A> aufrufen.  Im folgenden Beispiel wird ein Meldungsfeld erstellt, mit dem der tatsächliche Wert der <xref:System.Windows.Controls.Grid>\-Breite in der Steuerelementvorlage angezeigt wird:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## Siehe auch  
 [Suchen von Elementen, die mit einer DataTemplate generiert wurden](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [WPF\-XAML\-Namescopes](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)   
 [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)