---
title: 'Gewusst wie: Änderung der Spaltengröße mit einem GridSplitter'
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: b4652c06cfe6f048f6c75a11b9447d70d6820e4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556149"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a>Gewusst wie: Änderung der Spaltengröße mit einem GridSplitter
In diesem Beispiel wird gezeigt, wie zum Erstellen einer vertikales <xref:System.Windows.Controls.GridSplitter> zum Verteilen des Abstand zwischen zwei Spalten in einem <xref:System.Windows.Controls.Grid> ohne Änderung der Dimensionen des der <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Beispiel  
 **Erstellen eines GridSplitter-Elements, das den Rand einer Spalte überlagert**  
  
 Angeben einer <xref:System.Windows.Controls.GridSplitter> , die Größe der angrenzenden Spalten in einer <xref:System.Windows.Controls.Grid>legen die <xref:System.Windows.Controls.Grid.Column%2A> angefügte Eigenschaft auf eine der Spalten, die Sie anpassen möchten. Wenn Ihre <xref:System.Windows.Controls.Grid> verfügt über mehr als eine Zeile legen Sie die <xref:System.Windows.Controls.Grid.RowSpan%2A> -Eigenschaft, um die Anzahl der Zeilen. Legen Sie dann die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft <xref:System.Windows.HorizontalAlignment.Left> oder <xref:System.Windows.HorizontalAlignment.Right> (die Ausrichtung, die Sie festlegen, je nach den zwei Spalten Sie anpassen möchten). Legen Sie schließlich die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft <xref:System.Windows.VerticalAlignment.Stretch>.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 Ein <xref:System.Windows.Controls.GridSplitter> , die keine eigene Spalte möglicherweise von anderen Steuerelementen im verdeckt werden die <xref:System.Windows.Controls.Grid>. Weitere Informationen zum Vermeiden dieses Problems finden Sie unter [Sicherstellen, dass ein GridSplitter sichtbar ist](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Erstellen eines GridSplitter-Elements, das eine Spalte einnimmt**  
  
 Angeben einer <xref:System.Windows.Controls.GridSplitter> , die belegt, dass einer Spalteninhalts in einer <xref:System.Windows.Controls.Grid>legen die <xref:System.Windows.Controls.Grid.Column%2A> angefügte Eigenschaft auf eine der Spalten, die Sie anpassen möchten. Wenn das Raster mehrere Zeilen verfügt, legen Sie die <xref:System.Windows.Controls.Grid.RowSpan%2A> -Eigenschaft, um die Anzahl der Zeilen. Legen Sie dann die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> auf <xref:System.Windows.HorizontalAlignment.Center>, legen die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft, um <xref:System.Windows.VerticalAlignment.Stretch>, und legen Sie die <xref:System.Windows.Controls.ColumnDefinition.Width%2A> der Spalte, die enthält die <xref:System.Windows.Controls.GridSplitter> auf <xref:System.Windows.GridLength.Auto%2A>.  
  
 Das folgende Beispiel zeigt, wie eine vertikalen definiert <xref:System.Windows.Controls.GridSplitter> , die eine Spalte einnimmt, und ändert die Größe der Spalten auf beiden Seiten des Zertifikats.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.GridSplitter>  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
