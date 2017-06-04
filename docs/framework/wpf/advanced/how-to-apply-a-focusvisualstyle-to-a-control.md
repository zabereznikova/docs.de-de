---
title: "Gewusst wie: Anwenden eines FocusVisualStyle auf ein Steuerelement | Microsoft Docs"
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
  - "FocusVisualStyle-Eigenschaft"
  - "Eigenschaften, FocusVisualStyle"
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Anwenden eines FocusVisualStyle auf ein Steuerelement
Dieses Beispiel veranschaulicht, wie ein Stil für den visuellen Fokus im Allgemeinen erstellt und über die <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>\-Eigenschaft auf ein Steuerelement angewendet wird.  
  
## Beispiel  
 Das folgende Beispiel definiert einen Stil zum Erstellen einer zusätzlichen Zusammensetzung von Steuerelementen, wenn das entsprechende Steuerelement in der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] den Tastaturfokus erhält.  Dies wird erreicht, indem ein Stil mit einer <xref:System.Windows.Controls.ControlTemplate> definiert wird und dieser Stil anschließend beim Festlegen der <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>\-Eigenschaft als Ressource referenziert wird.  
  
 Ein externes Rechteck, das einem Rahmen ähnelt, wird außerhalb des rechteckigen Bereichs platziert.  Sofern nicht anderweitig modifiziert, werden für die Größenfestlegung des Stils die <xref:System.Windows.FrameworkElement.ActualHeight%2A> und die <xref:System.Windows.FrameworkElement.ActualWidth%2A> des rechteckigen Steuerelements verwendet, auf das der Stil für den visuellen Fokus angewendet wird.  In diesem Beispiel werden negative Werte für den <xref:System.Windows.FrameworkElement.Margin%2A> festgelegt, damit der Rahmen etwas außerhalb des fokussierten Steuerelements dargestellt wird.  
  
 [!code-xml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 Ein <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> wirkt additiv zu jedem Vorlagenstil für Steuerelemente, der aus einem expliziten Stil oder einem Designstil stammt. Der primäre Stil für ein Steuerelement kann weiterhin über eine <xref:System.Windows.Controls.ControlTemplate> und das Festlegen dieses Stils für die <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft erstellt werden.  
  
 Stile für den visuellen Fokus sollten konsistent in einem Design oder einer Benutzeroberfläche verwendet werden. Es empfiehlt sich nicht, verschiedene Stile für jedes fokussierbare Element zu verwenden.  Ausführlichere Informationen hierzu finden Sie unter [Fokusstile in Steuerelementen und FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## Siehe auch  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Fokusstile in Steuerelementen und FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)