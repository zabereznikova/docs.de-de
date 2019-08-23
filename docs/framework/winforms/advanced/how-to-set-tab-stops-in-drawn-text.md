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
ms.openlocfilehash: 8821f6170b8ba588e3197ef54eab14c2719a6cc3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947818"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Vorgehensweise: Festlegen von Tabstopps in gezeichnetem Text
Sie können Tabstopps für Text festlegen, indem Sie <xref:System.Drawing.StringFormat.SetTabStops%2A> die-Methode <xref:System.Drawing.StringFormat> eines-Objekts aufrufen und <xref:System.Drawing.StringFormat> dieses Objekt anschließend <xref:System.Drawing.Graphics.DrawString%2A> an die- <xref:System.Drawing.Graphics> Methode der-Klasse übergeben.  
  
> [!NOTE]
> Unter <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> stützt das Hinzufügen von Tabstopps zum Zeichnen von Text nicht, obwohl Sie vorhandene Tabstopps mit <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> dem-Flag erweitern können.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Tabstopp bei 150, 250 und 350 festgelegt. Anschließend wird im Code eine Liste mit Namen und testbewertungen im Registerkarten Format angezeigt.  
  
 Die folgende Abbildung zeigt den Text im Registerkarten Format:  
  
 ![Screenshot, der eine Liste mit Namen und Bewertungen im Registerkarten Format anzeigt.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 Der folgende Code übergibt zwei Argumente an die <xref:System.Drawing.StringFormat.SetTabStops%2A> -Methode. Das zweite Argument ist ein Array, das Tabulator Offsets enthält. Das erste an <xref:System.Drawing.StringFormat.SetTabStops%2A> übergebenen Argument ist 0 (null), womit angegeben wird, dass der erste Offset im Array von Position 0, dem linken Rand des umgebenden Rechtecks, gemessen wird.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
- Das vorherige Beispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, was ein Parameter von <xref:System.Windows.Forms.PaintEventHandler>ist.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
- [Vorgehensweise: Zeichnen von Text mit GDI](how-to-draw-text-with-gdi.md)
