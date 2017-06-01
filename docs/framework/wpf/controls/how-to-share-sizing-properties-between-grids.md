---
title: "Gewusst wie: Freigeben von Gr&#246;&#223;eneigenschaften zwischen Grids | Microsoft Docs"
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
  - "Grid-Steuerelement, Freigeben der Größenänderungsdaten von Spalten"
  - "Grid-Steuerelement, Freigeben der Größenänderungsdaten von Zeilen"
  - "Größenänderung von Daten in Grid-Steuerelementen"
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Freigeben von Gr&#246;&#223;eneigenschaften zwischen Grids
Dieses Beispiel veranschaulicht, wie Größenanpassungsdaten von Spalten und Zeilen zwischen <xref:System.Windows.Controls.Grid>\-Elementen freigegeben werden, um die Größenanpassung zu vereinheitlichen.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei <xref:System.Windows.Controls.Grid>\-Elemente als untergeordnete Elemente eines übergeordneten <xref:System.Windows.Controls.DockPanel> eingeführt.  Die [angefügte Eigenschaft](GTMT) <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> des <xref:System.Windows.Controls.Grid> wird über das übergeordnete <xref:System.Windows.Controls.DockPanel> definiert.  
  
 In diesem Beispiel wird der Eigenschaftswert durch die Verwendung von zwei <xref:System.Windows.Controls.Button>\-Elementen manipuliert, wobei jedes Element einen booleschen Eigenschaftswert darstellt.  Wenn der <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>\-Eigenschaftswert `true` ist, werden Größeninformationen gemeinsam von jedem Spalten\- oder Zeilenmember einer <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> genutzt, ungeachtet des Inhalts einer Zeile oder Spalte.  
  
 [!code-xml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 Im folgenden Code\-Behind\-Beispiel werden die Methoden behandelt, die vom Schaltflächenereignis <xref:System.Windows.Controls.Primitives.ButtonBase.Click> ausgelöst werden.  Das Beispiel schreibt die Ergebnisse dieser Methodenanrufe in <xref:System.Windows.Controls.TextBlock>\-Elemente, die entsprechende Get\-Methoden verwenden, um die neuen Eigenschaftswerte als Zeichenfolgen auszugeben.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)