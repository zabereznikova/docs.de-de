---
title: 'Vorgehensweise: Testen der Point4D-Struktur auf Gleichheit und Ungleichheit'
ms.date: 03/30/2017
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
ms.openlocfilehash: d72aef8a1328742f0b04c2ad009126e21390398a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367205"
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a>Vorgehensweise: Testen der Point4D-Struktur auf Gleichheit und Ungleichheit
Dieses Beispiel zeigt, wie Sie testen <xref:System.Windows.Media.Media3D.Point4D> Strukturen auf Gleichheit und Ungleichheit.  
  
 Der folgende Code zeigt, wie Sie testen <xref:System.Windows.Media.Media3D.Point4D> Strukturen auf Gleichheit und Ungleichheit mit der <xref:System.Windows.Media.Media3D.Point4D> Gleichheit-Methoden.  Die <xref:System.Windows.Media.Media3D.Point4D> Strukturen werden mit dem überladenen auf Gleichheit getestet (`==`) Operator, klicken Sie dann auf Ungleichheit, die mit den überladenen Ungleichheit (`!=`)-Operator, und schließlich eine <xref:System.Windows.Media.Media3D.Point3D> Struktur und ein <xref:System.Windows.Media.Media3D.Point4D> Struktur auf Gleichheit mit der statischen überprüft <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
