---
title: 'Vorgehensweise: Festlegen von Tabstopps in gezeichnetem Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 4bf9328b63be88f487995f7b9691683167271c46
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635805"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Vorgehensweise: Festlegen von Tabstopps in gezeichnetem Text
Sie können die Tabstopps für Text festlegen, durch den Aufruf der <xref:System.Drawing.StringFormat.SetTabStops%2A> -Methode der eine <xref:System.Drawing.StringFormat> -Objekt, und klicken Sie dann übergebe <xref:System.Drawing.StringFormat> -Objekt an die <xref:System.Drawing.Graphics.DrawString%2A> -Methode der der <xref:System.Drawing.Graphics> Klasse.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> wird nicht unterstützt, Hinzufügen von Tabstopps in gezeichnetem Text, obwohl Sie vorhandene Registerkarte erweitern können nicht mehr die <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> Flag.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel legt Tabstopps auf 150, 250 und 350 fest. Anschließend zeigt der Code eine tabulatorgetrennte Liste der Namen und Testergebnisse.  
  
 Die folgende Abbildung zeigt den Text im Registerkartenformat.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 Der folgende Code übergibt zwei Argumente an die <xref:System.Drawing.StringFormat.SetTabStops%2A> Methode. Das zweite Argument ist ein Array, Registerkarte Offsets enthält. Das erste Argument zu übergeben, um <xref:System.Drawing.StringFormat.SetTabStops%2A> ist 0. Dies gibt an, dass es sich bei der erste Offset im Array an Position 0 (null) dem linken Rand des umschließenden Rechtecks gemessen wird.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.  
  
## <a name="see-also"></a>Siehe auch
- [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [Vorgehensweise: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
