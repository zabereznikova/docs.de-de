---
title: "Stifte, Linien und Rechtecke in GDI+ | Microsoft Docs"
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
  - "Zeichnen, Linien"
  - "Zeichnen, Rechtecke"
  - "Beispiele [Windows Forms], Zeichnen von Linien und Formen"
  - "Beispiele [Windows Forms], GDI+"
  - "Beispiele [Windows Forms], Stifte"
  - "GDI+, Linien"
  - "GDI+, Stifte"
  - "GDI+, Rechtecke"
  - "Linien"
  - "Linien, Gestrichelt"
  - "Rechtecke"
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Stifte, Linien und Rechtecke in GDI+
Um mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Linien zu zeichnen, müssen Sie ein <xref:System.Drawing.Graphics>\-Objekt und ein <xref:System.Drawing.Pen>\-Objekt erstellen.  Das <xref:System.Drawing.Graphics>\-Objekt stellt die Methoden bereit, die den eigentlichen Zeichenvorgang ausführen. Das <xref:System.Drawing.Pen>\-Objekt speichert Attribute, z. B. Linienfarbe, \-stärke und \-art.  
  
## Zeichnen einer Linie  
 Beim Zeichnen einer Linie muss die <xref:System.Drawing.Graphics.DrawLine%2A>\-Methode des <xref:System.Drawing.Graphics>\-Objekts aufgerufen werden.  Das <xref:System.Drawing.Pen>\-Objekt wird als eines der Argumente an die <xref:System.Drawing.Graphics.DrawLine%2A>\-Methode übergeben.  Im folgenden Beispiel wird eine Linie vom Punkt \(4, 2\) zum Punkt \(12, 6\) gezeichnet:  
  
 [!code-csharp[LinesCurvesAndShapes#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 Da es sich bei <xref:System.Drawing.Graphics.DrawLine%2A> um eine überladene Methode der <xref:System.Drawing.Graphics>\-Klasse handelt, können Sie auf verschiedene Weisen Argumente für die Methode bereitstellen.  Beispielsweise können Sie zwei <xref:System.Drawing.Point>\-Objekte erstellen und die <xref:System.Drawing.Point>\-Objekte als Argumente an die <xref:System.Drawing.Graphics.DrawLine%2A>\-Methode übergeben:  
  
 [!code-csharp[LinesCurvesAndShapes#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## Erstellen eines Stiftes  
 Sie können bestimmte Attribute angeben, wenn Sie ein <xref:System.Drawing.Pen>\-Objekt erstellen.  Bei einem `Pen`\-Konstruktor können Sie beispielsweise Farbe und Stärke angeben.  Im folgenden Beispiel wird eine blaue Linie der Stärke 2 vom Punkt \(0, 0\) zum Punkt \(60, 30\) gezeichnet:  
  
 [!code-csharp[LinesCurvesAndShapes#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## Gestrichelte Linien und Linienenden  
 Das <xref:System.Drawing.Pen>\-Objekt stellt außerdem Eigenschaften wie <xref:System.Drawing.Pen.DashStyle%2A> bereit, mit denen Sie die Merkmale der Linie angeben können.  Im folgenden Beispiel wird eine gestrichelte Linie vom Punkt \(100, 50\) zum Punkt \(300, 80\) gezeichnet:  
  
 [!code-csharp[LinesCurvesAndShapes#44](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 Mithilfe der Eigenschaften des <xref:System.Drawing.Pen>\-Objekts können Sie viele weitere Attribute der Linie festlegen.  Die Eigenschaften <xref:System.Drawing.Pen.StartCap%2A> und <xref:System.Drawing.Pen.EndCap%2A> legen das Aussehen der Linienenden fest. Die Enden können flach, quadratisch, abgerundet oder dreieckig sein bzw. eine andere benutzerdefinierte Form aufweisen.  Mit der <xref:System.Drawing.Pen.LineJoin%2A>\-Eigenschaft können Sie angeben, ob verbundene Linien einen 45 Grad\-Winkel \(eine Gehrung\) bilden oder abgeschrägt, abgerundet oder abgeschnitten sind.  Die folgende Abbildung zeigt Linien mit verschiedenen End\- und Verbindungsstilen.  
  
 ![Linien](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.png "Aboutgdip02\_art04")  
  
## Zeichnen eines Rechtecks  
 Das Zeichnen von Rechtecken in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ähnelt dem Zeichnen von Linien.  Um ein Rechteck zu zeichnen, benötigen Sie ein <xref:System.Drawing.Graphics>\-Objekt und ein <xref:System.Drawing.Pen>\-Objekt.  Das <xref:System.Drawing.Graphics>\-Objekt stellt eine <xref:System.Drawing.Graphics.DrawRectangle%2A>\-Methode bereit, und das <xref:System.Drawing.Pen>\-Objekt enthält Attribute, wie Linienstärke und \-farbe.  Das <xref:System.Drawing.Pen>\-Objekt wird als eines der Argumente an die <xref:System.Drawing.Graphics.DrawRectangle%2A>\-Methode übergeben.  Im folgenden Beispiel wird ein Rechteck mit einer Breite von 80 und einer Höhe von 40 gezeichnet, dessen linke obere Ecke im Punkt \(100, 50\) liegt:  
  
 [!code-csharp[LinesCurvesAndShapes#45](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 Da es sich bei <xref:System.Drawing.Graphics.DrawRectangle%2A> um eine überladene Methode der <xref:System.Drawing.Graphics>\-Klasse handelt, können Sie auf verschiedene Weisen Argumente für die Methode bereitstellen.  Beispielsweise können Sie ein <xref:System.Drawing.Rectangle>\-Objekt erstellen und das <xref:System.Drawing.Rectangle>\-Objekt als Argument an die <xref:System.Drawing.Graphics.DrawRectangle%2A>\-Methode übergeben:  
  
 [!code-csharp[LinesCurvesAndShapes#46](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 Ein <xref:System.Drawing.Rectangle>\-Objekt umfasst Methoden und Eigenschaften zum Bearbeiten des Rechtecks und zum Erfassen von Informationen über das Rechteck.  Beispielsweise können Sie mit den Methoden <xref:System.Drawing.Rectangle.Inflate%2A> und <xref:System.Drawing.Rectangle.Offset%2A> die Größe und die Position des Rechtecks ändern.  Die <xref:System.Drawing.Rectangle.IntersectsWith%2A>\-Methode gibt Auskunft darüber, ob das Rechteck sich mit einem anderen Rechteck schneidet. Die <xref:System.Drawing.Rectangle.Contains%2A>\-Methode gibt an, ob sich ein bestimmter Punkt innerhalb des Rechtecks befindet.  
  
## Siehe auch  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 <xref:System.Drawing.Rectangle?displayProperty=fullName>   
 [Gewusst wie: Erstellen eines Stiftes](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)   
 [Gewusst wie: Zeichnen einer Linie in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)   
 [Gewusst wie: Zeichnen der Kontur einer Form](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)