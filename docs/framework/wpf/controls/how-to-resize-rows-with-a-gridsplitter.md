---
title: 'Vorgehensweise: Änderung der Zeilengröße mit einem GridSplitter'
ms.date: 03/30/2017
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
ms.openlocfilehash: 6760a7a691af4f666294556cae3bc95a4299730a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074273"
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a>Vorgehensweise: Änderung der Zeilengröße mit einem GridSplitter
Dieses Beispiel zeigt, wie Sie mit einer horizontalen <xref:System.Windows.Controls.GridSplitter> erneut zu verteilende den Abstand zwischen zwei Zeilen in einer <xref:System.Windows.Controls.Grid> ohne die Abmessungen des der <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Beispiel  
 **Erstellen ein GridSplitter-Elements, überlagert der Rand einer Zeile**  
  
 Angeben einer <xref:System.Windows.Controls.GridSplitter> ändert, die die Größe angrenzenden Zeilen in einer <xref:System.Windows.Controls.Grid>, legen die <xref:System.Windows.Controls.Grid.Row%2A> angefügte Eigenschaft auf eine der Zeilen, die Sie anpassen möchten. Wenn Ihre <xref:System.Windows.Controls.Grid> verfügt über mehr als eine Spalte, legen Sie die <xref:System.Windows.Controls.Grid.ColumnSpan%2A> angefügte Eigenschaft, um die Anzahl der Spalten angeben. Legen Sie dann die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> zu <xref:System.Windows.VerticalAlignment.Top> oder <xref:System.Windows.VerticalAlignment.Bottom> (welche Ausrichtung Sie festlegen, je nach den beiden Zeilen Sie anpassen möchten). Legen Sie schließlich die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft <xref:System.Windows.HorizontalAlignment.Stretch>.  
  
 Das folgende Beispiel zeigt, wie Sie die Definition eines horizontalen <xref:System.Windows.Controls.GridSplitter> , die angrenzende Zeilen ändert.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 Ein <xref:System.Windows.Controls.GridSplitter> , das ist eine eigene Zeile nicht belegen kann von anderen Steuerelementen im verdeckt werden die <xref:System.Windows.Controls.Grid>. Weitere Informationen zum Vermeiden dieses Problems finden Sie unter [Sicherstellen, dass ein GridSplitter sichtbar ist](how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Erstellen ein GridSplitter-Elements, das eine Zeile einnimmt**  
  
 Angeben einer <xref:System.Windows.Controls.GridSplitter> , die das über eine Zeile in einer <xref:System.Windows.Controls.Grid>, legen die <xref:System.Windows.Controls.Grid.Row%2A> angefügte Eigenschaft auf eine der Zeilen, die Sie anpassen möchten. Wenn Ihre <xref:System.Windows.Controls.Grid> verfügt über mehr als eine Spalte, legen Sie die <xref:System.Windows.Controls.Grid.ColumnSpan%2A> angefügte Eigenschaft auf die Anzahl der Spalten. Legen Sie dann die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> zu <xref:System.Windows.VerticalAlignment.Center>, legen die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft <xref:System.Windows.HorizontalAlignment.Stretch>, und legen Sie die <xref:System.Windows.Controls.RowDefinition.Height%2A> der Zeile, die enthält die <xref:System.Windows.Controls.GridSplitter> zu <xref:System.Windows.GridLength.Auto%2A>.  
  
 Das folgende Beispiel zeigt, wie Sie die Definition eines horizontalen <xref:System.Windows.Controls.GridSplitter> , die eine Zeile einnimmt und die Zeilen auf beiden Seiten davon ändert.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.GridSplitter>
- [Gewusst wie-Themen](gridsplitter-how-to-topics.md)
