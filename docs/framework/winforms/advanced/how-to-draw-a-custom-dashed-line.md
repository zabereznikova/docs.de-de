---
title: 'Vorgehensweise: Zeichnen einer benutzerdefinierten gestrichelten Linie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: 8dc1ad41cf8067bea5b811ca126ad29f5a600f69
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109186"
---
# <a name="how-to-draw-a-custom-dashed-line"></a>Vorgehensweise: Zeichnen einer benutzerdefinierten gestrichelten Linie
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet verschiedene Stile für gestrichelte Linie, die in aufgeführt sind die <xref:System.Drawing.Drawing2D.DashStyle> Enumeration. Wenn die standard-Dash-Stile nicht Ihren Anforderungen entsprechen, können Sie eine benutzerdefinierte Strichmusters erstellen.  
  
## <a name="example"></a>Beispiel  
 Um einer benutzerdefinierten gestrichelten Linie zu zeichnen, ordnen Sie die Striche und Zwischenräume in einem Array aus, und weisen Sie das Array als Wert für die <xref:System.Drawing.Pen.DashPattern%2A> Eigenschaft eine <xref:System.Drawing.Pen> Objekt. Das folgende Beispiel zeichnet eine benutzerdefinierte gestrichelte Linie, die auf Grundlage des Arrays `{5, 2, 15, 4}`. Wenn Sie die Elemente des Arrays mit der Stiftbreite 5 multiplizieren, erhalten Sie `{25, 10, 75, 20}`. Der angezeigte Bindestriche alternative lang zwischen 25 und 75, und die Leerzeichen alternative lang zwischen 10 und 20.  
  
 Die folgende Abbildung zeigt die resultierende gestrichelte Linie. Beachten Sie, dass der letzte Strich kürzer als 25 Einheiten sein, damit die Zeile am beenden kann (405, 5).  
  
 ![Darstellung eine gestrichelte Linie. ](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen Sie ein Windows Form und behandeln Sie das <xref:System.Windows.Forms.Control.Paint> Ereignis. Fügen Sie den vorherigen Code in die <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden eines Stiftes zum Zeichnen von Linien und Formen](using-a-pen-to-draw-lines-and-shapes.md)
