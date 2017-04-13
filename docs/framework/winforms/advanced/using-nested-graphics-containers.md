---
title: "Verwenden geschachtelter Grafikcontainer | Microsoft Docs"
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
  - "Grafiken [Windows Forms], Clipping"
  - "Grafiken, Geschachtelte Container"
  - "Grafiken, Transformationen in geschachtelten Objekten"
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Verwenden geschachtelter Grafikcontainer
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] stellt Container bereit, mit denen Sie Teile des in einem <xref:System.Drawing.Graphics>\-Objekt festgelegten Zustands vorübergehend ersetzen oder erweitern können.  Sie erstellen einen Container, indem Sie die <xref:System.Drawing.Graphics.BeginContainer%2A>\-Methode eines <xref:System.Drawing.Graphics>\-Objekts aufrufen.  <xref:System.Drawing.Graphics.BeginContainer%2A> kann wiederholt aufgerufen werden, um geschachtelte Container zu erstellen.  Jeder Aufruf von <xref:System.Drawing.Graphics.BeginContainer%2A> muss mit einem entsprechenden Aufruf von <xref:System.Drawing.Graphics.EndContainer%2A> abgeschlossen werden.  
  
## Transformationen in geschachtelten Containern  
 Im folgenden Beispiel werden ein <xref:System.Drawing.Graphics>\-Objekt und ein Container innerhalb dieses <xref:System.Drawing.Graphics>\-Objekts erstellt.  Die globale Transformation des <xref:System.Drawing.Graphics>\-Objekts entspricht einer Verschiebung von 100 Einheiten in x\-Richtung und 80 Einheiten in y\-Richtung.  Die globale Transformation des Containers entspricht einer Drehung um 30 Grad.  Der Aufruf  `DrawRectangle(pen, -60, -30, 120, 60)`  wird vom Code zweimal ausgeführt.  Der erste Aufruf von <xref:System.Drawing.Graphics.DrawRectangle%2A> erfolgt innerhalb des Containers, er findet also zwischen den Aufrufen von <xref:System.Drawing.Graphics.BeginContainer%2A> und <xref:System.Drawing.Graphics.EndContainer%2A> statt.  Der zweite Aufruf von <xref:System.Drawing.Graphics.DrawRectangle%2A> erfolgt nach dem Aufruf von <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 Im vorangehenden Code wird das aus dem Container heraus gezeichnete Rechteck zunächst durch die globale Transformation des Containers \(Drehung\) und anschließend durch die globale Transformation des <xref:System.Drawing.Graphics>\-Objekts \(Verschiebung\) transformiert.  Auf das außerhalb des Containers gezeichnete Rechteck wird lediglich die globale Transformation des <xref:System.Drawing.Graphics>\-Objekts \(Verschiebung\) angewendet.  In der folgenden Abbildung sind die beiden Rechtecke dargestellt.  
  
 ![Geschachtelte Container](../../../../docs/framework/winforms/advanced/media/csnestedcontainers1.png "csnestedcontainers1")  
  
## Clipping in geschachtelten Containern  
 Im folgenden Beispiel wird veranschaulicht, wie Clippingbereiche von geschachtelten Containern behandelt werden.  Im Code werden ein <xref:System.Drawing.Graphics>\-Objekt und ein Container innerhalb dieses <xref:System.Drawing.Graphics>\-Objekts erstellt.  Der Clippingbereich des <xref:System.Drawing.Graphics>\-Objekts ist ein Rechteck und der des Containers eine Ellipse.  Der Code führt zwei <xref:System.Drawing.Graphics.DrawLine%2A>\-Methodenaufrufe aus.  Der erste Aufruf von <xref:System.Drawing.Graphics.DrawLine%2A> erfolgt innerhalb und der zweite Aufruf von <xref:System.Drawing.Graphics.DrawLine%2A> außerhalb des Containers \(nach dem Aufruf von <xref:System.Drawing.Graphics.EndContainer%2A>\).  Die erste Linie wird abgeschnitten, da sich die beiden Clippingbereiche schneiden.  Die zweite Linie wird nur durch den rechteckigen Clippingbereich des <xref:System.Drawing.Graphics>\-Objekts abgeschnitten.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 In der folgenden Abbildung sind die beiden abgeschnittenen Linien dargestellt.  
  
 ![Geschachtelter Container](../../../../docs/framework/winforms/advanced/media/nestedcontainers2.png "nestedcontainers2")  
  
 Aus den beiden vorherigen Beispielen ist ersichtlich, dass Transformationen und Clippingbereiche in geschachtelten Containern kumulativ sind.  Wenn Sie die globalen Transformationen von Container und <xref:System.Drawing.Graphics>\-Objekt festlegen, werden auf die aus dem Container heraus gezeichneten Elemente beide Transformationen angewendet.  Zuerst wird die Transformation des Containers und anschließend die Transformation des <xref:System.Drawing.Graphics>\-Objekts angewendet.  Wenn Sie sowohl den Clippingbereich des Containers als auch den des <xref:System.Drawing.Graphics>\-Objekts definieren, werden die aus dem Container heraus gezeichneten Elemente abgeschnitten, da die beiden Clippingbereiche einander schneiden.  
  
