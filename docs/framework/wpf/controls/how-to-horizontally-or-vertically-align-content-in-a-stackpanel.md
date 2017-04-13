---
title: "Gewusst wie: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel | Microsoft Docs"
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
  - "Ausrichten, Inhalt"
  - "Inhaltsausrichtung"
  - "StackPanel-Steuerelement, Inhaltsausrichtung"
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel
In diesem Beispiel wird veranschaulicht, wie die <xref:System.Windows.Controls.StackPanel.Orientation%2A> des Inhalts in einem <xref:System.Windows.Controls.StackPanel>\-Element sowie die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> von untergeordnetem Inhalt angepasst werden kann.  
  
## Beispiel  
 Im folgenden Beispiel werden drei <xref:System.Windows.Controls.ListBox>\-Elemente in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] erstellt.  Jedes <xref:System.Windows.Controls.ListBox>\-Element stellt die möglichen Werte der Eigenschaften <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> eines <xref:System.Windows.Controls.StackPanel>\-Elements dar.  Wenn von einem Benutzer ein Wert in einem der <xref:System.Windows.Controls.ListBox>\-Elemente ausgewählt wird, ändert sich die zugehörige Eigenschaft des <xref:System.Windows.Controls.StackPanel>\-Objekts und seiner untergeordneten <xref:System.Windows.Controls.Button>\-Elemente.  
  
 [!code-xml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 Von der folgenden Code\-Behind\-Datei werden die Änderungen der Ereignisse festgelegt, die den Änderungen der <xref:System.Windows.Controls.ListBox>\-Auswahl zugeordnet sind.  <xref:System.Windows.Controls.StackPanel> wird durch den <xref:System.Windows.FrameworkElement.Name%2A> `sp1` identifiziert.  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.StackPanel>   
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>   
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)