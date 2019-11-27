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
ms.openlocfilehash: cb584f0dfbd905ca071f9a86b1eab231f3017538
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345212"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen (Visual Basic)
In den meisten Fällen können Sie die Eigenschaften und Methoden eines Objekts zur Entwurfszeit ermitteln und Code schreiben, um Sie zu behandeln. In einigen Fällen wissen Sie jedoch möglicherweise nicht, welche Eigenschaften und Methoden eines Objekts im voraus sind, oder Sie möchten, dass ein Endbenutzer die Möglichkeit bietet, Eigenschaften anzugeben oder Methoden zur Laufzeit auszuführen.  
  
## <a name="callbyname-function"></a>CallByName-Funktion  
 Stellen Sie sich z. b. eine Client Anwendung vor, die vom Benutzer eingegebene Ausdrücke auswertet, indem Sie einen Operator an eine COM-Komponente übergeben. Angenommen, Sie fügen der Komponente, die neue Operatoren erfordert, ständig neue Funktionen hinzu. Wenn Sie standardmäßige Objekt Zugriffs Verfahren verwenden, müssen Sie die Client Anwendung erneut kompilieren und verteilen, bevor Sie die neuen Operatoren verwenden können. Um dies zu vermeiden, können Sie die `CallByName`-Funktion verwenden, um die neuen Operatoren als Zeichen folgen zu übergeben, ohne die Anwendung zu ändern.  
  
 Mit der `CallByName`-Funktion können Sie mithilfe einer Zeichenfolge zur Laufzeit eine Eigenschaft oder Methode angeben. Die Signatur für die `CallByName`-Funktion sieht wie folgt aus:  
  
 *Ergebnis* = `CallByName`(*Object*, *prozebauname*, *CallType*, *Arguments*())  
  
 Das erste Argument, *Objekt*, nimmt den Namen des Objekts an, auf das Sie reagieren möchten. Das *prozedurename* -Argument nimmt eine Zeichenfolge an, die den Namen der aufzurufenden Methode oder Eigenschaften Prozedur enthält. Das *CallType* -Argument nimmt eine Konstante an, die den aufzurufenden Aufgabentyp darstellt: eine Methode (`Microsoft.VisualBasic.CallType.Method`), eine gelesene Eigenschaft (`Microsoft.VisualBasic.CallType.Get`) oder ein Eigenschaften Satz (`Microsoft.VisualBasic.CallType.Set`). Das *Argument Argument, das optional* ist, übernimmt ein Array vom Typ `Object`, das Argumente der Prozedur enthält.  
  
 Sie können `CallByName` mit Klassen in der aktuellen Projekt Mappe verwenden, aber es wird am häufigsten verwendet, um auf COM-Objekte oder-Objekte aus .NET Framework Assemblys zuzugreifen.  
  
 Angenommen, Sie fügen einen Verweis auf eine Assembly hinzu, die eine Klasse mit dem Namen `MathClass`enthält, die eine neue Funktion mit dem Namen `SquareRoot`enthält, wie im folgenden Code gezeigt:  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 Die Anwendung kann Textfeld-Steuerelemente verwenden, um zu steuern, welche Methode und ihre Argumente aufgerufen werden. Wenn `TextBox1` z. b. den auszuwertenden Ausdruck enthält und `TextBox2` verwendet wird, um den Namen der Funktion einzugeben, können Sie den folgenden Code verwenden, um die `SquareRoot`-Funktion für den Ausdruck in `TextBox1`aufzurufen:  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 Wenn Sie in `TextBox2`den Wert "64 `TextBox1`" eingeben und dann die `CallMath` Prozedur aufzurufen, wird die Quadratwurzel der Zahl in `TextBox1` ausgewertet. Der Code im Beispiel ruft die `SquareRoot`-Funktion (die eine Zeichenfolge mit dem Ausdruck enthält, die als erforderliches Argument ausgewertet werden soll) auf und gibt "8" in `TextBox1` (die Quadratwurzel von 64) zurück. Wenn der Benutzer natürlich in `TextBox2`eine ungültige Zeichenfolge eingibt, wenn die Zeichenfolge den Namen einer Eigenschaft anstelle einer Methode enthält, oder wenn die Methode über ein zusätzliches erforderliches Argument verfügt, tritt ein Laufzeitfehler auf. Sie müssen robusten Fehler Behandlungs Code hinzufügen, wenn Sie `CallByName` verwenden, um diese oder andere Fehler vorherzusagen.  
  
> [!NOTE]
> Obwohl die `CallByName`-Funktion in einigen Fällen nützlich sein kann, müssen Sie Ihre Nützlichkeit gegen die Auswirkungen auf die Leistung abwägen – die Verwendung `CallByName` zum Aufrufen einer Prozedur ist etwas langsamer als ein spät gebundener Aufruf. Wenn Sie eine Funktion aufrufen, die wiederholt aufgerufen wird, z. b. innerhalb einer Schleife, können `CallByName` schwerwiegende Auswirkungen auf die Leistung haben.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [Bestimmen des Objekttyps](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
