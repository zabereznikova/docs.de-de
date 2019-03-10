---
title: 'Vorgehensweise: Laden und Anzeigen von Metadateien'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 121f285a95d0169db79bdc302d80dba03b3b40c2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720042"
---
# <a name="how-to-load-and-display-metafiles"></a>Vorgehensweise: Laden und Anzeigen von Metadateien
Die <xref:System.Drawing.Imaging.Metafile> -Klasse, die erbt die <xref:System.Drawing.Image> Klasse, stellt Methoden zum Aufzeichnen, anzeigen und Überprüfen von Rasterbildern.  
  
## <a name="example"></a>Beispiel  
 Um einen Vektorbild (Metafile) auf dem Bildschirm anzuzeigen, müssen Sie eine <xref:System.Drawing.Imaging.Metafile> Objekt und ein <xref:System.Drawing.Graphics> Objekt. Übergeben Sie den Namen einer Datei (oder einen Stream) zu einem <xref:System.Drawing.Imaging.Metafile> Konstruktor. Nach der Erstellung einer <xref:System.Drawing.Imaging.Metafile> Objekt, und übergeben, die <xref:System.Drawing.Imaging.Metafile> -Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A> -Methode der ein <xref:System.Drawing.Graphics> Objekt.  
  
 Das Beispiel erstellt eine <xref:System.Drawing.Imaging.Metafile> Objekt aus einer Datei EMF (Erweiterte Metadatei) und anschließend zeichnet das Bild mit der linken oberen Ecke auf ("60", "10").  
  
 Die folgende Abbildung zeigt die Metadatei an der angegebenen Position gezeichnet.  
  
 ![Abbildung Position](./media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch
- [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](working-with-images-bitmaps-icons-and-metafiles.md)
