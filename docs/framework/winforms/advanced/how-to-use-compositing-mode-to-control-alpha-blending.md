---
title: 'Gewusst wie: Verwenden des Mischmodus zum Steuern des Alphablendings'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 564d46cb2d72ac63962657b39146489aaafd6a5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>Gewusst wie: Verwenden des Mischmodus zum Steuern des Alphablendings
Möglicherweise gibt es Zeiten, sollen eine Bitmap außerhalb des Bildschirms erstellen, die über die folgenden Eigenschaften verfügt:  
  
-   Farben haben alphanumerische Werte, die kleiner als 255 sind.  
  
-   Farben sind keinen alpha miteinander vermischt werden, wie Sie beim Erstellen der Bitmap.  
  
-   Wenn Sie die fertige Bitmap anzeigen, sind Farben in der Bitmap Alphablending mit den Hintergrundfarben auf dem Anzeigegerät.  
  
 Um eine solche Bitmap zu erstellen, erstellen Sie eine leere <xref:System.Drawing.Bitmap> -Objekt, und erstellen dann eine <xref:System.Drawing.Graphics> -Objekt auf Grundlage dieser Bitmap. Legen Sie den Modus wird von der <xref:System.Drawing.Graphics> -Objekt <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Graphics> -Objekt auf Grundlage einer <xref:System.Drawing.Bitmap> Objekt. Der Code verwendet die <xref:System.Drawing.Graphics> -Objekt zusammen mit zwei halb transparenten Pinseln (Alpha = 160) auf die Bitmap gezeichnet. Der Code füllt eine rote und eine grüne Ellipse halb transparenten Pinseln verwenden. Die grüne Ellipse überschneidet sich mit der Ellipse, die Rot, aber die grüne wird nicht mit dem roten gemischt, da die Mischmodus von der <xref:System.Drawing.Graphics> -Objekts festgelegt wird, um <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.  
  
 Der Code zeichnet die Bitmap auf dem Bildschirm zweimal: einmal auf weißem Hintergrund und einmal in einem Hintergrundthread mehrfarbige. Die Pixel in der Bitmap, die Teil von zwei Ellipsen haben einen Alphaanteil von 160, damit die Schaltfläche mit die Auslassungszeichen mit den Hintergrundfarben auf dem Bildschirm gemischt werden.  
  
 Die folgende Abbildung zeigt die Ausgabe des Codebeispiels. Beachten Sie, dass die Ellipse mit dem Hintergrund gemischt werden, aber sie sind nicht miteinander vermischt.  
  
 ![Quelle kopieren](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "Sourcecopy")  
  
 Das Codebeispiel enthält die folgende Anweisung:  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 Wenn Sie die Auslassungszeichen, um sowohl miteinander als auch mit dem Hintergrund gemischt werden soll, ändern Sie diese Anweisung, die der folgenden:  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 Die folgende Abbildung zeigt die Ausgabe des überarbeiteten Codes.  
  
 ![Quelle über](../../../../docs/framework/winforms/advanced/media/sourceover.png "Sourceover")  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs>`e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [Alphablending von Linien und Füllungen](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
