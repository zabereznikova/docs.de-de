---
title: 'Gewusst wie: Drehen, Spiegeln und Zerren von Bildern'
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
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eaa6286731d196dad387e1648644ca3e8103da03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>Gewusst wie: Drehen, Spiegeln und Zerren von Bildern
Sie können drehen, wider und ein Bild von Zielpunkte für die oberen linken, oberen rechten und unteren linken Ecke des ursprünglichen Bilds verzerren. Die drei Zielpunkte bestimmen eine affine Transformation, die ein Parallelogramm dem ursprungsabbild rechteckigen zuordnet.  
  
## <a name="example"></a>Beispiel  
 Nehmen wir beispielsweise an, die das ursprüngliche Bild ist ein Rechteck mit der linken oberen Ecke an (0, 0), rechten oberen Ecke an (100, 0), und der unteren linken Ecke auf (0, 50). Jetzt angenommen, Sie ordnen Sie die Punkte drei Zielpunkte wie folgt.  
  
|Ursprüngliche Punkt|Zielpunkt|  
|--------------------|-----------------------|  
|Linke (0, 0)|(200, 20)|  
|Rechts (100, 0)|(110, 100)|  
|Unten links (0, 50)|(250, 30)|  
  
 Die folgende Abbildung zeigt das ursprüngliche Image und das Bild, das Parallelogramm zugeordnet ist. Das ursprüngliche Image wurde verzerrt wiedergegeben, gedreht übersetzt und wurden. Die Zeile, die ausgeführt, über wird die x-Achse entlang des oberen Randes des ursprünglichen Bilds zugeordnet ist (200, 20) und (110, 100). Die Zeile, die ausgeführt, über wird die y-Achse entlang des linken Randes des ursprünglichen Bilds zugeordnet ist (200, 20) und (250, 30).  
  
 ![Streifen](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 Die folgende Abbildung zeigt eine ähnliche Transformation auf ein Foto angewendet.  
  
 ![Transformiert Anstieg](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 Die folgende Abbildung zeigt eine ähnliche Transformation, die auf eine Metadatei angewendet.  
  
 ![Transformiert Metadatei](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 Im folgenden Beispiel wird die Bilder, die in der ersten Abbildung gezeigt.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers. Achten Sie darauf, ersetzen Sie `Stripes.bmp` durch den Pfad zu einem Bild, das auf Ihrem System gültig ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
