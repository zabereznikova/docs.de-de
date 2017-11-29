---
title: 'Gewusst wie: Erstellen von Miniaturbildern'
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
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2a3866274340932819a419c622c10072dd67c439
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-thumbnail-images"></a>Gewusst wie: Erstellen von Miniaturbildern
Ein Miniaturbild ist eine kleine Version eines Bilds. Sie können ein Miniaturbild erstellen, durch Aufrufen der <xref:System.Drawing.Image.GetThumbnailImage%2A> Methode ein <xref:System.Drawing.Image> Objekt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus einer JPG-Datei. Das ursprüngliche Bild verfügt über eine Breite von 640 Pixel und eine Höhe von 479 Pixel. Der Code erstellt eine Miniaturansicht Image mit einer Breite von 100 Pixeln und eine Höhe von 100 Pixel.  
  
 Die folgende Abbildung zeigt die Miniaturansicht.  
  
 ![Miniaturansicht](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  In diesem Beispiel ist eine Rückrufmethode deklariert, aber nie verwendet. Alle Versionen von GDI + unterstützt.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers. Um das Beispiel auszuführen, gehen Sie folgendermaßen vor:  
  
1.  Erstellen Sie eine neue Windows Forms-Anwendung.  
  
2.  Fügen Sie den Beispielcode, in das Formular.  
  
3.  Erstellen Sie einen Ereignishandler für des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis  
  
4.  In der <xref:System.Windows.Forms.Control.Paint> Handler, rufen die `GetThumbnail` Methode und übergeben Sie `e` für <xref:System.Windows.Forms.PaintEventArgs>.  
  
5.  Suchen von Abbilddateien, die eine Miniaturansicht der machen möchten.  
  
6.  In der `GetThumbnail` -Methode, geben Sie den Pfad und Dateinamen an, in das Abbild.  
  
7.  Drücken Sie F5, um das Beispiel auszuführen.  
  
     Ein Miniaturbild Maßen 100 x 100 wird auf dem Formular angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
