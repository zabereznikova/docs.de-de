---
title: 'Gewusst wie: Laden und Anzeigen von Metadateien'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424822"
---
# <a name="how-to-load-and-display-metafiles"></a>Gewusst wie: Laden und Anzeigen von Metadateien
Die <xref:System.Drawing.Imaging.Metafile>-Klasse, die von der <xref:System.Drawing.Image>-Klasse erbt, stellt Methoden zum Aufzeichnen, anzeigen und untersuchen von Vektorbildern bereit.  
  
## <a name="example"></a>Beispiel  
 Zum Anzeigen eines Vektor Bilds (Metadatei) auf dem Bildschirm benötigen Sie ein <xref:System.Drawing.Imaging.Metafile>-Objekt und ein <xref:System.Drawing.Graphics>-Objekt. Übergeben Sie den Namen einer Datei (oder eines Datenstroms) an einen <xref:System.Drawing.Imaging.Metafile> Konstruktor. Nachdem Sie ein <xref:System.Drawing.Imaging.Metafile>-Objekt erstellt haben, übergeben Sie das <xref:System.Drawing.Imaging.Metafile>-Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A>-Methode eines <xref:System.Drawing.Graphics> Objekts.  
  
 Im Beispiel wird ein <xref:System.Drawing.Imaging.Metafile> Objekt aus einer EMF-Datei (Enhanced Metafile) erstellt und dann mit der linken oberen Ecke bei (60, 10) gezeichnet.  
  
 In der folgenden Abbildung ist die an der angegebenen Position gezeichnete Metadatendatei dargestellt.  
  
 ![Screenshot der Bildposition](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das vorherige Beispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, bei dem es sich um einen Parameter des <xref:System.Windows.Forms.Control.Paint> Ereignis Handlers handelt.  
  
## <a name="see-also"></a>Siehe auch

- [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](working-with-images-bitmaps-icons-and-metafiles.md)
