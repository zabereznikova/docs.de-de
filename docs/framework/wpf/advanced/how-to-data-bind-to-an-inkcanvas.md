---
title: 'Gewusst wie: Datenbindung an ein InkCanvas-Steuerelement'
ms.date: 03/30/2017
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
ms.openlocfilehash: 4081ae7dd6854934804062cfce60d10106c1e1d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a>Gewusst wie: Datenbindung an ein InkCanvas-Steuerelement
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Binden der <xref:System.Windows.Controls.InkCanvas.Strokes%2A> Eigenschaft ein <xref:System.Windows.Controls.InkCanvas> in eine andere <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xaml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 Das folgende Beispiel veranschaulicht das Binden der <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaft mit einer Datenquelle.  
  
 [!code-xaml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 Das folgende Beispiel deklariert zwei <xref:System.Windows.Controls.InkCanvas> -Objekte in XAML und stellt die Datenbindung zwischen ihnen und anderen Datenquellen her.  Die erste <xref:System.Windows.Controls.InkCanvas>namens `ic`, mit zwei Datenquellen gebunden ist.  Die <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> und <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaften auf `ic` gebunden <xref:System.Windows.Controls.ListBox> Objekte, die wiederum in der XAML-definierte Arrays gebunden sind.  Die <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, und <xref:System.Windows.Controls.InkCanvas.Strokes%2A> Eigenschaften des zweiten <xref:System.Windows.Controls.InkCanvas> gebunden sind mit dem ersten <xref:System.Windows.Controls.InkCanvas>, `ic`.  
  
 [!code-xaml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
