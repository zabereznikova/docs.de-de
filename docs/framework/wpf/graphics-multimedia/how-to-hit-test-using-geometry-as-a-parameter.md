---
title: 'Vorgehensweise: Treffertest mit Geometrie als Parameter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 8bed7784b00f49178c9a87def74b62f7ce620ec7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923407"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>Vorgehensweise: Treffertest mit Geometrie als Parameter
Dieses Beispiel zeigt, wie Sie einen Treffer Test für ein visuelles Objekt ausführen, <xref:System.Windows.Media.Geometry> indem Sie als Treffer Testparameter verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie einen Treffer Test mithilfe <xref:System.Windows.Media.GeometryHitTestParameters> von für <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> die-Methode einrichten. Der <xref:System.Windows.Point> Wert, der an die `OnMouseDown` -Methode weitergegeben wird, wird <xref:System.Windows.Media.Geometry> verwendet, um ein-Objekt zu erstellen, um den Bereich des Treffer Tests zu erweitern.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 Die <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> -Eigenschaft <xref:System.Windows.Media.GeometryHitTestResult> von enthält Informationen zu den Ergebnissen eines Treffer Tests, der einen <xref:System.Windows.Media.Geometry> als Treffer Testparameter verwendet. In der folgenden Abbildung wird die Beziehung zwischen der Treffertestgeometrie (blauer Kreis) und dem gerenderten Inhalt des Zielobjekts (rotes Quadrat) dargestellt.  
  
 ![Diagramm, das IntersectionDetail anzeigt, das bei Treffer Tests verwendet wird.](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 Im folgenden Beispiel wird gezeigt, wie Sie einen Treffer Test Rückruf implementieren <xref:System.Windows.Media.Geometry> , wenn ein als Treffer Testparameter verwendet wird. Der `result` -Parameter wird in einen <xref:System.Windows.Media.GeometryHitTestResult> umgewandelt, um den Wert der- <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> Eigenschaft abzurufen. Mit dem Eigenschafts Wert können Sie feststellen <xref:System.Windows.Media.Geometry> , ob der Treffer Testparameter vollständig oder teilweise im gerenderten Inhalt des Treffer Test Ziels enthalten ist. In diesem Fall fügt der Beispielcode der Liste visueller Objekte nur Treffertestergebnisse hinzu, die vollständig im Zielbereich enthalten sind.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
> Der <xref:System.Windows.Media.HitTestResult> Rückruf sollte nicht aufgerufen werden, wenn die Überschneidungs <xref:System.Windows.Media.IntersectionDetail.Empty>Details ist.  
  
## <a name="see-also"></a>Siehe auch

- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
- [Vorgehensweise: Treffertest für eine Geometrie in einem visuellen Objekt](how-to-hit-test-geometry-in-a-visual.md)
