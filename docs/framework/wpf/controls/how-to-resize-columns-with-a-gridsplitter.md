---
title: 'Vorgehensweise: Änderung der Spaltengröße mit einem GridSplitter'
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: f743e9ccf8a984a646a4b8f05ee99162e5bc73ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210437"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a>Vorgehensweise: Änderung der Spaltengröße mit einem GridSplitter
Dieses Beispiel zeigt, wie Sie ein vertikales erstellen <xref:System.Windows.Controls.GridSplitter> zum Verteilen des Abstand zwischen zwei Spalten in einer <xref:System.Windows.Controls.Grid> ohne die Abmessungen des der <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Beispiel  
 **Erstellen ein GridSplitter-Elements, überlagert der Rand einer Spalte**  
  
 Angeben einer <xref:System.Windows.Controls.GridSplitter> , die Größe der angrenzender Spalten in einer <xref:System.Windows.Controls.Grid>legen die <xref:System.Windows.Controls.Grid.Column%2A> angefügte Eigenschaft auf eine der Spalten, die Sie anpassen möchten. Wenn Ihre <xref:System.Windows.Controls.Grid> verfügt über mehr als eine Zeile, legen Sie die <xref:System.Windows.Controls.Grid.RowSpan%2A> angefügte Eigenschaft auf die Anzahl der Zeilen. Legen Sie dann die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft <xref:System.Windows.HorizontalAlignment.Left> oder <xref:System.Windows.HorizontalAlignment.Right> (welche Ausrichtung Sie festlegen, je nach den zwei Spalten, die Sie zum Ändern der Größe möchten). Legen Sie schließlich die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft <xref:System.Windows.VerticalAlignment.Stretch>.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 Ein <xref:System.Windows.Controls.GridSplitter> , die keine eigene Spalte möglicherweise von anderen Steuerelementen im verdeckt werden die <xref:System.Windows.Controls.Grid>. Weitere Informationen zum Vermeiden dieses Problems finden Sie unter [Sicherstellen, dass ein GridSplitter sichtbar ist](how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Erstellen ein GridSplitter-Elements, das eine Spalte einnimmt**  
  
 Angeben einer <xref:System.Windows.Controls.GridSplitter> , das eine Spalte in einer <xref:System.Windows.Controls.Grid>legen die <xref:System.Windows.Controls.Grid.Column%2A> angefügte Eigenschaft auf eine der Spalten, die Sie anpassen möchten. Wenn Ihr Raster über mehr als eine Zeile verfügt, legen Sie die <xref:System.Windows.Controls.Grid.RowSpan%2A> angefügte Eigenschaft auf die Anzahl der Zeilen. Legen Sie dann die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> zu <xref:System.Windows.HorizontalAlignment.Center>legen die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft, um <xref:System.Windows.VerticalAlignment.Stretch>, und legen Sie die <xref:System.Windows.Controls.ColumnDefinition.Width%2A> der Spalte, die enthält die <xref:System.Windows.Controls.GridSplitter> zu <xref:System.Windows.GridLength.Auto%2A>.  
  
 Das folgende Beispiel zeigt, wie Sie definieren eine vertikale <xref:System.Windows.Controls.GridSplitter> , die eine Spalte einnimmt und die Spalten auf beiden Seiten davon ändert.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.GridSplitter>
- [Gewusst wie-Themen](gridsplitter-how-to-topics.md)
