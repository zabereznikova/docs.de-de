---
title: 'Gewusst wie: Zuschneiden und Skalieren von Bildern'
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
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de905cf70013098a4282e3f4af092ccbea16ccfd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-crop-and-scale-images"></a>Gewusst wie: Zuschneiden und Skalieren von Bildern
Die <xref:System.Drawing.Graphics> Klasse stellt mehrere <xref:System.Drawing.Graphics.DrawImage%2A> Methoden, von denen einige Quell- und Zielschemas Rechteck Parameter haben, die zum Zuschneiden und Skalieren von Bildern verwendet werden können.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datenträgerdatei Apple.gif. Der Code zeichnet das gesamte Apple-Bild in seiner ursprünglichen Größe an. Der Code ruft dann die <xref:System.Drawing.Graphics.DrawImage%2A> Methode von einer <xref:System.Drawing.Graphics> Objekt, das einen Teil der Apple-Bildes in ein Zielrechteck zu zeichnen, die größer als das ursprüngliche Apple-Image ist.  
  
 Die <xref:System.Drawing.Graphics.DrawImage%2A> Methode bestimmt, welcher Teil der Apple gezogen werden unter Verwendung des fünften und sechsten Argumente suchen soll. In diesem Fall wird die Apple 75 Prozent der Breite und 75 Prozent der Höhe zugeschnitten.  
  
 Die <xref:System.Drawing.Graphics.DrawImage%2A> Methode bestimmt, wo Sie zugeschnittene Apple gezeichnet werden soll und wie groß die zugeschnittenen Apfels anhand des Zielrechtecks, dies ist durch das zweite Argument angegeben. In diesem Fall ist das Zielrechteck 30 Prozent breiter und 30 Prozent höher als das ursprüngliche Image.  
  
 Die folgende Abbildung zeigt die ursprüngliche Apple und die skalierte Apple zugeschnitten.  
  
 ![Zuschneiden und skalieren](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers. Achten Sie darauf, ersetzen Sie `Apple.gif` mit einem Dateinamen und Pfad, die auf Ihrem System gültig sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
