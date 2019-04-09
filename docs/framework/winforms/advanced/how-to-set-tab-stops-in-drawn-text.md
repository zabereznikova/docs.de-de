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
ms.openlocfilehash: 68dbebfc4fab773fe749f9443d0c61883099d2ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197489"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Vorgehensweise: Festlegen von Tabstopps in gezeichnetem Text
Sie können die Tabstopps für Text festlegen, durch den Aufruf der <xref:System.Drawing.StringFormat.SetTabStops%2A> -Methode der eine <xref:System.Drawing.StringFormat> -Objekt, und klicken Sie dann übergebe <xref:System.Drawing.StringFormat> -Objekt an die <xref:System.Drawing.Graphics.DrawString%2A> -Methode der der <xref:System.Drawing.Graphics> Klasse.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> wird nicht unterstützt, Hinzufügen von Tabstopps in gezeichnetem Text, obwohl Sie vorhandene Registerkarte erweitern können nicht mehr die <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> Flag.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel legt Tabstopps auf 150, 250 und 350 fest. Anschließend zeigt der Code eine tabulatorgetrennte Liste der Namen und Testergebnisse.  
  
 Die folgende Abbildung zeigt den Text im Registerkartenformat an:  
  
 ![Screenshot, der eine tabulatorgetrennte Liste der Namen und Ergebnisse anzeigt.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 Der folgende Code übergibt zwei Argumente an die <xref:System.Drawing.StringFormat.SetTabStops%2A> Methode. Das zweite Argument ist ein Array, Registerkarte Offsets enthält. Das erste Argument zu übergeben, um <xref:System.Drawing.StringFormat.SetTabStops%2A> ist 0. Dies gibt an, dass es sich bei der erste Offset im Array an Position 0 (null) dem linken Rand des umschließenden Rechtecks gemessen wird.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
- [Vorgehensweise: Zeichnen von Text mit GDI](how-to-draw-text-with-gdi.md)
