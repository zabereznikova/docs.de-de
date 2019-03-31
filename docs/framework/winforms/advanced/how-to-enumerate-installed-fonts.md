---
title: 'Vorgehensweise: Auflisten installierter Schriftarten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: e56f06d6f7a762a1ef1ff85fa30751ea64f9f14b
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653742"
---
# <a name="how-to-enumerate-installed-fonts"></a>Vorgehensweise: Auflisten installierter Schriftarten
Die <xref:System.Drawing.Text.InstalledFontCollection> Klasse erbt von der <xref:System.Drawing.Text.FontCollection> abstrakte Basisklasse. Sie können eine <xref:System.Drawing.Text.InstalledFontCollection> Objekt, das auf dem Computer installierten Schriftarten aufzulisten. Die <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft eine <xref:System.Drawing.Text.InstalledFontCollection> Objekt ist ein Array von <xref:System.Drawing.FontFamily> Objekte.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel listet die Namen der Schriftfamilien alle auf dem Computer installiert. Der Code Ruft die <xref:System.Drawing.FontFamily.Name%2A> Eigenschaft der einzelnen <xref:System.Drawing.FontFamily> Objekt im Array zurückgegeben werden, indem die <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft. Wie die Familiennamen abgerufen werden, werden sie eine durch Trennzeichen getrennte Liste verkettet. Die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> zeichnen die durch Trennzeichen getrennte Liste in einem Rechteck.  
  
 Wenn Sie den Beispielcode ausführen, wird die Ausgabe ähnelt, die in der folgenden Abbildung dargestellt aussehen:  
  
 ![Screenshot mit der installierten Schriftfamilien.](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>. Darüber hinaus sollten Sie importieren die <xref:System.Drawing.Text> Namespace.  
  
## <a name="see-also"></a>Siehe auch
- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
