---
title: 'Gewusst wie: Erstellen von vertikalem Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182559"
---
# <a name="how-to-create-vertical-text"></a>Gewusst wie: Erstellen von vertikalem Text
Sie können <xref:System.Drawing.StringFormat> ein Objekt verwenden, um anzugeben, dass Text vertikal statt horizontal gezeichnet werden soll.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird <xref:System.Drawing.StringFormatFlags.DirectionVertical> der <xref:System.Drawing.StringFormat.FormatFlags%2A> Wert <xref:System.Drawing.StringFormat> der Eigenschaft eines Objekts zugewiesen. Dieses <xref:System.Drawing.StringFormat> Objekt wird <xref:System.Drawing.Graphics.DrawString%2A> an die <xref:System.Drawing.Graphics> Methode der Klasse übergeben. Der <xref:System.Drawing.StringFormatFlags.DirectionVertical> Wert ist ein <xref:System.Drawing.StringFormatFlags> Member der Enumeration.  
  
 Die folgende Abbildung zeigt den vertikalen Text:
  
 ![Grafik, die vertikalen Schrifttext anzeigt.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
- Das obige Beispiel ist für die Verwendung <xref:System.Windows.Forms.PaintEventArgs> `e` mit Windows Forms <xref:System.Windows.Forms.PaintEventHandler>konzipiert und erfordert , was ein Parameter von ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Gewusst wie: Zeichnen von Text mit GDI](how-to-draw-text-with-gdi.md)
