---
title: "Gewusst wie: Treffertest mit Geometrie als Parameter | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Geometry-Objekte, Treffertests für visuelle Objekte"
  - "Treffertests, In visuellen Objekten mithilfe von Geometry-Objekten"
  - "Visuelle Objekte, Treffertests für"
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Treffertest mit Geometrie als Parameter
Dieses Beispiel zeigt, wie Sie einen [Treffertest](GTMT) für ein visuelles Objekt durchführen, indem Sie <xref:System.Windows.Media.Geometry> als Parameter verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie mit <xref:System.Windows.Media.GeometryHitTestParameters> für die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>\-Methode ein Treffertest eingerichtet wird.  Der an die `OnMouseDown`\-Methode übergebene <xref:System.Windows.Point>\-Wert wird zum Erstellen eines <xref:System.Windows.Media.Geometry>\-Objekts verwendet, um den Bereich des Treffertests zu erweitern.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 Die <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A>\-Eigenschaft von <xref:System.Windows.Media.GeometryHitTestResult> stellt Informationen über die Ergebnisse eines Treffertests bereit, in dem eine <xref:System.Windows.Media.Geometry> als Treffertestparameter verwendet wird.  In der folgenden Abbildung wird die Beziehung zwischen der Treffertestgeometrie \(der blaue Kreis\) und dem gerenderten Inhalt des Zielobjekts \(das rote Quadrat\) dargestellt.  
  
 ![Diagramm von IntersectionDetail bei Treffertests](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")  
Schnittmenge einer Treffertestgeometrie und eines Zielobjekts  
  
 Das folgende Beispiel zeigt, wie Sie einen Treffertestrückruf implementieren, wenn <xref:System.Windows.Media.Geometry> als Treffertestparameter verwendet wird.  Der `result`\-Parameter wird in ein <xref:System.Windows.Media.GeometryHitTestResult> umgewandelt, um den Wert der <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A>\-Eigenschaft abzurufen.  Mit diesem Eigenschaftswert können Sie feststellen, ob der <xref:System.Windows.Media.Geometry>\-Treffertestparameter ganz oder teilweise im gerenderten Inhalt des Treffertestziels enthalten ist.  In diesem Fall fügt der Beispielcode der Liste visueller Objekte nur Treffertestergebnisse hinzu, die vollständig im Zielbereich enthalten sind.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  Rufen Sie den <xref:System.Windows.Media.HitTestResult>\-Rückruf nicht auf, wenn die Schnittmenge den Wert <xref:System.Windows.Media.IntersectionDetail> aufweist.  
  
## Siehe auch  
 [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [Treffertest für eine Geometrie in einem visuellen Objekt](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)