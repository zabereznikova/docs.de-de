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
ms.openlocfilehash: 34234ee0400e1d2ca36f2f559b63d282f590ca0d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709882"
---
# <a name="how-to-enumerate-installed-fonts"></a>Vorgehensweise: Auflisten installierter Schriftarten
Die <xref:System.Drawing.Text.InstalledFontCollection> Klasse erbt von der <xref:System.Drawing.Text.FontCollection> abstrakte Basisklasse. Sie können eine <xref:System.Drawing.Text.InstalledFontCollection> Objekt, das auf dem Computer installierten Schriftarten aufzulisten. Die <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft eine <xref:System.Drawing.Text.InstalledFontCollection> Objekt ist ein Array von <xref:System.Drawing.FontFamily> Objekte.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel listet die Namen der Schriftfamilien alle auf dem Computer installiert. Der Code Ruft die <xref:System.Drawing.FontFamily.Name%2A> Eigenschaft der einzelnen <xref:System.Drawing.FontFamily> Objekt im Array zurückgegeben werden, indem die <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft. Wie die Familiennamen abgerufen werden, werden sie eine durch Trennzeichen getrennte Liste verkettet. Die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> zeichnen die durch Trennzeichen getrennte Liste in einem Rechteck.  
  
 Wenn Sie den Beispielcode ausführen, werden die Ausgabe ähnelt, die in der folgenden Abbildung dargestellt.  
  
 ![Installierte Schriftarten](./media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist. Darüber hinaus sollten Sie importieren die <xref:System.Drawing.Text> Namespace.  
  
## <a name="see-also"></a>Siehe auch
- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
