---
title: "Gewusst wie: Änderung der Zeilengröße mit einem GridSplitter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6621cc0048270b97c42ff4c4e646b0ddd9ca3477
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a>Gewusst wie: Änderung der Zeilengröße mit einem GridSplitter
Dieses Beispiel zeigt, wie eine horizontale <xref:System.Windows.Controls.GridSplitter> erneut zu verteilende den Abstand zwischen den zwei Zeilen in einer <xref:System.Windows.Controls.Grid> ohne Änderung der Dimensionen des der <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Beispiel  
 **Erstellen eines GridSplitter-Elements, das den Rand einer Zeile überlagert**  
  
 Angeben einer <xref:System.Windows.Controls.GridSplitter> , die Größe angrenzenden Zeilen in eine <xref:System.Windows.Controls.Grid>, legen die <xref:System.Windows.Controls.Grid.Row%2A> angefügte Eigenschaft auf eine der Zeilen, die Sie anpassen möchten. Wenn Ihre <xref:System.Windows.Controls.Grid> verfügt über mehr als eine Spalte Festlegen der <xref:System.Windows.Controls.Grid.ColumnSpan%2A> -Eigenschaft, um die Anzahl der Spalten angeben. Legen Sie dann die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> auf <xref:System.Windows.VerticalAlignment.Top> oder <xref:System.Windows.VerticalAlignment.Bottom> (die Ausrichtung, die Sie festlegen, je nach den beiden Zeilen Sie anpassen möchten). Legen Sie schließlich die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft <xref:System.Windows.HorizontalAlignment.Stretch>.  
  
 Das folgende Beispiel zeigt, wie eine horizontale definiert <xref:System.Windows.Controls.GridSplitter> , die angrenzende Zeilen ändert.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 Ein <xref:System.Windows.Controls.GridSplitter> beansprucht, die keinen eine eigene Zeile kann von anderen Steuerelementen im verdeckt werden die <xref:System.Windows.Controls.Grid>. Weitere Informationen zum Vermeiden dieses Problems finden Sie unter [Sicherstellen, dass ein GridSplitter sichtbar ist](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Erstellen eines GridSplitter-Elements, das eine Zeile einnimmt**  
  
 Angeben einer <xref:System.Windows.Controls.GridSplitter> , die belegt einer Zeile in einer <xref:System.Windows.Controls.Grid>legen die <xref:System.Windows.Controls.Grid.Row%2A> angefügte Eigenschaft auf eine der Zeilen, die Sie anpassen möchten. Wenn Ihre <xref:System.Windows.Controls.Grid> verfügt über mehr als eine Spalte Festlegen der <xref:System.Windows.Controls.Grid.ColumnSpan%2A> -Eigenschaft auf die Anzahl der Spalten. Legen Sie dann die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> auf <xref:System.Windows.VerticalAlignment.Center>, legen die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft, um <xref:System.Windows.HorizontalAlignment.Stretch>, und legen Sie die <xref:System.Windows.Controls.RowDefinition.Height%2A> der Zeile, die enthält die <xref:System.Windows.Controls.GridSplitter> auf <xref:System.Windows.GridLength.Auto%2A>.  
  
 Das folgende Beispiel zeigt, wie eine horizontale definiert <xref:System.Windows.Controls.GridSplitter> , die eine Zeile einnimmt, und ändert die Größe der Zeilen auf beiden Seiten des Zertifikats.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.GridSplitter>  
 [Gewusst wie-Themen](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
