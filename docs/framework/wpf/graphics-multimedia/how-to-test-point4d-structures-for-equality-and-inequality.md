---
title: 'Vorgehensweise: Testen der Point4D-Strukturen auf Gleichheit und Ungleichheit'
ms.date: 03/30/2017
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
ms.openlocfilehash: ce1188e99ef2b0682427cc2e227aaccd27f7c4f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770151"
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a>Vorgehensweise: Testen der Point4D-Strukturen auf Gleichheit und Ungleichheit
Dieses Beispiel zeigt, wie Sie testen <xref:System.Windows.Media.Media3D.Point4D> Strukturen auf Gleichheit und Ungleichheit.  
  
 Der folgende Code zeigt, wie Sie testen <xref:System.Windows.Media.Media3D.Point4D> Strukturen auf Gleichheit und Ungleichheit mit der <xref:System.Windows.Media.Media3D.Point4D> Gleichheit-Methoden.  Die <xref:System.Windows.Media.Media3D.Point4D> Strukturen werden mit dem überladenen auf Gleichheit getestet (`==`) Operator, klicken Sie dann auf Ungleichheit, die mit den überladenen Ungleichheit (`!=`)-Operator, und schließlich eine <xref:System.Windows.Media.Media3D.Point3D> Struktur und ein <xref:System.Windows.Media.Media3D.Point4D> Struktur auf Gleichheit mit der statischen überprüft <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
