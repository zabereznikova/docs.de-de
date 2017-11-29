---
title: 'Gewusst wie: Erstellen eines komplexen Grid'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c0008a7379feefd9b3fe719f85b3205a72fb51d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-complex-grid"></a>Gewusst wie: Erstellen eines komplexen Grid
Dieses Beispiel zeigt, wie ein <xref:System.Windows.Controls.Grid> Layout erstellt wird, der einen Monatskalender ähnelt.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel definiert acht Zeilen und acht Spalten mithilfe der <xref:System.Windows.Controls.RowDefinition> und <xref:System.Windows.Controls.ColumnDefinition> Klassen. Er verwendet die <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> und <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> angefügten Eigenschaften zusammen mit <xref:System.Windows.Shapes.Rectangle> Elemente, die den Hintergrund der einzelnen Spalten und Zeilen ausfüllen. Dieser Entwurf ist möglich, da mehr als ein Element vorhanden, in jeder Zelle in sein kann einer <xref:System.Windows.Controls.Grid>, ein grundlegender Unterschied zwischen <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Documents.Table>.  
  
 Im Beispiel wird die vertikale Farbverläufe <xref:System.Windows.Shapes.Shape.Fill%2A> die Zeilen und Spalten, um die visuelle Darstellung und die Lesbarkeit des Kalenders zu verbessern. Formatiert <xref:System.Windows.Controls.TextBlock> Elemente darstellen, die Datumsangaben und die Tage der Woche. <xref:System.Windows.Controls.TextBlock>Elemente werden absolut positioniert Zellen mithilfe der <xref:System.Windows.FrameworkElement.Margin%2A> -Eigenschaft und die Eigenschaften für die Ausrichtung, die in das Format für die Anwendung definiert sind.  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md)
