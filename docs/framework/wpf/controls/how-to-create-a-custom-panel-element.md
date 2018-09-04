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
ms.openlocfilehash: bca8900ccb3c31a78066a43709a5e9334bc09eab
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43531783"
---
# <a name="how-to-create-a-custom-panel-element"></a>Gewusst wie: Erstellen eines benutzerdefinierten Bereichselements
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, das das Standardverhalten des Layouts des überschreiben die <xref:System.Windows.Controls.Panel> Element, und erstellen Sie benutzerdefinierte Layouts-Elemente, die abgeleitet sind <xref:System.Windows.Controls.Panel>.  
  
 Im Beispiel definiert eine einfache benutzerdefinierte <xref:System.Windows.Controls.Panel> Element namens `PlotPanel`, die untergeordneten Elemente zwei hartcodierten x und y-Koordinaten entsprechend positioniert. In diesem Beispiel `x` und `y` auf festlegen `50`; aus diesem Grund werden alle untergeordneten Elemente an diesem Speicherort auf der x- und y positioniert Achsen.  
  
 Zum Implementieren von benutzerdefinierten <xref:System.Windows.Controls.Panel> Verhalten, das Beispiel verwendet die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden. Jede Methode gibt die <xref:System.Windows.Size> Daten, die zum Positionieren und die untergeordneten Elemente gerendert sind.  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Panel>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Erstellen einer benutzerdefinierten Content-Wrapping Panel Sample](https://go.microsoft.com/fwlink/?LinkID=159979)
