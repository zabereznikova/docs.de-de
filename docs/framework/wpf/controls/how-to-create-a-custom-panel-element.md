---
title: 'Gewusst wie: Erstellen eines benutzerdefinierten Bereichselements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 31edc75114c5dad613e5b65e7d8b051e2c3713af
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799145"
---
# <a name="how-to-create-a-custom-panel-element"></a>Gewusst wie: Erstellen eines benutzerdefinierten Bereichselements
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie das Standardlayoutverhalten des <xref:System.Windows.Controls.Panel> Elements überschrieben und benutzerdefinierte Layoutelemente erstellt werden, die von <xref:System.Windows.Controls.Panel>abgeleitet werden.  
  
 Im Beispiel wird ein einfaches benutzerdefiniertes <xref:System.Windows.Controls.Panel> Element mit dem Namen `PlotPanel`definiert, das untergeordnete Elemente nach zwei hart codierten x-und y-Koordinaten positioniert. In diesem Beispiel sind `x` und `y` auf `50`festgelegt. Daher werden alle untergeordneten Elemente an dieser Stelle auf der x-und der y-Achse positioniert.  
  
 Zum Implementieren von benutzerdefinierten <xref:System.Windows.Controls.Panel> Verhalten verwendet das Beispiel die Methoden <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>. Jede Methode gibt die <xref:System.Windows.Size> Daten zurück, die erforderlich sind, um untergeordnete Elemente zu positionieren und zu Rendering.  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Panel>
- [Übersicht über Panel-Elemente](panels-overview.md)
