---
title: 'Gewusst wie: Erstellen einer privaten Schriftartenauflistung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: 824d42c40b07e8662395e7a1286b9a5a6112c415
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-private-font-collection"></a>Gewusst wie: Erstellen einer privaten Schriftartenauflistung
Die <xref:System.Drawing.Text.PrivateFontCollection> Klasse erbt von der <xref:System.Drawing.Text.FontCollection> abstrakte Basisklasse. Sie können eine <xref:System.Drawing.Text.PrivateFontCollection> Objekt, das einen Satz von Schriftarten, die speziell für Ihre Anwendung zu verwalten. Installierten Systemschriftarten sowie Schriftarten, die nicht auf dem Computer installiert wurden, kann einer privaten schriftartenauflistung einschließen. Um eine Schriftartdatei zu einer privaten schriftartenauflistung hinzuzufügen, rufen Sie die <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> Methode von einer <xref:System.Drawing.Text.PrivateFontCollection> Objekt.  
  
 Die <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft von einem <xref:System.Drawing.Text.PrivateFontCollection> Objekt enthält ein Array von <xref:System.Drawing.FontFamily> Objekte.  
  
 Die Anzahl der Schriftfamilien in einer privaten schriftartenauflistung entspricht nicht unbedingt die Anzahl der Schriftartdateien, die der Auflistung hinzugefügt wurden. Nehmen wir beispielsweise an, dass Sie die Dateien ArialBd.tff, Times.tff und TimesBd.tff einer Sammlung hinzufügen. Es werden drei Dateien, aber nur zwei Familien in der Auflistung da Times.tff und TimesBd.tff derselben Familie angehören.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel fügt die folgenden drei Schriftartdateien zu einem <xref:System.Drawing.Text.PrivateFontCollection> Objekt:  
  
-   "C:"\\*Systemroot*\Fonts\Arial.tff (Arial, regulären)  
  
-   "C:"\\*Systemroot*\Fonts\CourBI.tff (Courier New, fett, kursiv)  
  
-   "C:"\\*Systemroot*\Fonts\TimesBd.tff (Times New Roman fett)  
  
 Der Code Ruft ein Array von <xref:System.Drawing.FontFamily> Objekte aus der <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft von der <xref:System.Drawing.Text.PrivateFontCollection> Objekt.  
  
 Für jede <xref:System.Drawing.FontFamily> Objekt in der Auflistung, die der Code Ruft die <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> Methode, um zu bestimmen, ob verschiedene Formateigenschaften (Normal, fett, kursiv, fett, kursiv, unterstrichen und durchgestrichen) verfügbar sind. Die Argumente zu übergeben, um die <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> Methode sind Mitglied der <xref:System.Drawing.FontStyle> Enumeration.  
  
 Wenn Sie eine Kombination der angegebenen Familie/Formats verfügbar ist, wird ein <xref:System.Drawing.Font> -Objekt erstellt wird, verwenden diese Familie und des Stils. Das erste Argument zu übergeben, um die <xref:System.Drawing.Font.%23ctor%2A> Konstruktor ist, den Namen der Schriftfamilie (keine <xref:System.Drawing.FontFamily> Objekt wie bei anderen Variationen der Fall ist die <xref:System.Drawing.Font.%23ctor%2A> Konstruktor). Nach der <xref:System.Drawing.Font> Objekt erstellt wurde, erfolgt eine Übergabe an die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> Klasse, um den Familiennamen zusammen mit dem Namen der Formatvorlage anzuzeigen.  
  
 Die Ausgabe des folgenden Codes ähnelt der Ausgabe, die in der folgenden Abbildung gezeigt.  
  
 ![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")  
  
 Arial.tff (die im folgenden Codebeispiel wird die privaten schriftartenauflistung hinzugefügt wurde) wird die Schriftartdatei für Arial Schriftschnitt. Beachten Sie jedoch, dass die Programmausgabe mehrere verfügbaren Formate als reguläre für die Schriftart Arial Familie anzeigt. Grund hierfür ist, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fett, kursiv und Fett Kursiv Stile vom Schriftschnitt simulieren können. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] kann außerdem unterstrichen und durchgestrichen vom Schriftschnitt Normal erstellen.  
  
 Auf ähnliche Weise [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fett kursive Formatierung von Schriftschnitt Fett oder kursiv Stil simulieren können. Die Ausgabe zeigt an, dass fett kursive Formatierung für die Familie Zeiten verfügbar ist, obwohl TimesBd.tff (Times New Roman fett) die einzige ist Times-Datei in der Auflistung.  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
