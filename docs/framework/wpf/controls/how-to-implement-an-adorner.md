---
title: 'Vorgehensweise: Implementieren eines Adorners'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: 53a25396ba5d8a5c78e850e636b7c882c03d5152
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362642"
---
# <a name="how-to-implement-an-adorner"></a>Vorgehensweise: Implementieren eines Adorners
Dieses Beispiel zeigt eine minimale Adornerimplementierung.  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Beachten Sie, dass für Adorner kein Renderingverhalten festgelegt ist. Damit wird sichergestellt, dass für das Rendering die Adorner-Implementierung verantwortlich ist.   Eine gängige Methode, der Renderingverhalten zu implementieren ist, überschreiben die <xref:System.Windows.UIElement.OnRender%2A> -Methode und eine oder mehrere <xref:System.Windows.Media.DrawingContext> Objekte, um die Darstellung des Adorners nach Bedarf (wie im folgenden Beispiel gezeigt) zu rendern.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Ein benutzerdefinierter Adorner wird erstellt, durch die Implementierung einer Klasse, die von der abstrakten erbt <xref:System.Windows.Documents.Adorner> Klasse.  Der Beispiel-Adorner verziert einfach die Ecken einer <xref:System.Windows.UIElement> mit Kreisen durch Überschreiben der <xref:System.Windows.UIElement.OnRender%2A> Methode.  
  
### <a name="code"></a>Code  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Adorner](adorners-overview.md)
