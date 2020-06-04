---
title: Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen
ms.date: 07/20/2015
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
ms.openlocfilehash: 29072479db36f9f8a81ffd7f3f5b10208ebaa984
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410656"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen (Visual Basic)
In den meisten Fällen können Sie die Eigenschaften und Methoden eines Objekts zur Entwurfszeit ermitteln und Code schreiben, um Sie zu behandeln. In einigen Fällen wissen Sie jedoch möglicherweise nicht, welche Eigenschaften und Methoden eines Objekts im voraus sind, oder Sie möchten, dass ein Endbenutzer die Möglichkeit bietet, Eigenschaften anzugeben oder Methoden zur Laufzeit auszuführen.  
  
## <a name="callbyname-function"></a>CallByName-Funktion  
 Stellen Sie sich z. b. eine Client Anwendung vor, die vom Benutzer eingegebene Ausdrücke auswertet, indem Sie einen Operator an eine COM-Komponente übergeben. Angenommen, Sie fügen der Komponente, die neue Operatoren erfordert, ständig neue Funktionen hinzu. Wenn Sie standardmäßige Objekt Zugriffs Verfahren verwenden, müssen Sie die Client Anwendung erneut kompilieren und verteilen, bevor Sie die neuen Operatoren verwenden können. Um dies zu vermeiden, können Sie die-Funktion verwenden, `CallByName` um die neuen Operatoren als Zeichen folgen zu übergeben, ohne die Anwendung zu ändern.  
  
 Mit der- `CallByName` Funktion können Sie zur Laufzeit eine Eigenschaft oder Methode mit einer Zeichenfolge angeben. Die Signatur für die- `CallByName` Funktion sieht wie folgt aus:  
  
 *Result*  =  Ergebnis `CallByName` (*Object*, *prozebauname*, *CallType*, *Arguments*())  
  
 Das erste Argument, *Objekt*, nimmt den Namen des Objekts an, auf das Sie reagieren möchten. Das *prozedurename* -Argument nimmt eine Zeichenfolge an, die den Namen der aufzurufenden Methode oder Eigenschaften Prozedur enthält. Das *CallType* -Argument nimmt eine Konstante an, die den aufzurufenden Aufgabentyp darstellt: eine Methode ( `Microsoft.VisualBasic.CallType.Method` ), eine Eigenschaften Lesemethode ( `Microsoft.VisualBasic.CallType.Get` ) oder ein Eigenschaften Satz ( `Microsoft.VisualBasic.CallType.Set` ). Das *Argument Argument, das optional* ist, nimmt ein Array vom Typ an, `Object` das Argumente der Prozedur enthält.  
  
 Sie können `CallByName` mit Klassen in der aktuellen Projekt Mappe verwenden, aber es wird am häufigsten verwendet, um auf COM-Objekte oder-Objekte aus .NET Framework Assemblys zuzugreifen.  
  
 Angenommen, Sie fügen einen Verweis auf eine Assembly hinzu, die eine Klasse mit dem Namen enthält, `MathClass` die eine neue Funktion mit dem Namen aufweist `SquareRoot` , wie im folgenden Code gezeigt:  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 Die Anwendung kann Textfeld-Steuerelemente verwenden, um zu steuern, welche Methode und ihre Argumente aufgerufen werden. Wenn z. b. `TextBox1` den auszuwertenden Ausdruck enthält und `TextBox2` zur Eingabe des Namens der Funktion verwendet wird, können Sie den folgenden Code verwenden, um die `SquareRoot` Funktion für den Ausdruck in aufzurufen `TextBox1` :  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 Wenn Sie "64" in `TextBox1` , "quaderoot" in eingeben `TextBox2` und dann die Prozedur aufzurufen `CallMath` , wird die Quadratwurzel der Zahl in `TextBox1` ausgewertet. Der Code im Beispiel ruft die `SquareRoot` -Funktion auf (die eine Zeichenfolge, die den Ausdruck enthält, als erforderliches Argument ausgewertet) und "8" in `TextBox1` (die Quadratwurzel von 64) zurückgibt. Wenn der Benutzer natürlich in eine ungültige Zeichenfolge eingibt `TextBox2` , wenn die Zeichenfolge den Namen einer Eigenschaft anstelle einer Methode enthält, oder wenn die Methode über ein zusätzliches erforderliches Argument verfügt, tritt ein Laufzeitfehler auf. Sie müssen robusten Fehler Behandlungs Code hinzufügen, wenn Sie verwenden `CallByName` , um diese oder andere Fehler vorherzusagen.  
  
> [!NOTE]
> Obwohl die `CallByName` Funktion in einigen Fällen nützlich sein kann, müssen Sie Ihre Nützlichkeit gegen die Auswirkungen auf die Leistung abwägen – die Verwendung `CallByName` von zum Aufrufen einer Prozedur ist etwas langsamer als ein spät gebundener Aufruf. Wenn Sie eine Funktion aufrufen, die wiederholt aufgerufen wird, wie z. b. innerhalb einer-Schleife, kann sich die `CallByName` Leistung stark negativ auf die Leistung auswirken.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [Bestimmen des Objekttyps](determining-object-type.md)
