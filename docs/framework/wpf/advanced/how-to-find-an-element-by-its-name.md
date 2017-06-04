---
title: "Gewusst wie: Suchen nach einem Element anhand des Namens | Microsoft Docs"
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
  - "Elemente, Suchen nach Name"
  - "FindName-Methode"
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Suchen nach einem Element anhand des Namens
Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.FrameworkElement.FindName%2A>\-Methode zum Suchen nach einem Element anhand seines <xref:System.Windows.FrameworkElement.Name%2A>\-Werts verwenden.  
  
## Beispiel  
 In diesem Beispiel wird die Methode zum Suchen nach einem bestimmten Element anhand seines Namens als Ereignishandler einer Schaltfläche geschrieben.  `stackPanel` ist die <xref:System.Windows.FrameworkElement.Name%2A>\-Eigenschaft des <xref:System.Windows.FrameworkElement>\-Stammelements, das durchsucht wird, und die Beispielmethode zeigt das gefundene Element dann an, indem es in einen <xref:System.Windows.Controls.TextBlock> umgewandelt wird und indem eine der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Eigenschaften von <xref:System.Windows.Controls.TextBlock> für die Sichtbarkeit geändert wird.  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]