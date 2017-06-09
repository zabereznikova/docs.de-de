---
title: "Bereiche in GDI+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Zeichnen, Bereiche"
  - "GDI+, Bereiche"
  - "Bereiche"
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Bereiche in GDI+
Ein Bereich ist ein Teil des Anzeigebereichs eines Ausgabegeräts.  Es gibt einfache Bereiche \(ein einzelnes Rechteck\) und komplexe Bereiche \(eine Kombination aus Polygonen und geschlossenen Kurven\).  Die folgende Abbildung zeigt zwei Bereiche: einen aus einem Rechteck konstruierten Bereich und einen aus einem Pfad konstruierten Bereich.  
  
 ![Bereiche](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.png "AboutGdip02\_Art27")  
  
## Verwenden von Bereichen  
 Bereiche werden häufig für das Clipping und zum Testen auf Treffer verwendet.  Beim Clipping wird das Zeichnen auf einen bestimmten Bereich im Anzeigebereich beschränkt, meist auf den Bereich, der aktualisiert werden muss.  Beim Testen auf Treffer wird ermittelt, ob der Cursor sich in einem bestimmten Bereich des Bildschirms befindet, wenn eine Maustaste gedrückt wird.  
  
 Sie können einen Bereich aus einem Rechteck oder aus einem Pfad konstruieren.  Außerdem können Sie komplexe Bereiche erstellen, indem Sie vorhandene Bereiche miteinander kombinieren.  Die <xref:System.Drawing.Region>\-Klasse stellt die folgenden Methoden zum Kombinieren von Bereichen bereit: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A> und <xref:System.Drawing.Region.Complement%2A>.  
  
 Die Schnittmenge zwischen zwei Bereichen ist die Menge aller Punkte, die zu beiden Bereichen gehören.  Die Union \(Vereinigung\) ist die Menge aller Punkte, die zu einem der beiden Bereiche oder zu beiden Bereichen gehören.  Die Komplementärmenge eines Bereichs ist die Menge aller Punkte, die sich nicht in dem Bereich befinden.  Die folgende Abbildung zeigt die Schnittmenge und die Vereinigungsmenge der beiden Bereiche aus der vorherigen Abbildung.  
  
 ![Bereiche](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02\_Art28")  
  
 Wenn die <xref:System.Drawing.Region.Xor%2A>\-Methode auf ein Bereichspaar angewendet wird, generiert sie einen Bereich, der alle Punkte enthält, die entweder zum einen oder zum anderen Bereich gehören, jedoch nicht zu beiden.  Wenn die <xref:System.Drawing.Region.Exclude%2A>\-Methode auf ein Bereichspaar angewendet wird, generiert sie einen Bereich, der alle Punkte aus dem ersten Bereich enthält, die nicht im zweiten Bereich enthalten sind.  Die folgende Abbildung zeigt die Bereiche, die sich durch Anwenden der <xref:System.Drawing.Region.Xor%2A>\-Methode und der <xref:System.Drawing.Region.Exclude%2A>\-Methode auf die beiden Bereiche ergeben, die zu Beginn dieses Themas abgebildet wurden.  
  
 ![Bereiche](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.png "AboutGdip02\_Art29")  
  
 Um einen Bereich zu füllen, benötigen Sie ein <xref:System.Drawing.Graphics>\-Objekt, ein <xref:System.Drawing.Brush>\-Objekt und ein <xref:System.Drawing.Region>\-Objekt.  Das <xref:System.Drawing.Graphics>\-Objekt stellt die <xref:System.Drawing.Graphics.FillRegion%2A>\-Methode bereit, und das <xref:System.Drawing.Brush>\-Objekt speichert Attribute für die Füllung, wie Farbe und Muster.  Im folgenden Beispiel wird ein Bereich mit einer Volltonfarbe gefüllt.  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## Siehe auch  
 <xref:System.Drawing.Region?displayProperty=fullName>   
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Verwenden von Bereichen](../../../../docs/framework/winforms/advanced/using-regions.md)