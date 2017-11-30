---
title: 'Gewusst wie: Treffertest mit Geometrie als Parameter'
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
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 32feb70a3b7a44a5a48f57fc2ecee912de4d39ef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>Gewusst wie: Treffertest mit Geometrie als Parameter
In diesem Beispiel wird gezeigt, wie zum Ausführen von Treffertests auf ein visuelles Objekt mithilfe einer <xref:System.Windows.Media.Geometry> Parameter als Treffer zu testen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie ein Treffertest mit eingerichtet <xref:System.Windows.Media.GeometryHitTestParameters> für die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode. Die <xref:System.Windows.Point> -Wert, der übergeben wird die `OnMouseDown` Methode dient zum Erstellen einer <xref:System.Windows.Media.Geometry> Objekt, um den Bereich des Treffertests zu erweitern.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 Die <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> Eigenschaft <xref:System.Windows.Media.GeometryHitTestResult> enthält Informationen über die Ergebnisse eines Treffertests verwendet eine <xref:System.Windows.Media.Geometry> Parameter als Treffer zu testen. In der folgenden Abbildung wird die Beziehung zwischen der Treffertestgeometrie (blauer Kreis) und dem gerenderten Inhalt des Zielobjekts (rotes Quadrat) dargestellt.  
  
 ![Diagramm von IntersectionDetail bei Treffertests](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")  
Schnittmenge einer Treffertestgeometrie und eines Zielobjekts  
  
 Im folgende Beispiel wird gezeigt, wie einen Treffertest-Rückruf implementieren bei einem <xref:System.Windows.Media.Geometry> als Treffertestparameter verwendet wird. Die `result` Parameter umgewandelt wird eine <xref:System.Windows.Media.GeometryHitTestResult> zum Abrufen des Werts der <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> Eigenschaft. Den Wert der Eigenschaft können Sie bestimmen, ob die <xref:System.Windows.Media.Geometry> Treffertest-Parameter ist vollständig oder teilweise enthaltenen den gerenderten Inhalt des Ziels Treffertest. In diesem Fall fügt der Beispielcode der Liste visueller Objekte nur Treffertestergebnisse hinzu, die vollständig im Zielbereich enthalten sind.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  Die <xref:System.Windows.Media.HitTestResult> Rückruf darf nicht aufgerufen werden, wenn die Schnittmenge ist <xref:System.Windows.Media.IntersectionDetail.Empty>.  
  
## <a name="see-also"></a>Siehe auch  
 [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Vorgehensweise: Treffertest für eine Geometrie in einem visuellen Objekt](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)
