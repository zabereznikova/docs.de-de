---
title: "Gewusst wie: Erstellen eines komplexen Grid | Microsoft Docs"
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
  - "Kalender, Erstellen"
  - "Grid-Steuerelement, Erstellen, Komplexes Raster"
  - "Monatskalender, Erstellen"
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Erstellen eines komplexen Grid
Dieses Beispiel zeigt, wie man mit einem <xref:System.Windows.Controls.Grid> ein Layout erstellt, das wie ein Monatskalender aussieht.  
  
## Beispiel  
 Im folgenden Beispiel werden mithilfe der <xref:System.Windows.Controls.RowDefinition>\-Klasse und der <xref:System.Windows.Controls.ColumnDefinition>\-Klasse acht Zeilen und acht Spalten definiert.  Die angefügten Eigenschaften <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=fullName> und <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=fullName> werden zusammen mit den <xref:System.Windows.Shapes.Rectangle>\-Elementen verwendet, die den Hintergrund der einzelnen Spalten und Zeilen ausfüllen.  Diese Gestaltung wird dadurch ermöglicht, dass in jeder Zelle in einem <xref:System.Windows.Controls.Grid> mehrere Elemente vorhanden sein können \(was ein grundlegender Unterschied zwischen <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Documents.Table> ist\).  
  
 Für die Spalten und Zeilen werden vertikale Farbverläufe verwendet \(<xref:System.Windows.Shapes.Shape.Fill%2A>\), um die visuelle Darstellung und Lesbarkeit des Kalenders zu verbessern.  Formatierte <xref:System.Windows.Controls.TextBlock>\-Elemente stellen Datumsangaben und Wochentage dar.   <xref:System.Windows.Controls.TextBlock>\-Elemente werden mittels der im Format für die Anwendung definierten <xref:System.Windows.FrameworkElement.Margin%2A>\-Eigenschaft und Ausrichtungseigenschaften absolut positioniert.  
  
 [!code-xml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.Documents.TableCell>   
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md)