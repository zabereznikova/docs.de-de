---
title: "Gewusst wie: &#196;nderung der Spaltengr&#246;&#223;e mit einem GridSplitter | Microsoft Docs"
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
  - "Datenblattspalten, Größenänderung"
  - "GridSplitter-Steuerelement, Ändern der Größe von Datenblattspalten"
  - "Ändern der Größe von Datenblattspalten"
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: &#196;nderung der Spaltengr&#246;&#223;e mit einem GridSplitter
In diesem Beispiel wird die Erstellung eines vertikalen <xref:System.Windows.Controls.GridSplitter> veranschaulicht, um den Platz zwischen zwei Spalten in einem <xref:System.Windows.Controls.Grid> zu verteilen, ohne die Dimensionen des <xref:System.Windows.Controls.Grid> zu ändern.  
  
## Beispiel  
 ****Erstellen eines GridSplitters, der den Rand einer Spalte überlagert****  
  
 Um einen <xref:System.Windows.Controls.GridSplitter> anzugeben, der die Größe der benachbarten Spalten in einem <xref:System.Windows.Controls.Grid> ändert, legen Sie die [angefügte Eigenschaft](GTMT) <xref:System.Windows.Controls.Grid.Column%2A> auf eine der Spalten fest, deren Größe geändert werden soll.  Wenn das <xref:System.Windows.Controls.Grid> aus mehr als einer Zeile besteht, legen Sie die an <xref:System.Windows.Controls.Grid.RowSpan%2A> angehängte Eigenschaft auf die Anzahl der Zeilen fest.  Legen Sie anschließend die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>\-Eigenschaft auf <xref:System.Windows.HorizontalAlignment> oder <xref:System.Windows.HorizontalAlignment> fest \(die Ausrichtung ist von den zwei Spalten abhängig, deren Größe geändert werden soll\).  Legen Sie abschließend die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>\-Eigenschaft auf <xref:System.Windows.VerticalAlignment> fest.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 Ein <xref:System.Windows.Controls.GridSplitter>, der über keine eigene Spalte verfügt, kann von anderen Steuerelementen im <xref:System.Windows.Controls.Grid> verdeckt werden.  Weitere Informationen zum Vermeiden dieses Problems finden Sie unter [Sicherstellen, dass ein GridSplitter sichtbar ist](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 ****Erstellen eines GridSplitter, der eine Spalte einnimmt****  
  
 Um einen <xref:System.Windows.Controls.GridSplitter> anzugeben, der eine Spalte in einem <xref:System.Windows.Controls.Grid> einnimmt, legen Sie die [angefügte Eigenschaft](GTMT) <xref:System.Windows.Controls.Grid.Column%2A> auf eine der Spalten fest, deren Größe geändert werden soll.  Wenn das Raster aus mehr als einer Zeile besteht, legen Sie die an <xref:System.Windows.Controls.Grid.RowSpan%2A> angehängte Eigenschaft auf die Anzahl der Zeilen fest.  Legen Sie anschließend die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> auf <xref:System.Windows.HorizontalAlignment> fest, die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>\-Eigenschaft auf <xref:System.Windows.VerticalAlignment> und die <xref:System.Windows.Controls.ColumnDefinition.Width%2A> der Spalte, die den <xref:System.Windows.Controls.GridSplitter> enthält, auf <xref:System.Windows.GridLength.Auto%2A>.  
  
 Im folgenden Beispiel wird die Definition von einem vertikalen <xref:System.Windows.Controls.GridSplitter> veranschaulicht, der eine Spalte einnimmt und die Größe der angrenzenden Spalten anpasst.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.GridSplitter>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)