---
title: "Gewusst wie: Kacheln einer Form mit einem Bild | Microsoft Docs"
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
  - "Bitmaps [Windows Forms], Füllen von Formen mit"
  - "Bilder [Windows Forms], Füllen von Formen mit"
  - "Formen, Kacheln mit Bildern"
  - "Strukturpinsel, Kacheln mit Bildern mithilfe von"
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Kacheln einer Form mit einem Bild
Genauso wie ein Fußboden mit nebeneinander liegenden Fliesen gekachelt sein kann, kann eine Form durch nebeneinander liegende rechteckige Bilder ausgefüllt \("gekachelt"\) werden.  Um das Innere einer Form zu kacheln, verwenden Sie einen Strukturpinsel.  Wenn Sie ein <xref:System.Drawing.TextureBrush>\-Objekt erstellen, ist eines der an den Konstruktor übergebenen Argumente ein <xref:System.Drawing.Image>\-Objekt.  Wenn Sie das Innere einer Form mit dem Strukturpinsel zeichnen, wird die Form mit wiederholten Kopien dieses Bildes ausgefüllt.  
  
 Durch die Umbruchmoduseigenschaft des <xref:System.Drawing.TextureBrush>\-Objekts wird bestimmt, mit welcher Ausrichtung ein Bild in einem rechteckigen Raster wiederholt wird.  Alle Kacheln im Raster können entweder dieselbe Ausrichtung haben, oder Sie lassen das Bild von einer Rasterposition zur nächsten kippen.  Das Kippen kann horizontal, vertikal oder in beide Richtungen erfolgen.  Im folgenden Beispiel wird veranschaulicht, wie eine Form mit verschiedenen Kipparten gekachelt wird.  
  
### So kacheln Sie ein Bild  
  
-   In diesem Beispiel wird das folgende 75×75\-Bild verwendet, um ein 200×200\-Rechteck zu kacheln.  
  
 ![Fläche 1](../../../../docs/framework/winforms/advanced/media/tile1.png "tile1")  
  
-   In der folgenden Abbildung wird gezeigt, wie das Rechteck mit dem Bild gekachelt wird.  Beachten Sie, dass alle Kacheln dieselbe Ausrichtung haben; es wird also keine Kachel gekippt.  
  
 ![Fläche 2](../../../../docs/framework/winforms/advanced/media/tile2.png "tile2")  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### So kippen Sie ein Bild für das Kacheln horizontal  
  
-   In diesem Beispiel wird dasselbe 75×75\-Bild verwendet, um ein 200×200\-Rechteck auszufüllen.  Der Umbruchmodus ist so festgelegt, dass das Bild horizontal gekippt wird.  In der folgenden Abbildung wird gezeigt, wie das Rechteck mit dem Bild gekachelt wird.  Beachten Sie, während Sie in einer bestimmten Zeile von einer Kachel zur nächsten übergehen, dass das Bild horizontal gekippt ist.  
  
 ![Fläche 3](../../../../docs/framework/winforms/advanced/media/tile3.png "tile3")  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### So kippen Sie ein Bild für das Kacheln vertikal  
  
-   In diesem Beispiel wird dasselbe 75×75\-Bild verwendet, um ein 200×200\-Rechteck auszufüllen.  Der Umbruchmodus ist so festgelegt, dass das Bild vertikal gekippt wird.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### So kippen Sie ein Bild für das Kacheln horizontal und vertikal  
  
-   In diesem Beispiel wird dasselbe 75×75\-Bild verwendet, um ein 200×200\-Rechteck zu kacheln.  Der Umbruchmodus ist so festgelegt, dass das Bild sowohl horizontal als auch vertikal gekippt wird.  In der folgenden Abbildung wird gezeigt, wie das Rechteck mit dem Bild gekachelt wird.  Beachten Sie, während Sie in einer bestimmten Zeile von einer Kachel zur nächsten übergehen, dass das Bild horizontal gekippt ist, und dass es vertikal gekippt ist, wenn Sie in einer bestimmten Spalte von einer Kachel zur nächsten übergehen.  
  
 ![Fläche 5](../../../../docs/framework/winforms/advanced/media/tile5.png "tile5")  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## Siehe auch  
 [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)