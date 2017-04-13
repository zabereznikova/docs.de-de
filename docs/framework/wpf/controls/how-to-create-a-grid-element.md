---
title: "Gewusst wie: Erstellen eines Elements von Grid | Microsoft Docs"
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
  - "Grid-Steuerelement, Erstellen, Rasterinstanz"
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Erstellen eines Elements von Grid
## Beispiel  
 Im folgenden Beispiel wird das Erstellen und Verwenden einer Instanz des <xref:System.Windows.Controls.Grid>\-Steuerelements mithilfe von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code veranschaulicht.  In diesem Beispiel werden drei <xref:System.Windows.Controls.ColumnDefinition>\-Objekte und drei <xref:System.Windows.Controls.RowDefinition>\-Objekte zum Erstellen eines Rasters verwendet, das neun Zellen \(wie in einem Arbeitsblatt\) enthält.  Jede Zelle enthält ein Daten darstellendes <xref:System.Windows.Controls.TextBlock>\-Element. Die oberste Zeile enthält einen <xref:System.Windows.Controls.TextBlock>, auf den die <xref:System.Windows.Controls.Grid.ColumnSpan%2A>\-Eigenschaft angewendet wurde.  Um die Begrenzungen jeder Zelle anzuzeigen, ist die <xref:System.Windows.Controls.Grid.ShowGridLines%2A>\-Eigenschaft aktiviert.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Grid>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)