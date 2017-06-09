---
title: "Gewusst wie: Ausf&#252;llen einer Form mit einer Volltonfarbe | Microsoft Docs"
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
  - "Farben, Hinzufügen zu Formen"
  - "Formen, Füllen"
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Ausf&#252;llen einer Form mit einer Volltonfarbe
Um eine Form mit einer Volltonfarbe auszufüllen, erstellen Sie ein <xref:System.Drawing.SolidBrush>\-Objekt und übergeben dieses <xref:System.Drawing.SolidBrush>\-Objekt dann als Argument an eine der Füllmethoden der <xref:System.Drawing.Graphics>\-Klasse.  Im folgenden Beispiel wird gezeigt, wie Sie eine Ellipse mit der Farbe Rot füllen.  
  
## Beispiel  
 Im folgenden Code benötigt der <xref:System.Drawing.SolidBrush.%23ctor%2A>\-Konstruktor ein <xref:System.Drawing.Color>\-Objekt als einziges Argument.  Die von der <xref:System.Drawing.Color.FromArgb%2A>\-Methode verwendeten Werte stellen die Alpha\-, Rot\-, Grün\- und Blauanteile der Farbe dar.  Jeder dieser Werte muss im Bereich 0 bis 255 liegen.  Der erste Wert von 255 gibt an, dass die Farbe nicht transparent ist, und der zweite Wert von 255 gibt an, dass der Rotanteil die höchste Intensität hat.  Die beiden Nullen geben an, dass sowohl der Grün\- als auch der Blauanteil eine Intensität von 0 haben.  
  
 Die vier an die <xref:System.Drawing.Graphics.FillEllipse%2A>\-Methode übergebenen Zahlen \(0, 0, 100, 60\) geben die Position und Größe des die Ellipse umschließenden Rechtecks an.  Die obere linke Ecke des Rechtecks liegt bei \(0, 0\); es hat eine Breite von 100 und eine Höhe von 60 Einheiten.  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)