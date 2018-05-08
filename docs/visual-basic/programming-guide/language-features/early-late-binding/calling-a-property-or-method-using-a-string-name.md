---
title: Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen (Visual Basic)
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
ms.openlocfilehash: 76be426049489bb58e50878822c03fa5cd5cca8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen (Visual Basic)
In den meisten Fällen können Sie zur Entwurfszeit die Eigenschaften und Methoden eines Objekts zu ermitteln und Code schreiben, um deren Behandlung. Jedoch in einigen Fällen Sie möglicherweise nicht über die Eigenschaften und Methoden eines Objekts im Voraus wissen, oder sollten Sie nur die Flexibilität, Endbenutzer, geben Sie Eigenschaften oder Methoden zur Laufzeit ausführen.  
  
## <a name="callbyname-function"></a>CallByName-Funktion  
 Betrachten Sie z. B. eine Clientanwendung, die vom Benutzer eingegeben wird, übergeben Sie einen Operator auf eine COM-Komponente Ausdrücke auswertet. Angenommen Sie, Sie sind sich ständig neue Funktionen hinzufügen, an die Komponente, die neue Operatoren erfordern. Bei Verwendung von standard Objektzugriff müssen Sie erneut kompilieren und die Clientanwendung neu verteilen, bevor die neue Operatoren verwendet werden können. Um dies zu vermeiden, können Sie die `CallByName` Funktion, um die neuen Operatoren als Zeichenfolgen übergeben werden, ohne die Anwendung zu ändern.  
  
 Die `CallByName` -Funktion können Sie eine Zeichenfolge zu verwenden, um einer Eigenschaft oder Methode zur Laufzeit anzugeben. Die Signatur für die `CallByName` Funktion sieht wie folgt aus:  
  
 *Ergebnis* = `CallByName`(*Objekt*, *Prozedurname*, *Aufruftyp*, *Argumente*())  
  
 Das erste Argument *Objekt*, erhält den Namen des Objekts, das nach dem vorgegangen werden soll. Die *Prozedurname* Argument akzeptiert eine Zeichenfolge, die den Namen der aufzurufenden Methode oder Eigenschaft Prozedur enthält. Die *Aufruftyp* Argument akzeptiert eine Konstante, die den Typ der aufzurufenden Prozedur darstellt: eine Methode (`Microsoft.VisualBasic.CallType.Method`), eine Eigenschaft zu lesen (`Microsoft.VisualBasic.CallType.Get`), oder eine Eigenschaft festlegen (`Microsoft.VisualBasic.CallType.Set`). Die *Argumente* -Argument, das optional ist, wird ein Array vom Typ `Object` , die keine Argumente an die Prozedur enthält.  
  
 Sie können `CallByName` mit Klassen in der aktuellen Projektmappe angezeigt, aber es ist am häufigsten verwendet, um den Zugriff auf COM-Objekte oder-Objekte aus [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys.  
  
 Angenommen, Sie einen Verweis auf eine Assembly hinzufügen, die eine Klasse namens enthält `MathClass`, dem verfügt über eine neue Funktion, die mit dem Namen `SquareRoot`, wie im folgenden Code gezeigt:  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 Die Anwendung konnte Textfeld-Steuerelemente zum Steuerelement, welche Methode aufgerufen wird und Argumente verwenden. Z. B. wenn `TextBox1` enthält den Ausdruck ausgewertet werden soll, und `TextBox2` wird verwendet, um den Namen der Funktion eingeben, können Sie den folgenden Code zum Aufrufen der `SquareRoot` Funktion zum Ausdruck im `TextBox1`:  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 Bei der Eingabe von "64" in `TextBox1`, in "SquareRoot" `TextBox2`, und rufen Sie anschließend die `CallMath` Prozedur, die Quadratwurzel der Zahl in `TextBox1` ausgewertet wird. Der Code im Beispiel ruft die `SquareRoot` -Funktion (der akzeptiert einer Zeichenfolge, enthält den Ausdruck, der als ein erforderliches Argument ausgewertet werden) und gibt "8" im `TextBox1` (die Quadratwurzel von 64). Natürlich, wenn der Benutzer eingibt, eine ungültige Zeichenfolge in `TextBox2`, wenn die Zeichenfolge den Namen einer Eigenschaft anstelle einer Methode enthält oder die Methode ein weiteres erforderliches Argument aufweist, tritt ein Laufzeitfehler auf. Stabile Fehlerbehandlungscode hinzugefügt werden, wenn Sie verwenden, stehen Ihnen `CallByName` auf diesen oder andere Fehler zu erwarten.  
  
> [!NOTE]
>  Während der `CallByName` Funktion kann in einigen Fällen nützlich sein, Sie müssen abwägen, des Nutzens Leistungseinbußen – mit `CallByName` zum Aufrufen einer Prozedur ist etwas langsamer als eine spät gebundenen Aufruf. Wenn Sie eine Funktion aufrufen, die wiederholt, z. B. in einer Schleife aufgerufen wird `CallByName` kann eine schwerwiegende Auswirkungen auf die Leistung haben.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>  
 [Bestimmen des Objekttyps](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
