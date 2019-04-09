---
title: 'Vorgehensweise: Erstellen von Miniaturbildern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 79b6258e7e6d7f16cc7a1e32a0c99dfe0eaeaa0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144013"
---
# <a name="how-to-create-thumbnail-images"></a>Vorgehensweise: Erstellen von Miniaturbildern
Eine Miniaturansicht ist eine kleine Version eines Bilds. Sie können ein Miniaturbild erstellen, durch den Aufruf der <xref:System.Drawing.Image.GetThumbnailImage%2A> Methode eine <xref:System.Drawing.Image> Objekt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus einer JPG-Datei. Das ursprüngliche Image verfügt über eine Breite von 640 Pixel und eine Höhe von 479 Pixel. Der Code erstellt ein Miniaturbild, die eine Breite von 100 Pixel und eine Höhe von 100 Pixel aufweist.  
  
 Die folgende Abbildung zeigt die Miniaturansicht.  
  
 ![Miniaturansicht](./media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  In diesem Beispiel wird eine Callback-Methode deklariert, aber nie verwendet. Alle Versionen von GDI + unterstützt.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler. Um das Beispiel auszuführen, gehen Sie folgendermaßen vor:  
  
1.  Erstellen Sie eine neue Windows Forms-Anwendung.  
  
2.  Fügen Sie den Beispielcode, in das Formular.  
  
3.  Erstellen Sie einen Ereignishandler für des Formulars des <xref:System.Windows.Forms.Control.Paint> Ereignis  
  
4.  In der <xref:System.Windows.Forms.Control.Paint> Handler, rufen die `GetThumbnail` Methode und übergeben Sie `e` für <xref:System.Windows.Forms.PaintEventArgs>.  
  
5.  Finden Sie eine Bilddatei, der Sie eine Miniaturansicht erstellen möchten.  
  
6.  In der `GetThumbnail` Methode, geben Sie den Pfad und Dateinamen an, in Ihrem Image.  
  
7.  Drücken Sie F5, um das Beispiel auszuführen.  
  
     Eine Miniaturansicht 100 x 100 wird im Formular angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- [Bilder, Bitmaps und Metadateien](images-bitmaps-and-metafiles.md)
- [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](working-with-images-bitmaps-icons-and-metafiles.md)