## Qualitätseinstellungen in geschachtelten Containern  
 Qualitätseinstellungen \(<xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.TextRenderingHint%2A> u. ä.\) in geschachtelten Containern sind nicht kumulativ. Vielmehr werden die Qualitätseinstellungen eines <xref:System.Drawing.Graphics>\-Objekts temporär durch die Qualitätseinstellungen des Containers ersetzt.  Wenn Sie einen neuen Container erstellen, werden als Qualitätseinstellungen für diesen Container Standardwerte festgelegt.  Angenommen, bei einem <xref:System.Drawing.Graphics>\-Objekt wurde für den Glättungsmodus <xref:System.Drawing.Drawing2D.SmoothingMode> festgelegt.  Wenn Sie einen Container erstellen, wird der Glättungsmodus innerhalb des Containers automatisch zum Standardmodus.  Der Glättungsmodus des Containers kann beliebig festgelegt werden, und alle aus dem Container heraus gezeichneten Elemente werden entsprechend diesem Modus gezeichnet.  Auf Elemente, die nach dem Aufruf von <xref:System.Drawing.Graphics.EndContainer%2A> gezeichnet werden, wird der Glättungsmodus \(<xref:System.Drawing.Drawing2D.SmoothingMode>\) angewendet, der vor dem Aufruf von <xref:System.Drawing.Graphics.BeginContainer%2A> gültig war.  
  
## Auf mehreren Ebenen geschachtelte Container  
 In einem <xref:System.Drawing.Graphics>\-Objekt können mehrere Container geschachtelt werden.  Sie können eine Abfolge von Containern erstellen, wobei jeder in seinem Vorgänger geschachtelt ist. Außerdem können globale Transformation, Clippingbereich und Qualitätseinstellungen jedes einzelnen Containers festgelegt werden.  Wenn Sie eine Zeichenmethode aus dem innersten Container aufrufen, werden die Transformationen in der entsprechenden Reihenfolge angewendet, also beginnend beim innersten Container bis hin zum äußersten Container.  Elemente, die aus dem innersten Container gezeichnet werden, werden dort abgeschnitten, wo sich die Clippingbereiche schneiden.  
  
 Im folgenden Beispiel wird ein <xref:System.Drawing.Graphics>\-Objekt erstellt und sein TextRenderingHint auf <xref:System.Drawing.Drawing2D.SmoothingMode> festgelegt.  Durch den Code werden zwei Container erstellt, die ineinander geschachtelt sind.  Der TextRenderingHint des äußeren Containers ist auf <xref:System.Drawing.Text.TextRenderingHint> und der des inneren Containers auf <xref:System.Drawing.Drawing2D.SmoothingMode> festgelegt.  Durch den Code werden drei Zeichenfolgen gezeichnet: eine aus dem inneren Container, eine aus dem äußeren Container und eine dritte aus dem <xref:System.Drawing.Graphics>\-Objekt selbst.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 In der folgenden Abbildung sind die drei Zeichenfolgen dargestellt.  Die aus dem inneren Container und dem <xref:System.Drawing.Graphics>\-Objekt gezeichneten Zeichenfolgen werden durch Antialiasing geglättet.  Die Zeichenfolge aus dem äußeren Container wird nicht durch Antialiasing geglättet, da die <xref:System.Drawing.Graphics.TextRenderingHint%2A>\-Eigenschaft den Wert <xref:System.Drawing.Text.TextRenderingHint> hat.  
  
 ![Geschachtelte Container](../../../../docs/framework/winforms/advanced/media/nestedcontainers3.png "nestedcontainers3")  
  
## Siehe auch  
 <xref:System.Drawing.Graphics>   
 [Verwalten des Zustands eines Graphics\-Objekts](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)