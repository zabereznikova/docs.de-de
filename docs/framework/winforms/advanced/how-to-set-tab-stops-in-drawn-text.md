---
title: 'Gewusst wie: Festlegen von Tabstopps in gezeichnetem Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: e7f3fe9757db26bcc9dc9735f3d3d854edb7c099
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Gewusst wie: Festlegen von Tabstopps in gezeichnetem Text
Festlegen von Tabstopps für Text können durch Aufrufen der <xref:System.Drawing.StringFormat.SetTabStops%2A> Methode eine <xref:System.Drawing.StringFormat> Objekt und deren Übergabe, die <xref:System.Drawing.StringFormat> -Objekt an die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> Klasse.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> verfügt, die nicht unterstützen das Hinzufügen von Tabstopps in gezeichnetem Text, obwohl Sie vorhandene Registerkarte erweitern können nicht verwendet mehr die <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> Flag.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel legt Tabstopps auf 150, 250 und 350 fest. Anschließend zeigt den Code eine im Registerkartenformat Liste mit Namen und Testergebnissen.  
  
 Die folgende Abbildung zeigt den Text im Registerkartenformat.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 Folgender Code übergibt zwei Argumente an die <xref:System.Drawing.StringFormat.SetTabStops%2A> Methode. Das zweite Argument ist ein Array, Registerkarte Offsets enthält. Das erste Argument zu übergeben, um <xref:System.Drawing.StringFormat.SetTabStops%2A> ist-0 und bedeutet, dass es sich bei der erste Offset im Array an Position 0 (null) dem linken Rand des umschließenden Rechtecks gemessen wird.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
