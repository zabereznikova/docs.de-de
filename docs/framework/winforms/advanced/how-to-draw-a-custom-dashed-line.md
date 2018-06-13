---
title: 'Gewusst wie: Zeichnen einer benutzerdefinierten gestrichelten Linie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: 39dde3bb45165783171326b79e98744807350952
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521614"
---
# <a name="how-to-draw-a-custom-dashed-line"></a>Gewusst wie: Zeichnen einer benutzerdefinierten gestrichelten Linie
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] stellt mehrere Stile für gestrichelte Linie, die in aufgeführt sind die <xref:System.Drawing.Drawing2D.DashStyle> Enumeration. Wenn diese Stile Gedankenstrich nicht Ihren Anforderungen entsprechen, können Sie eine benutzerdefinierte Strichmusters erstellen.  
  
## <a name="example"></a>Beispiel  
 Zum Zeichnen einer benutzerdefinierten gestrichelten Linie Größen der Striche und Zwischenräume in einem Array platzieren, und weisen Sie das Array als Wert für die <xref:System.Drawing.Pen.DashPattern%2A> Eigenschaft ein <xref:System.Drawing.Pen> Objekt. Im folgende Beispiel zeichnet eine benutzerdefinierte gestrichelte Linie, die auf Grundlage des Arrays `{5, 2, 15, 4}`. Wenn Sie die Elemente des Arrays mit der Stiftbreite 5 multiplizieren, erhalten Sie `{25, 10, 75, 20}`. Der angezeigten Bindestriche alternative lang zwischen 25 und 75 sowie die Adressbereiche alternative lang zwischen 10 und 20.  
  
 Die folgende Abbildung zeigt die resultierende gestrichelte Linie. Beachten Sie, dass der letzte Strich kürzer als 25 Einheiten sein, damit auf die Linie enden kann (405, 5).  
  
 ![Stifte](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen eines Windows Form, und behandeln Sie des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis. Fügen Sie den vorangehenden Code in der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
