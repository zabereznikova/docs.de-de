---
title: Erweiterungsmethoden (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: 9e005d0dc7da154fbaffbf7e02c55445a1213195
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296237"
---
# <a name="extension-methods-visual-basic"></a>Erweiterungsmethoden (Visual Basic)
Erweiterungsmethoden ermöglichen Entwicklern das Hinzufügen von benutzerdefinierten Funktionen, Datentypen, die bereits definiert sind, ohne einen neuen abgeleiteten Typ zu erstellen. Erweiterungsmethoden ermöglichen das Schreiben eine Methode, die aufgerufen werden können, als handele es sich um eine Instanzenmethode des vorhandenen Typs.  
  
## <a name="remarks"></a>Hinweise  
 Eine Erweiterungsmethode kann ausschließlich eine `Sub`-Prozedur oder eine `Function`-Prozedur sein. Erweiterungseigenschaften, -felder oder -ereignisse können nicht definiert werden. Alle Erweiterungsmethoden müssen mit dem Erweiterungsattribut `<Extension()>` aus dem <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>-Namespace markiert werden.  
  
 Der erste Parameter in der Definition einer Erweiterungsmethode gibt den Datentyp an, der von der Methode erweitert wird. Beim Ausführen der Methode wird der erste Parameter an die Instanz des Datentyps gebunden, der die Methode aufruft.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Beispiel wird eine `Print`-Erweiterung für den <xref:System.String>-Datentyp definiert. Die Methode verwendet `Console.WriteLine`, um eine Zeichenfolge anzuzeigen. Durch den `Print`-Parameter der `aString`-Methode wird festgelegt, dass die <xref:System.String>-Klasse von der Methode erweitert wird.  
  
 [!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]  
  
 Beachten Sie, dass die Definition der Erweiterungsmethode mit dem Erweiterungsattribut `<Extension()>` markiert ist. Die Markierung des Moduls, in dem die Methode definiert ist, ist optional, aber jede Erweiterungsmethode muss markiert werden. Zum Zugriff auf das Erweiterungsattribut muss <xref:System.Runtime.CompilerServices> importiert werden.  
  
 Erweiterungsmethoden können nur innerhalb von Modulen deklariert werden. Bei dem Modul, in dem eine Erweiterungsmethode definiert wird, handelt es sich normalerweise um ein anderes Modul als das, in dem sie aufgerufen wird. Stattdessen wird das Modul, in dem die Erweiterungsmethode enthalten ist, ggf. importiert, um es in den Gültigkeitsbereich einzubinden. Nachdem sich das Modul, in dem `Print` enthalten ist, im Gültigkeitsbereich befindet, kann die Methode wie jede andere gewöhnliche Instanzenmethode, die keine Argumente verwendet (z. B. `ToUpper`) aufgerufen werden:  
  
 [!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]  
  
 Das nächste Beispiel, `PrintAndPunctuate`, ist auch eine Erweiterung für <xref:System.String> und wird dieses Mal mit zwei Parametern definiert. Der erste Parameter, `aString`, legt fest, dass die Erweiterungsmethode <xref:System.String> erweitert. Mit dem zweiten Parameter, `punc`, wird eine aus Satzzeichen bestehende Zeichenfolge bereitgestellt, die beim Aufruf der Methode als Argument übergeben wird. Durch die Methode wird die Zeichenfolge gefolgt von den Satzzeichen angezeigt.  
  
 [!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]  
  
 Die Methode wird aufgerufen, indem ein Zeichenfolgenargument für `punc` gesendet wird: `example.PrintAndPunctuate(".")`  
  
 Im folgenden Beispiel werden `Print` und `PrintAndPunctuate` definiert und aufgerufen. <xref:System.Runtime.CompilerServices> wird in das Definitionsmodul importiert, um den Zugriff auf das Erweiterungsattribut zu ermöglichen.  
  
### <a name="code"></a>Code  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
  
    <Extension()>   
    Public Sub Print(ByVal aString As String)  
        Console.WriteLine(aString)  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 Als Nächstes werden die Erweiterungsmethoden in den Gültigkeitsbereich eingebunden und aufgerufen.  
  
```vb  
Imports ConsoleApplication2.StringExtensions  
Module Module1  
  
    Sub Main()  
  
        Dim example As String = "Example string"  
        example.Print()  
  
        example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>Kommentare  
 Die einzige Voraussetzung für das Ausführen dieser oder ähnlicher Erweiterungsmethoden besteht darin, dass sie sich innerhalb des Gültigkeitsbereichs befinden müssen. Wenn sich das Modul mit einer Erweiterungsmethode im Gültigkeitsbereich befindet, ist es für IntelliSense erkennbar und kann wie jede andere gewöhnliche Instanzenmethode aufgerufen werden.  
  
 Beachten Sie, dass beim Aufrufen der Methoden kein Argument für den ersten Parameter gesendet wird. Der `aString`-Parameter in den vorherigen Methodendefinitionen ist an `example` gebunden, also die Instanz von `String`, durch die sie aufgerufen werden. Der Compiler verwendet `example` als das an den ersten Parameter gesendete Argument.  
  
 Wenn eine Erweiterungsmethode für ein Objekt aufgerufen wird, das auf `Nothing` festgelegt ist, wird die Erweiterungsmethode ausgeführt. Dies trifft nicht auf normale Instanzmethoden zu. Sie können in der Erweiterungsmethode explizit auf `Nothing` überprüfen.  
  
## <a name="types-that-can-be-extended"></a>Erweiterungsfähige Typen  
 Erweiterungsmethoden können für die meisten Typen definiert werden, die in Visual Basic-Parameterlisten wie den folgenden dargestellt werden können:  
  
-   Klassen (Referenztypen)  
  
-   Strukturen (Werttypen)  
  
-   Schnittstellen  
  
-   Delegaten  
  
-   ByRef- und ByVal-Argumente  
  
-   Parameter für generische Methoden  
  
-   Arrays  
  
 Da der erste Parameter den Datentyp angibt, der durch die Erweiterungsmethode erweitert wird, ist er erforderlich und kann nicht ausgelassen werden. Aus diesem Grund kann ein `Optional`-Parameter oder ein `ParamArray`-Parameter nicht der erste Parameter in der Parameterliste sein.  
  
 Erweiterungsmethoden werden bei der späten Bindung nicht berücksichtigt. Im folgenden Beispiel löst die `anObject.PrintMe()`-Anweisung eine <xref:System.MissingMemberException>-Ausnahme aus. Dieselbe Ausnahme wird angezeigt, wenn die zweite `PrintMe`-Erweiterungsmethodendefinition gelöscht würde.  
  
 [!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]  
  
## <a name="best-practices"></a>Bewährte Methoden  
 Erweiterungsmethoden bieten eine einfache und leistungsstarke Möglichkeit zur Erweiterung eines vorhandenen Typs. Um sie erfolgreich zu verwenden, sind jedoch einige Punkte zu beachten. Obwohl sich diese Überlegungen hauptsächlich auf Autoren von Klassenbibliotheken beziehen, können sie gleichzeitig Anwendungen betreffen, die Erweiterungsmethoden verwenden.  
  
 Erweiterungsmethoden, die Sie Typen hinzufügen, die sich nicht in Ihrem Besitz befinden, sind im Allgemeinen angreifbarer als Erweiterungsmethoden, die Sie Typen hinzufügen, die von Ihnen gesteuert werden. In Klassen, die sich nicht in Ihrem Besitz befinden, können einige Ereignisse auftreten, die Ihre Erweiterungsmethoden negativ beeinflussen könnten.  
  
-   Falls ein Instanzenmember vorhanden ist, auf den zugegriffen werden kann und der über eine mit den Argumenten in der aufrufenden Anweisung kompatible Signatur verfügt, ohne dass einschränkende Konvertierungen vom Argument zum Parameter festgelegt sind, wird die Instanzenmethode vor allen Erweiterungsmethoden verwendet. Daher ist es möglich, dass auf einen vorhandenen Erweiterungsmember, den Sie verwenden möchten, nicht mehr zugegriffen werden kann, wenn einer Klasse zu einem bestimmten Zeitpunkt eine geeignete Instanzenmethode hinzugefügt wird.  
  
-   Der Autor einer Erweiterungsmethode kann nicht verhindern, dass andere Programmierer Erweiterungsmethoden schreiben, die Vorrang vor der ursprünglichen Erweiterung haben und damit Konflikte verursachen.  
  
-   Sie können die Stabilität verbessern, indem Sie Erweiterungsmethoden in einen eigenen Namespace einfügen. Consumer Ihrer Bibliothek können einen Namespace dann ein- oder ausschließen bzw. vom Rest der Bibliothek getrennt unter den Namespaces auswählen.  
  
-   Das Erweitern von Schnittstellen bietet u. U. mehr Sicherheit als das Erweitern von Klassen, insbesondere, wenn Sie nicht der Besitzer der Schnittstelle oder Klasse sind. Eine Änderung einer Schnittstelle wirkt sich auf jede Klasse aus, die von ihr implementiert wird. Deshalb ist es eher unwahrscheinlich, dass der Autor Methoden in einer Schnittstelle hinzufügt oder ändert. Wenn eine Klasse jedoch zwei Schnittstellen implementiert, die über Erweiterungsmethoden mit gleicher Signatur verfügen, wird keine der Erweiterungsmethoden angezeigt.  
  
-   Erweitern Sie einen möglichst spezifischen Typ. Wenn Sie in einer Typhierarchie einen Typ auswählen, von dem viele andere Typen abgeleitet sind, können auf viele Weisen Instanzenmethoden oder andere Erweiterungsmethoden eingeführt werden, die Konflikte mit Ihren Instanzen- oder Erweiterungsmethoden verursachen könnten.  
  
## <a name="extension-methods-instance-methods-and-properties"></a>Erweiterungsmethoden, Instanzmethoden und Eigenschaften  
 Wenn eine Instanzmethode im Gültigkeitsbereich über eine Signatur verfügt, die mit den Argumenten einer Aufrufanweisung kompatibel ist, wird die Instanzmethode vor den Erweiterungsmethoden bevorzugt ausgewählt. Die Instanzmethode hat auch dann Vorrang, wenn die Erweiterungsmethode eine bessere Übereinstimmung aufweist. Im folgenden Beispiel enthält die `ExampleClass` eine Instanzmethode mit der Bezeichnung `ExampleMethod`, die über einen Parameter des Typs `Integer` verfügt. Die Erweiterungsmethode `ExampleMethod` erweitert die `ExampleClass` und verfügt über einen Parameter des Typs `Long`.  
  
 [!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]  
  
 Mit dem ersten Aufruf an `ExampleMethod` im folgenden Code wird die Erweiterungsmethode aufgerufen, da `arg1` den Wert `Long` hat und nur mit dem `Long`-Parameter in der Erweiterungsmethode kompatibel ist. Der zweite Aufruf von `ExampleMethod` verfügt über ein `Integer`-Argument, `arg2`, und es ruft die Instanzmethode auf.  
  
 [!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]  
  
 Kehren Sie nun die Datentypen der Parameter in den zwei Methoden um:  
  
 [!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]  
  
 Dieses Mal ruft der Code in `Main` beide Male die Instanzmethode auf. Das liegt daran, dass sowohl `arg1` und `arg2` über eine Erweiterungskonvertierung zu `Long` verfügen, und die Instanzmethode in beiden Fällen Vorrang vor der Erweiterungsmethode hat.  
  
 [!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]  
  
 Dies bedeutet, dass eine Erweiterungsmethode keine vorhandene Instanzmethode ersetzen kann. Wenn eine Erweiterungsmethode jedoch über denselben Namen wie eine Instanzmethode verfügt, die Signaturen aber keine Konflikte verursachen, kann auf beide Methoden zugegriffen werden. Wenn die `ExampleClass` beispielsweise eine Methode mit dem Namen `ExampleMethod` enthält, die keine Argumente verwendet, sind Erweiterungsmethoden mit demselben Namen aber unterschiedlichen Signaturen zulässig, wie in folgendem Code dargestellt.  
  
 [!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]  
  
 Dieser Code generiert folgende Ausgabe:  
  
 `Extension method`  
  
 `Instance method`  
  
 Bezüglich Eigenschaften ist der Sachverhalt unkomplizierter: Wenn eine Erweiterungsmethode den gleichen Namen wie eine Eigenschaft der Klasse hat, die sie erweitert, wird die Erweiterungsmethode nicht angezeigt, und es kann nicht darauf zugegriffen werden.  
  
## <a name="extension-method-precedence"></a>Rangfolge von Erweiterungsmethoden  
 Wenn sich zwei Erweiterungsmethoden mit identischen Signaturen im Gültigkeitsbereich befinden und zugreifbar sind, wird die Methode mit der höheren Rangfolge aufgerufen. Die Rangfolge einer Erweiterungsmethode basiert auf dem Mechanismus, der verwendet wird, um die Methode in den Gültigkeitsbereich einzubinden. Die folgende Liste gibt die hierarchische Rangfolge von oben nach unten an:  
  
1. Im aktuellen Modul definierte Erweiterungsmethoden.  
  
2. Erweiterungsmethoden, die innerhalb von Datentypen im aktuellen Namespace oder in übergeordneten Namespaces definiert sind, wobei untergeordnete Namespaces eine höhere Rangfolge als übergeordnete Namespaces haben.  
  
3. In Typimporten in der aktuellen Datei definierte Erweiterungsmethoden.  
  
4. In Namespaceimporten in der aktuellen Datei definierte Erweiterungsmethoden.  
  
5. In Typimporten auf Projektebene definierte Erweiterungsmethoden.  
  
6. In Namespaceimporten auf Projektebene definierte Erweiterungsmethoden.  
  
 Wenn sich die Mehrdeutigkeit durch die Anwendung einer Rangfolge nicht auflösen lässt, können Sie den vollqualifizierten Namen zum Festlegen der aufgerufenen Methode verwenden. Wenn die `Print`-Methode aus dem vorherigen Beispiel in einem Modul mit dem Namen `StringExtensions` definiert wird, lautet der vollqualifizierte Name `StringExtensions.Print(example)` und nicht `example.Print()`.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Erweiterungsmethoden](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [Module-Anweisung](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Optionale Parameter](./optional-parameters.md)
- [Parameterarrays](./parameter-arrays.md)
- [Übersicht über Attribute](../../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
