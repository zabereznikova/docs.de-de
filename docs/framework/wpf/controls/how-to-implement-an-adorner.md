---
title: 'Vorgehensweise: Implementieren eines Adorners'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: da318fee42b4628351217774de2a2225cfb21ee1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770980"
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
