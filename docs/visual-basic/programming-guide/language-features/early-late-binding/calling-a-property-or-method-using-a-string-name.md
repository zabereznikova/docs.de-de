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
ms.openlocfilehash: eb9d214d7bb226a4e14cb42e78bffd940049838d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967528"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen (Visual Basic)
In den meisten Fällen können Sie ermitteln die Eigenschaften und Methoden eines Objekts zur Entwurfszeit und Schreiben von Code, damit sie verarbeitet. Jedoch in einigen Fällen Sie möglicherweise nicht über Eigenschaften und Methoden eines Objekts im Voraus kennen, oder die Flexibilität, Benutzer, geben Sie Eigenschaften oder Methoden zur Laufzeit ausführen kann auch sinnvoll sein.  
  
## <a name="callbyname-function"></a>CallByName-Funktion  
 Betrachten Sie z. B. eine Clientanwendung, die Ausdrücke, die vom Benutzer eingegeben haben, übergeben Sie einen Operator auf eine COM-Komponente ausgewertet wird. Angenommen Sie, Sie werden ständig neue Funktionen hinzufügen, auf die Komponente, die neue Operatoren erfordern. Wenn Sie den standard für den Objektzugriff verwenden, müssen Sie neu kompilieren und die Client-Anwendung neu verteilen, bevor sie die neuen Operatoren verwenden kann. Um dies zu vermeiden, können Sie die `CallByName` Funktion, um die neuen Operatoren als Zeichenfolge übergeben, ohne die Anwendung zu ändern.  
  
 Die `CallByName` -Funktion können Sie eine Zeichenfolge zu verwenden, um eine Eigenschaft oder Methode zur Laufzeit anzugeben. Die Signatur für die `CallByName` Funktion sieht wie folgt aus:  
  
 *Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())  
  
 Das erste Argument, *Objekt*, erhält den Namen des Objekts, auf die reagiert werden soll. Die *Prozedurname* Argument akzeptiert eine Zeichenfolge, die den Namen der aufzurufenden Methode oder Eigenschaft Prozedur enthält. Die *CallType* Argument akzeptiert eine Konstante, die den Typ des aufzurufenden Prozedur darstellt: eine Methode (`Microsoft.VisualBasic.CallType.Method`), eine Eigenschaft zu lesen (`Microsoft.VisualBasic.CallType.Get`), oder eine Eigenschaft festzulegen (`Microsoft.VisualBasic.CallType.Set`). Die *Argumente* -Argument, das optional ist, nimmt ein Array vom Typ `Object` , die keine Argumente an die Prozedur enthält.  
  
 Sie können `CallByName` mit Klassen in der aktuellen Lösung, sondern wird meistens den Zugriff auf COM-Objekte verwendet, oder Objekte aus [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys.  
  
 Angenommen, Sie über einen Verweis auf eine Assembly hinzufügen, die eine Klasse namens enthält `MathClass`, die über eine neue Funktion, die mit dem Namen verfügt `SquareRoot`, wie im folgenden Code gezeigt:  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 Die Anwendung konnte Textfeld-Steuerelemente zum Steuerelement, welche Methode aufgerufen wird, und seine Argumente verwenden. Z. B. wenn `TextBox1` enthält den Ausdruck ausgewertet werden soll, und `TextBox2` wird verwendet, um den Namen der Funktion eingeben, können Sie den folgenden Code zum Aufrufen verwenden die `SquareRoot` Funktion für den Ausdruck in `TextBox1`:  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 Bei Eingabe von "64" in `TextBox1`, in "SquareRoot" `TextBox2`, und rufen Sie dann die `CallMath` Prozedur, die Quadratwurzel der Zahl in `TextBox1` ausgewertet wird. Ruft der Code im Beispiel die `SquareRoot` Funktion (der akzeptiert einer Zeichenfolge, enthält den Ausdruck als ein erforderliches Argument ausgewertet wird) und gibt "8" in `TextBox1` (die Quadratwurzel von 64). Natürlich auch, wenn der Benutzer eine ungültige Zeichenfolge in eingibt `TextBox2`, wenn die Zeichenfolge den Namen einer Eigenschaft anstelle einer Methode enthält oder die Methode ein zusätzliches Argument für die erforderlichen aufweist, ein Laufzeitfehler auftritt. Müssen Sie stabile Fehlerbehandlung Code hinzufügen, bei der Verwendung `CallByName` diese oder andere Fehlermeldungen vorhersehen.  
  
> [!NOTE]
>  Während der `CallByName` Funktion kann in einigen Fällen nützlich sein, müssen Sie die Zweckmäßigkeit mit Auswirkungen auf die Leistung abwägen – mit `CallByName` ist etwas langsamer als ein spät gebundenen Aufruf zum Aufrufen einer Prozedur. Wenn Sie eine Funktion aufrufen, die wiederholt, z. B. aufgerufen wird, wie in einer Schleife, `CallByName` kann eine schwerwiegende Auswirkungen auf die Leistung haben.  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [Bestimmen des Objekttyps](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
