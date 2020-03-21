---
title: 'Gewusst wie: Positionieren der untergeordneten Elemente eines Rasters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 44268c32732a9409ea30f028adaa8a2631a06c5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186721"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Gewusst wie: Positionieren der untergeordneten Elemente eines Rasters
In diesem Beispiel wird gezeigt, wie die <xref:System.Windows.Controls.Grid> get- und set-Methoden verwendet werden, die für die Positionierung untergeordneter Elemente definiert sind.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird <xref:System.Windows.Controls.Grid> ein`grid1`übergeordnetes Element ( ) definiert, das drei Spalten und drei Zeilen enthält. Ein <xref:System.Windows.Shapes.Rectangle> untergeordnetes`rect1`Element ( <xref:System.Windows.Controls.Grid> ) wird der Spaltenposition Null, Zeilenposition Null hinzugefügt. <xref:System.Windows.Controls.Button>Elemente stellen Methoden dar, die <xref:System.Windows.Shapes.Rectangle> aufgerufen werden <xref:System.Windows.Controls.Grid>können, um das Element innerhalb der neu zu positionieren. Wenn ein Benutzer auf eine Schaltfläche klickt, wird die zugehörige Methode aktiviert.  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 Im folgenden CodeBehind-Beispiel werden die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Methoden behandelt, die von den Schaltflächenereignissen angezeigt werden. Im Beispiel werden diese <xref:System.Windows.Controls.TextBlock> Methodenaufrufe an Elemente schrieben, die verwandte ab-Methoden verwenden, um die neuen Eigenschaftswerte als Zeichenfolgen auszugeben.  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 Hier ist das fertige Ergebnis!

 ![Ein Screenshot zeigt eine WPF-Benutzeroberfläche mit zwei Spalten, die rechte Seite hat ein 3 x 3 Raster und die linke hat Schaltflächen, um ein farbiges Rechteck zwischen den Spalten und Zeilen des Rasters zu verschieben](././media/grid-methods-sample.png)
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.Grid>
- [Übersicht über Panel-Elemente](panels-overview.md)
