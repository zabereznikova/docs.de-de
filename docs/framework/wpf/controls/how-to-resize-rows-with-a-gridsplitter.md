---
title: "Gewusst wie: &#196;nderung der Zeilengr&#246;&#223;e mit einem GridSplitter | Microsoft Docs"
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
  - "Rasterzeilen, Größenänderung"
  - "GridSplitter-Steuerelement, Ändern der Größe von Rasterzeilen"
  - "Ändern der Größe von Rasterzeilen"
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: &#196;nderung der Zeilengr&#246;&#223;e mit einem GridSplitter
In diesem Beispiel wird veranschaulicht, wie mit einem horizontalen <xref:System.Windows.Controls.GridSplitter> der Platz zwischen zwei Zeilen in einem <xref:System.Windows.Controls.Grid> neu verteilt werden kann, ohne die Abmessungen des <xref:System.Windows.Controls.Grid> zu ändern.  
  
## Beispiel  
 ****Erstellen eines GridSplitters, der den Rand einer Zeile überlagert****  
  
 Um einen <xref:System.Windows.Controls.GridSplitter> anzugeben, der die Größe der benachbarten Zeilen in einem <xref:System.Windows.Controls.Grid> ändert, legen Sie die <xref:System.Windows.Controls.Grid.Row%2A> [angefügte Eigenschaft](GTMT) auf eine der Zeilen fest, deren Größe geändert werden soll.  Wenn das <xref:System.Windows.Controls.Grid> aus mehr als einer Spalte besteht, legen Sie die entsprechende <xref:System.Windows.Controls.Grid.ColumnSpan%2A>\-Eigenschaft auf die Anzahl der Spalten fest.  Legen Sie dann die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>\-Eigenschaft auf <xref:System.Windows.VerticalAlignment> oder <xref:System.Windows.VerticalAlignment> fest \(die Ausrichtung ist von den beiden Zeilen abhängig, deren Größe geändert werden soll\).  Legen Sie abschließend die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>\-Eigenschaft auf <xref:System.Windows.HorizontalAlignment> fest.  
  
 Das folgende Beispiel veranschaulicht die Definition eines horizontalen <xref:System.Windows.Controls.GridSplitter>, der die Größe benachbarter Zeilen ändert.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterRowOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 Ein <xref:System.Windows.Controls.GridSplitter>, der über keine eigene Zeile verfügt, kann von anderen Steuerelementen im <xref:System.Windows.Controls.Grid> verdeckt werden.  Weitere Informationen zum Vermeiden dieses Problems finden Sie unter [Sicherstellen, dass ein GridSplitter sichtbar ist](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 ****Erstellen eines GridSplitters, der eine Zeile einnimmt****  
  
 Um einen <xref:System.Windows.Controls.GridSplitter> anzugeben, der eine Zeile in einem <xref:System.Windows.Controls.Grid> einnimmt, legen Sie die <xref:System.Windows.Controls.Grid.Row%2A> [angefügte Eigenschaft](GTMT) auf eine der Zeilen fest, deren Größe geändert werden soll.  Wenn das <xref:System.Windows.Controls.Grid> aus mehr als einer Spalte besteht, legen Sie die entsprechende <xref:System.Windows.Controls.Grid.ColumnSpan%2A>\-Eigenschaft auf die Anzahl der Spalten fest.  Legen Sie anschließend <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> auf <xref:System.Windows.VerticalAlignment>, die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>\-Eigenschaft auf <xref:System.Windows.HorizontalAlignment> und die <xref:System.Windows.Controls.RowDefinition.Height%2A> der Zeile, die den <xref:System.Windows.Controls.GridSplitter> enthält, auf <xref:System.Windows.GridLength.Auto%2A> fest.  
  
 Im folgenden Beispiel wird die Definition eines horizontalen <xref:System.Windows.Controls.GridSplitter> veranschaulicht, der eine Zeile einnimmt und die Größe der angrenzenden Zeilen anpasst.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterEntireRowPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xml[GridSplitterRowColumn#GridSplitterEntireRowPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.GridSplitter>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)