---
title: "Gewusst wie: Verwenden des Mischmodus zum Steuern des Alphablendings | Microsoft Docs"
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
  - "Alphablending, Zusammensetzen"
  - "Farben, Mischen"
  - "Farben, Steuern der Transparenz"
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Verwenden des Mischmodus zum Steuern des Alphablendings
In manchen Situationen möchten Sie möglicherweise eine Offscreenbitmap erstellen, die über die folgenden Merkmale verfügt:  
  
-   Farben mit Alphawerten unter 255.  
  
-   Farben, für die beim Erstellen der Bitmap kein gegenseitiges Alphablending verwendet wird.  
  
-   Bei Anzeige der fertigen Bitmap wird für die Bitmapfarben ein Alphablending mit den Hintergrundfarben auf dem Anzeigegerät ausgeführt.  
  
 Um eine solche Bitmap zu erstellen, legen Sie ein leeres <xref:System.Drawing.Bitmap>\-Objekt an und erstellen dann auf der Grundlage dieser Bitmap ein <xref:System.Drawing.Graphics>\-Objekt.  Legen Sie den Mischmodus des <xref:System.Drawing.Graphics>\-Objekts auf <xref:System.Drawing.Drawing2D.CompositingMode?displayProperty=fullName> fest.  
  
## Beispiel  
 Im folgenden Beispiel wird auf der Grundlage eines <xref:System.Drawing.Bitmap>\-Objekts ein <xref:System.Drawing.Graphics>\-Objekt erstellt.  Im Code wird das <xref:System.Drawing.Graphics>\-Objekt zusammen mit zwei halbtransparenten Pinseln \(Alpha \= 160\) verwendet, um auf der Bitmap zu zeichnen.  Eine rote und eine grüne Ellipse werden im Code durch halb transparente Pinsel ausgefüllt.  Die grüne Ellipse überlappt zwar die rote Ellipse, wird jedoch nicht mit ihr gemischt, da als Mischmodus des <xref:System.Drawing.Graphics>\-Objekts <xref:System.Drawing.Drawing2D.CompositingMode> festgelegt ist.  
  
 Durch den Code wird die Bitmap zweimal auf dem Bildschirm gezeichnet: einmal auf einem weißen Hintergrund und ein weiteres Mal auf einem mehrfarbigen Hintergrund.  Die Pixel in der Bitmap, die zu den beiden Ellipsen gehören, haben einen Alphaanteil von 160. Die Ellipsen werden deshalb mit den Hintergrundfarben auf dem Bildschirm gemischt.  
  
 Die folgende Abbildung zeigt die Ausgabe des Codebeispiels.  Beachten Sie, dass die Ellipsen zwar mit dem Hintergrund, nicht aber untereinander gemischt werden.  
  
 ![Quellkopie](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")  
  
 Das Codebeispiel enthält die folgende Anweisung:  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 Wenn die Ellipsen sowohl untereinander als auch mit dem Hintergrund gemischt werden sollen, ändern Sie diese Anweisung wie folgt:  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 In der folgenden Abbildung ist das Ergebnis des geänderten Codes dargestellt.  
  
 ![Quelle stationär](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 <xref:System.Drawing.Color.FromArgb%2A>   
 [Alphablending von Linien und Füllungen](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)