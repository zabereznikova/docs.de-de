---
title: 'Vorgehensweise: Verwenden des Mischmodus zum Steuern des Alphablendings'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 1a5cf23890cd6183d92e33ec4e24f87c226e8ec3
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2019
ms.locfileid: "58462863"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>Vorgehensweise: Verwenden des Mischmodus zum Steuern des Alphablendings
Möglicherweise gibt es Situationen, eine Offscreen-Bitmap zu erstellen, die die folgenden Eigenschaften besitzt:  
  
-   Farben haben alpha-Werte, die kleiner als 255 sind.  
  
-   Farben sind nicht alpha miteinander kombiniert werden, wie Sie die Bitmap zu erstellen.  
  
-   Wenn Sie die fertige Bitmap angezeigt wird, sind die Farben in der Bitmap Alphablending mit den Hintergrundfarben, auf dem Anzeigegerät.  
  
 Um eine solche Bitmap zu erstellen, erstellen Sie ein leeres <xref:System.Drawing.Bitmap> Objekt an, und erstellen dann eine <xref:System.Drawing.Graphics> -Objekt auf Grundlage dieser Bitmap. Legen Sie den Modus zusammensetzt, von der <xref:System.Drawing.Graphics> -Objekt <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Graphics> Objekt auf Grundlage einer <xref:System.Drawing.Bitmap> Objekt. Der Code verwendet die <xref:System.Drawing.Graphics> Objekt zusammen mit zwei halb transparenten Pinseln (Alpha = 160) auf die Bitmap gezeichnet. Der Code füllt eine rote und einer grünen Ellipse mit der halb transparenten Pinseln. Die grüne Ellipse überschneidet sich mit der roten Ellipse, aber die grüne wird nicht mit dem roten gemischt, da die Mischmodus von der <xref:System.Drawing.Graphics> Objekt nastaven NA hodnotu <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.  
  
 Der Code zeichnet die Bitmap auf dem Bildschirm zweimal: einmal auf weißem Hintergrund und einmal auf einem Hintergrund mehrfarbige. Die Pixel in der Bitmap, die Teil von zwei Ellipsen sind über einen Alphaanteil von 160, müssen mit den Hintergrundfarben, auf dem Bildschirm die Auslassungspunkte gemischt werden.  
  
 Die folgende Abbildung zeigt die Ausgabe des Codebeispiels. Beachten Sie, dass die Ellipsen mit dem Hintergrund zwar, aber sie sind nicht miteinander kombiniert.  
  
 ![Diagramm mit Auslassungszeichen gemischt mit dem Hintergrund, nicht miteinander.](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 Das Codebeispiel enthält die folgende Anweisung:  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 Wenn Sie die Auslassungspunkte aus, um sowohl miteinander als auch mit dem Hintergrund gemischt werden möchten, ändern Sie diese Anweisung wie folgt:  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 Die folgende Abbildung zeigt die Ausgabe der überarbeitete Code.  
  
 ![Diagramm, Ellipsen zeigt gemischt zusammen und Hintergrund.](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs>`e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Color.FromArgb%2A>
- [Alphablending von Linien und Füllungen](alpha-blending-lines-and-fills.md)
