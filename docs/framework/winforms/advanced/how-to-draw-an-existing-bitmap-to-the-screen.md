---
title: 'Gewusst wie: Zeichnen einer vorhandenen Bitmap auf dem Bildschirm'
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
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b3c8aef4aee74fbcdcc80301f5d5c1020883341
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>Gewusst wie: Zeichnen einer vorhandenen Bitmap auf dem Bildschirm
Sie können ein vorhandenes Image einfach auf dem Bildschirm zeichnen. Zunächst müssen Sie erstellen eine <xref:System.Drawing.Bitmap> Objekt mithilfe der Bitmapkonstruktor, der einen Dateinamen akzeptiert <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>. Dieser Konstruktor akzeptiert Bilder mit unterschiedlichen Dateiformaten, z. B. BMP, GIF, JPEG, PNG und TIFF. Nach der Erstellung der <xref:System.Drawing.Bitmap> Objekt, und übergeben, die <xref:System.Drawing.Bitmap> -Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A> Methode von einer <xref:System.Drawing.Graphics> Objekt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird ein <xref:System.Drawing.Bitmap> Objekt aus einer JPEG-Datei, und klicken Sie dann zeichnet die Bitmap mit der linken oberen Ecke an (60, 10).  
  
 Die folgende Abbildung zeigt die Bitmap gezeichnet, die an der angegebenen Position.  
  
 ![Abbildung Position](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
