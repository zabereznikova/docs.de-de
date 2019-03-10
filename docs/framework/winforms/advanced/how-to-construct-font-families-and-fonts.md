---
title: 'Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: b651671e525ae5cfc365a392b96d258ac835a21c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708553"
---
# <a name="how-to-construct-font-families-and-fonts"></a>Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Schriftarten mit dem gleichen Schriftart, aber verschiedene Formate gruppiert in Schriftfamilien. Die Familie der Schriftart Arial enthält beispielsweise die folgenden Schriftarten:  
  
-   Arial regulären  
  
-   Arial fett  
  
-   Arial kursiv  
  
-   Arial fett kursiv  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Mithilfe von vier Formaten Familien: Normal, fett, kursiv und fett kursiv. Adjektive, z. B. *eingrenzen* und *gerundet* Stile werden nicht berücksichtigt stattdessen werden sie Teil des Namens der Familie. Arial breit genug ist z. B. eine Schriftfamilie mit den folgenden Elementen:  
  
-   Arial schmalen regulären  
  
-   Arial Schmal Fett  
  
-   Arial schmalen kursiv  
  
-   Arial schmalen fett kursiv  
  
 Bevor Sie mit Text zeichnen können [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], müssen Sie erstellen eine <xref:System.Drawing.FontFamily> Objekt und ein <xref:System.Drawing.Font> Objekt. Die <xref:System.Drawing.FontFamily> Objekt gibt an, die Schriftart (z. B. Arial), und die <xref:System.Drawing.Font> Objekt gibt an, die Größe, Stil und Einheiten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen regulären Stil Schriftart Arial mit einer Größe von 16 Pixel. Im folgenden Code wird das erste Argument übergeben, um die <xref:System.Drawing.Font.%23ctor%2A> Konstruktor ist die <xref:System.Drawing.FontFamily> Objekt. Das zweite Argument gibt an, die Größe der Schriftart in das vierte Argument identifizierte-Einheiten gemessen wird. Das dritte Argument gibt den Stil an.  
  
 <xref:System.Drawing.GraphicsUnit.Pixel> ist ein Mitglied der <xref:System.Drawing.GraphicsUnit> -Enumeration und <xref:System.Drawing.FontStyle.Regular> ist ein Mitglied der <xref:System.Drawing.FontStyle> Enumeration.  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs>`e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.  
  
## <a name="see-also"></a>Siehe auch
- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
