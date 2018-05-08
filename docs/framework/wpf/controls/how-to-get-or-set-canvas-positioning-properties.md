---
title: 'Gewusst wie: Abrufen und Festlegen von Canvas-Positionierungseigenschaften'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 294b49d427a67da849ce930cf29a48f1735bf135
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a>Gewusst wie: Abrufen und Festlegen von Canvas-Positionierungseigenschaften
Dieses Beispiel zeigt, wie die Positionierung Methoden die <xref:System.Windows.Controls.Canvas> Element des untergeordneten Inhalts zu positionieren. In diesem Beispiel verwendet den Inhalt in einen <xref:System.Windows.Controls.ListBoxItem> zur Darstellung Werte positionieren und konvertiert die Werte in Instanzen von <xref:System.Double>, dies ist ein erforderliches Argument für die Positionierung. Die Werte sind dann wieder in Zeichenfolgen konvertiert und als Text im angezeigt ein <xref:System.Windows.Controls.TextBlock> -Element mithilfe der <xref:System.Windows.Controls.Canvas.GetLeft%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ListBox> Element, das elf auswählbare hat <xref:System.Windows.Controls.ListBoxItem> Elemente. Die <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> Ereignistriggern der `ChangeLeft` benutzerdefinierte Methode, die im nachfolgenden Codeblock definiert.  
  
 Jedes <xref:System.Windows.Controls.ListBoxItem> stellt eine <xref:System.Double> Wert, der eines der Argumente ist, der <xref:System.Windows.Controls.Canvas.SetLeft%2A> Methode <xref:System.Windows.Controls.Canvas> akzeptiert. Zum Verwenden einer <xref:System.Windows.Controls.ListBoxItem> zur Darstellung einer Instanz von <xref:System.Double>, müssen Sie zuerst Konvertieren der <xref:System.Windows.Controls.ListBoxItem> in den richtigen Datentyp.  
  
 [!code-xaml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 Wenn ein Benutzer ändert die <xref:System.Windows.Controls.ListBox> Auswahl, ruft der `ChangeLeft` benutzerdefinierte Methode. Diese Methode übergibt der <xref:System.Windows.Controls.ListBoxItem> auf eine <xref:System.Windows.LengthConverter> -Objekt, das konvertiert die <xref:System.Windows.Controls.ContentControl.Content%2A> des eine <xref:System.Windows.Controls.ListBoxItem> mit einer Instanz von <xref:System.Double> (Beachten Sie, das diesen Wert auf bereits konvertiert wurde eine <xref:System.String> mithilfe der <xref:System.Windows.Controls.Control.ToString%2A> die Methode). Dieser Wert wird dann zurück zum Übergeben der <xref:System.Windows.Controls.Canvas.SetLeft%2A> und <xref:System.Windows.Controls.Canvas.GetLeft%2A> Methoden der <xref:System.Windows.Controls.Canvas> damit ändern Sie die Position von der `text1` Objekt.  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.ListBoxItem>  
 <xref:System.Windows.LengthConverter>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
