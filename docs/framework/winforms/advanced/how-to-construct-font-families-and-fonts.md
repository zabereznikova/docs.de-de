---
title: 'Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: ceace5950ec135ea4d52081da7d1de7a820583ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-construct-font-families-and-fonts"></a>Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Schriftarten mit dem gleichen Schriftart, aber unterschiedliche Stile gruppiert in Schriftartfamilien. Die Schriftart Arial Familie enthält beispielsweise die folgenden Schriftarten:  
  
-   Arial reguläre  
  
-   Arial fett  
  
-   Arial kursiv  
  
-   Arial Bold Italic  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] vier Stile Familien verwendet: Normal, fett, kursiv und fett kursiv. Adjektive wie z. B. *eingrenzen* und *gerundet* Stile; werden nicht berücksichtigt werden Teil des Namens der Familie. Arial Narrow ist beispielsweise eine Schriftfamilie mit den folgenden Elementen:  
  
-   Arial Schmal reguläre  
  
-   Arial Schmal Fett  
  
-   Arial Schmal kursiv  
  
-   Arial Schmal Fett Kursiv  
  
 Bevor Sie mit Text zeichnen können [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], müssen Sie erstellen eine <xref:System.Drawing.FontFamily> Objekt und ein <xref:System.Drawing.Font> Objekt. Die <xref:System.Drawing.FontFamily> Objekt angibt (z. B. Arial), Schriftart und die <xref:System.Drawing.Font> Objekt gibt an, die Größe, den Stil und die Einheiten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen Schriftschnitt Schriftart Arial mit einer Größe von 16 Pixel. Im folgenden Code wird das erste Argument übergeben, um die <xref:System.Drawing.Font.%23ctor%2A> Konstruktor ist die <xref:System.Drawing.FontFamily> Objekt. Das zweite Argument gibt die Größe der Schriftart an, gemessen in Einheiten, die durch das vierte Argument identifiziert. Das dritte Argument gibt den Stil.  
  
 <xref:System.Drawing.GraphicsUnit.Pixel> ist ein Mitglied der <xref:System.Drawing.GraphicsUnit> Enumeration und <xref:System.Drawing.FontStyle.Regular> ist ein Mitglied der <xref:System.Drawing.FontStyle> Enumeration.  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
