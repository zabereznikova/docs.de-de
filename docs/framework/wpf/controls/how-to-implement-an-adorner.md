---
title: 'Gewusst wie: Implementieren eines Adorners'
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
helpviewer_keywords: adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3f69fee64ea65e8d49cce523c85669993cc6bce
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-implement-an-adorner"></a>Gewusst wie: Implementieren eines Adorners
Dieses Beispiel zeigt eine minimale Adornerimplementierung.  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Beachten Sie, dass für Adorner kein Renderingverhalten festgelegt ist. Damit wird sichergestellt, dass für das Rendering die Adorner-Implementierung verantwortlich ist.   Ist eine allgemeine Möglichkeit zum Implementieren von Renderingverhalten überschreiben die <xref:System.Windows.UIElement.OnRender%2A> -Methode, und verwenden Sie eine oder mehrere <xref:System.Windows.Media.DrawingContext> Objekte zum Rendern der Funktionsindikator visuelle Elemente nach Bedarf (wie im folgenden Beispiel gezeigt).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Ein benutzerdefinierter Adorner wird erstellt, durch die Implementierung einer Klasse, die von der abstrakten erbt <xref:System.Windows.Documents.Adorner> Klasse.  Beispieladorner werden einfach die Ecken des eine <xref:System.Windows.UIElement> mit Kreisen durch Überschreiben der <xref:System.Windows.UIElement.OnRender%2A> Methode.  
  
### <a name="code"></a>Code  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Adorner](../../../../docs/framework/wpf/controls/adorners-overview.md)
