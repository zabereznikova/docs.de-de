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
ms.openlocfilehash: 7d66bf147a220bdcdfd32a703d3407817a184a54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521471"
---
# <a name="how-to-create-vertical-text"></a>Gewusst wie: Erstellen von vertikalem Text
Sie können eine <xref:System.Drawing.StringFormat> Objekt, um anzugeben, dass Text vertikal oder horizontal gezeichnet werden soll.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel weist den Wert <xref:System.Drawing.StringFormatFlags.DirectionVertical> auf die <xref:System.Drawing.StringFormat.FormatFlags%2A> Eigenschaft ein <xref:System.Drawing.StringFormat> Objekt. <xref:System.Drawing.StringFormat> -Objekt übergeben wird die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> Klasse. Der Wert <xref:System.Drawing.StringFormatFlags.DirectionVertical> ist ein Mitglied der <xref:System.Drawing.StringFormatFlags> Enumeration.  
  
 Die folgende Abbildung zeigt den vertikalen Text an.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")  
  
 [!code-csharp[System.Drawing.FontsAndText#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e` , einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
