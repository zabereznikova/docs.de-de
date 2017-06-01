---
title: "Gewusst wie: Positionieren der untergeordneten Elemente eines Rasters | Microsoft Docs"
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
  - "Grid-Steuerelement, Positionieren von untergeordneten Elementen"
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Positionieren der untergeordneten Elemente eines Rasters
In diesem Beispiel wird gezeigt, wie die auf <xref:System.Windows.Controls.Grid> definierten Get\- und Set\-Methoden zum Positionieren untergeordneter Elemente verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird ein übergeordnetes <xref:System.Windows.Controls.Grid>\-Element \(`grid1`\) definiert, das über drei Spalten und drei Zeilen verfügt.  Ein untergeordnetes <xref:System.Windows.Shapes.Rectangle>\-Element \(`rect1`\) wird zum <xref:System.Windows.Controls.Grid>\-Element an Spaltenposition 0 \(null\), Zeilenposition 0 \(null\) hinzugefügt.  <xref:System.Windows.Controls.Button>\-Elemente stellen Methoden dar, die aufgerufen werden können, um das <xref:System.Windows.Shapes.Rectangle>\-Element im <xref:System.Windows.Controls.Grid>\-Element neu zu positionieren.  Wenn ein Benutzer auf eine Schaltfläche klickt, wird die zugehörige Methode aktiviert.  
  
 [!code-xml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 Im folgenden Code\-Behind\-Beispiel werden die Methoden behandelt, die von den <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignissen der Schaltfläche ausgelöst werden.  Im Beispiel werden diese Methodenaufrufe in <xref:System.Windows.Controls.TextBlock>\-Elemente geschrieben, die zugehörige Get\-Methoden verwenden, um die neuen Eigenschaftswerte als Zeichenfolgen auszugeben.  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Grid>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)