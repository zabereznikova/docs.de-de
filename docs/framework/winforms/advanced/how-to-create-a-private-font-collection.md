---
title: 'Vorgehensweise: Erstellen einer privaten Schriftartenauflistung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: f78d48c88b72388676f5e7ae963b98d8f1b4beac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210687"
---
# <a name="how-to-create-a-private-font-collection"></a>Vorgehensweise: Erstellen einer privaten Schriftartenauflistung
Die <xref:System.Drawing.Text.PrivateFontCollection> Klasse erbt von der <xref:System.Drawing.Text.FontCollection> abstrakte Basisklasse. Sie können eine <xref:System.Drawing.Text.PrivateFontCollection> Objekt, das einen Satz von Schriftarten, die speziell für Ihre Anwendung zu verwalten. Installierte Systemschriftarten sowie Schriftarten, die nicht auf dem Computer installiert wurden, kann eine privaten schriftartenauflistung enthalten. Rufen Sie zum Hinzufügen einer Schriftartdatei zu einer privaten schriftartenauflistung der <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> Methode eine <xref:System.Drawing.Text.PrivateFontCollection> Objekt.  
  
 Die <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft eine <xref:System.Drawing.Text.PrivateFontCollection> Objekt enthält ein Array von <xref:System.Drawing.FontFamily> Objekte.  
  
 Die Anzahl der Schriftfamilien in einer privaten schriftartenauflistung ist nicht unbedingt mit dem die Anzahl der Schriftartdateien, die der Auflistung hinzugefügt wurden. Nehmen wir beispielsweise an, dass Sie die Dateien ArialBd.tff Times.tff und TimesBd.tff zu einer Sammlung hinzufügen. Es werden drei Dateien, aber nur zwei Familien in der Auflistung da Times.tff und TimesBd.tff derselben Sprachfamilie angehören.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel fügt die folgenden drei Schriftartdateien in einem <xref:System.Drawing.Text.PrivateFontCollection> Objekt:  
  
-   "C:"\\*Systemroot*\Fonts\Arial.tff (Arial, reguläre)  
  
-   "C:"\\*Systemroot*\Fonts\CourBI.tff (Courier New, fett, kursiv)  
  
-   "C:"\\*Systemroot*\Fonts\TimesBd.tff (Times New Roman fett formatiert)  
  
 Der Code Ruft ein Array von <xref:System.Drawing.FontFamily> Objekte aus der <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft der <xref:System.Drawing.Text.PrivateFontCollection> Objekt.  
  
 Für jede <xref:System.Drawing.FontFamily> Objekt in der Auflistung, die der Code Ruft die <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> Methode, um zu bestimmen, ob die verschiedenen Stile (Normal, fett, kursiv, fett, kursiv, unterstrichen und durchgestrichen) verfügbar sind. Die Argumente zu übergeben, um die <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> Methode sind Mitglieder der <xref:System.Drawing.FontStyle> Enumeration.  
  
 Wenn eine Kombination der angegebenen Familie / "Style" verfügbar ist, wird eine <xref:System.Drawing.Font> Objekt wird anhand dieser Kategorie und Stil erstellt. Das erste Argument zu übergeben, um die <xref:System.Drawing.Font.%23ctor%2A> Konstruktor ist, den Namen der Schriftfamilie (keinen <xref:System.Drawing.FontFamily> Objekt wie bei anderen Varianten des der Fall ist die <xref:System.Drawing.Font.%23ctor%2A> Konstruktor). Nach der <xref:System.Drawing.Font> -Objekt erstellt wird, erfolgt eine Übergabe an die <xref:System.Drawing.Graphics.DrawString%2A> -Methode der der <xref:System.Drawing.Graphics> Klasse, um den Familiennamen, zusammen mit dem Namen der Formatvorlage anzuzeigen.  
  
 Die Ausgabe des folgenden Codes ähnelt die Ausgabe in der folgenden Abbildung gezeigt:  
  
 ![Screenshot mit Text in verschiedenen Schriftarten.](./media/how-to-create-a-private-font-collection/various-fonts-text-output.png)  
  
 Arial.tff (die im folgenden Codebeispiel wird der private Schriftart-Auflistung hinzugefügt wurde) ist die Schriftart für Arial Schriftschnitt. Beachten Sie jedoch, dass das Programm mehrere verfügbaren Formate als reguläre für die Familie der Schriftart Arial verwendet wird. Der Grund dafür ist [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können die fett, kursiv und Fett Kursiv Stile vom Schriftschnitt simuliert werden. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] kann außerdem unterstrichen und durchgestrichen normal vom Schriftschnitt erstellen.  
  
 Auf ähnliche Weise [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können fett kursive Formatierung aus der fettformatierung oder kursive simulieren. Die Programmausgabe zeigt, dass die fett formatierten kursive Formatierung für die Zeiten-Familie verfügbar ist, auch wenn TimesBd.tff (Times New Roman fett formatiert) die einzige ist Times-Datei in der Auflistung.  
  
 [!code-csharp[System.Drawing.FontsAndText#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Text.PrivateFontCollection>
- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
