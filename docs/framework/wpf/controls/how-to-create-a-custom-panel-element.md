---
title: 'Gewusst wie: Erstellen eines benutzerdefinierten Bereichselements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7e7cca5b6f7a0d5085e70c4ab6ac33ff83b75217
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-panel-element"></a>Gewusst wie: Erstellen eines benutzerdefinierten Bereichselements
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird gezeigt, wie das Standardverhalten des Layouts des überschreiben die <xref:System.Windows.Controls.Panel> Element, und erstellen Sie benutzerdefinierte Layoutelemente, die abgeleitet sind <xref:System.Windows.Controls.Panel>.  
  
 Im Beispiel definiert eine einfache benutzerdefinierte <xref:System.Windows.Controls.Panel> Element namens `PlotPanel`, die untergeordnete Elemente zwei hartcodierten x- und y-Koordinaten entsprechend positioniert. In diesem Beispiel `x` und `y` festgelegt `50`; daher werden alle untergeordneten Elemente an dieser Stelle auf der x- und y-Achse positioniert Achsen.  
  
 Zum Implementieren von benutzerdefinierten <xref:System.Windows.Controls.Panel> Verhaltensweisen, die im Beispiel wird die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden. Jede Methode gibt die <xref:System.Windows.Size> Daten, die erforderlich sind zum Positionieren und Rendern von untergeordneten Elementen.  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Panel>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Erstellen einer benutzerdefinierten Inhalt Wrapping Bereichsbeispiel](http://go.microsoft.com/fwlink/?LinkID=159979)
