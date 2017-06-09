---
title: "Gewusst wie: Sicherstellen, dass ein GridSplitter sichtbar ist | Microsoft Docs"
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
  - "GridSplitter-Steuerelement, Sicherstellen der Sichtbarkeit von"
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Sicherstellen, dass ein GridSplitter sichtbar ist
In diesem Beispiel wird erläutert, wie Sie sicherstellen, dass ein <xref:System.Windows.Controls.GridSplitter>\-Steuerelement nicht von anderen Steuerelementen in einem <xref:System.Windows.Controls.Grid> verdeckt wird.  
  
## Beispiel  
 Die <xref:System.Windows.Controls.Panel.Children%2A>\-Eigenschaften eines <xref:System.Windows.Controls.Grid>\-Elements werden in der Reihenfolge gerendert, in der sie im Markup oder im Code definiert sind.  <xref:System.Windows.Controls.GridSplitter>\-Steuerelemente können von anderen Steuerelementen ausgeblendet werden, wenn Sie sie nicht in der <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung als letzte Elemente definieren, oder wenn Sie anderen Steuerelementen einen höheren <xref:System.Windows.Controls.Panel.ZIndexProperty>\-Wert geben.  
  
 Um zu verhindern, dass <xref:System.Windows.Controls.GridSplitter>\-Steuerelemente verdeckt werden, führen Sie einen der folgenden Schritte aus.  
  
-   Stellen Sie sicher, dass <xref:System.Windows.Controls.GridSplitter>\-Steuerelemente als letzte <xref:System.Windows.Controls.Panel.Children%2A> zum <xref:System.Windows.Controls.Grid> hinzugefügt werden.  Im folgenden Beispiel wird der <xref:System.Windows.Controls.GridSplitter> als letztes Element in der <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung vom <xref:System.Windows.Controls.Grid> dargestellt.  
  
 [!code-xml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   Legen Sie den Wert für <xref:System.Windows.Controls.Panel.ZIndexProperty> des <xref:System.Windows.Controls.GridSplitter> höher als den Wert für ein Steuerelement fest, das es andernfalls verdecken würde.  Im folgenden Beispiel wird dem <xref:System.Windows.Controls.GridSplitter>\-Steuerelement eine höhere <xref:System.Windows.Controls.Panel.ZIndexProperty> als dem <xref:System.Windows.Controls.Button>\-Steuerelement zugewiesen.  
  
 [!code-xml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   Legen Sie Ränder für das Steuerelement fest, das andernfalls den <xref:System.Windows.Controls.GridSplitter> verdecken würde, sodass der <xref:System.Windows.Controls.GridSplitter> angezeigt wird.  Im folgenden Beispiel werden Ränder für ein Steuerelement festgelegt, das sich andernfalls mit dem <xref:System.Windows.Controls.GridSplitter> überlappen und diesen ausblenden würde.  
  
 [!code-xml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.GridSplitter>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)