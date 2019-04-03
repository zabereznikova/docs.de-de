---
title: Problembehandlung bei Prozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: 492a7474a38a7e41b7e3b3f59dfa118c30256ea4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830135"
---
# <a name="troubleshooting-procedures-visual-basic"></a>Problembehandlung bei Prozeduren (Visual Basic)
Diese Seite listet einige der häufigsten Probleme, die auftreten können, bei der Verwendung von Prozeduren an.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>Array-Typ zurückgeben aus einer Funktionsprozedur  
 Wenn eine `Function` Prozedur gibt den Datentyp eines Arrays, können keine der `Function` Namen zum Speichern von Werten in den Elementen des Arrays. Wenn Sie versuchen möchten, interpretiert der Compiler es als Aufruf an die `Function`. Im folgende Beispiel werden Compilerfehler generiert.  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 Die Anweisung `allOnes(i) = 1` generiert einen Compilerfehler, da sie zum Aufrufen `allOnes` mit einem Argument vom falschen Typ (ein Singleton `Integer` anstelle von einer `Integer` Array). Die Anweisung `Return allOnes()` generiert einen Compilerfehler, da sie zum Aufrufen `allOnes` ohne Argument.  
  
 **Richtige Vorgehensweise:** Um die Elemente eines Arrays zu ändern, die zurückgegeben werden soll, definieren Sie ein internes Array als lokale Variable. Im folgende Beispiel wird ohne Fehler kompiliert.  
  
 [!code-vb[VbVbcnProcedures#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#66)]  
  
## <a name="argument-not-being-modified-by-procedure-call"></a>Argument nicht geändert wird durch Prozeduraufruf  
 Wenn Sie beabsichtigen, eine Prozedur ein Programmierelement, das zugrunde liegende Argument im aufrufenden Code ändern zu können, müssen Sie es als Verweis übergeben. Aber eine Prozedur kann auf die Elemente eines Typarguments Verweis zugreifen, selbst wenn er als Wert übergeben.  
  
-   **Zugrunde liegende Variable**. Um das Verfahren zum Ersetzen des Werts, der das zugrunde liegende Variablenelement zu ermöglichen, muss die Prozedur deklarieren Sie den Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). Darüber hinaus der aufrufende Code muss nicht setzen Sie das Argument in Klammern ein, da dies überschreiben würde die `ByRef` Übergabemechanismus.  
  
-   **Verweisen auf Elementen des Typs**. Wenn Sie einen Parameter deklarieren [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), die Prozedur nicht das zugrunde liegende Variablenelement ändern. Allerdings, wenn das Argument ein Verweistyp ist, kann die Prozedur ändern die Member des Objekts auf den er verweist, obwohl sie nicht den Wert der Variablen ersetzen kann. Wenn das Argument ein Array-Variable ist, z. B. die Prozedur kann nicht weisen Sie ein neues Array zu, aber kann sich eine oder mehrere der Elemente ändern. Die geänderten Elemente werden in der zugrunde liegende Array-Variable im aufrufenden Code übernommen.  
  
 Das folgende Beispiel definiert zwei Prozeduren, die eine Array-Variable als Wert und ausgeführt werden, die Elemente. Prozedur `increase` einfach auf die einzelnen Elemente hinzugefügt. Prozedur `replace` weist ein neues Array, an den Parameter `a()` , und klicken Sie dann auf die einzelnen Elemente hinzugefügt. Die neuzuweisung ist jedoch nicht die zugrunde liegende Arrayvariable im aufrufenden Code beeinträchtigen, da `a()` deklariert `ByVal`.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 Im folgenden Beispiel wird die Aufrufe von `increase` und `replace`.  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 Die erste `MsgBox` aufrufen, zeigt "nach increase(n):: 11, 21, 31, 41". Da `n` ist ein Verweistyp, `increase` können ihre Member, ändern, obwohl er übergeben wird `ByVal`.  
  
 Die zweite `MsgBox` aufrufen, zeigt "nach Replace(n):: 11, 21, 31, 41". Da `n` übergeben `ByVal`, `replace` die Variable kann nicht geändert werden `n` durch ein neues Array zugewiesen wird. Wenn `replace` neuen Arrayinstanz erstellt `k` und weist sie auf die lokale Variable `a`, er verliert den Verweis auf `n` vom aufrufenden Code übergeben. Wenn sie die Mitglieder der erhöht `a`, nur das lokale Array `k` betroffen ist.  
  
 **Richtige Vorgehensweise:** Um eine zugrunde liegende Variablenelement ändern können, als Verweis übergeben. Das folgende Beispiel zeigt die Änderung in der Deklaration der `replace` , ermöglicht es, ein Array mit einem anderen im aufrufenden Code zu ersetzen.  
  
 [!code-vb[VbVbcnProcedures#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#64)]  
  
## <a name="unable-to-define-an-overload"></a>Definieren Sie eine Überladung kann nicht  
 Wenn Sie eine überladene Version einer Prozedur definieren möchten, müssen Sie den gleichen Namen und eine andere Signatur verwenden. Wenn der Compiler die Deklaration aus einer Überladung mit derselben Signatur unterscheiden kann, wird einen Fehler generiert.  
  
 Die *Signatur* einer Prozedur richtet sich nach den Namen der Prozedur und der Parameterliste. Jede Überladung muss, die von allen Domänencontrollern in mindestens einem der anderen Komponenten der Signatur unterscheiden sich jedoch müssen den gleichen Namen wie alle anderen Überladungen. Weitere Informationen finden Sie unter [Procedure Overloading](./procedure-overloading.md).  
  
 Die folgenden Elemente, sind auch wenn sie an die Parameterliste betreffen keine Komponenten dieser Signatur einer Prozedur:  
  
-   Schlüsselwörter für Prozedurmodifizierer, z. B. `Public`, `Shared`, und `Static`  
  
-   Parameternamen  
  
-   Parametermodifiziererschlüsselwörter, z. B. `ByRef` und `Optional`  
  
-   Der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungsoperators)  
  
 Sie können nicht durch die Änderung nur eine oder mehrere der vorhergehenden Elemente eine Prozedur zu überladen.  
  
 **Richtige Vorgehensweise:** Um eine Überladung der Prozedur definieren können, müssen Sie die Signatur variieren. Da Sie den gleichen Namen verwenden müssen, müssen Sie die Anzahl, Reihenfolge oder Datentypen der Parameter variieren. In einer generischen Prozedur können Sie die Anzahl von Typparametern variieren. In ein Konvertierungsoperator ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)), können Sie den Rückgabetyp unterscheiden.  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Überladen von Auflösung mit optionalen "und" ParamArray-Argumente  
 Wenn Sie eine Prozedur mit einem oder mehreren überladen werden [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) Parameter oder ein [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Parameter, Sie müssen vermeiden Duplizieren eines der *implizite Überladungen*. Weitere Informationen finden Sie unter [Überlegungen zu überladen von Prozeduren](./considerations-in-overloading-procedures.md).  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a>Aufrufen einer falschen Version einer überladenen Prozedur  
 Wenn eine Prozedur mehrere überladene Versionen aufweist, sollten Sie mit allen zugehörigen Parameterlisten vertraut sein und verstehen, wie Anrufe zwischen Überladungen in Visual Basic aufgelöst wird. Andernfalls könnten Sie eine Überladung nicht beabsichtigten aufrufen.  
  
 Wenn Sie die Überladung, die für Sie aufrufen möchten ermittelt haben, achten Sie darauf, dass Sie die folgenden Regeln beachten:  
  
-   Geben Sie die richtige Anzahl von Argumenten, und klicken Sie in der richtigen Reihenfolge.  
  
-   Im Idealfall sollten Ihre Argumente, die genau dieselben Datentypen wie die entsprechenden Parameter aufweisen. In jedem Fall muss der Datentyp der einzelnen Argumente mit den entsprechenden Parameter erweitert werden. Dies gilt auch für die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) festgelegt `Off`. Wenn Sie eine Überladung erfordert einschränkende Konvertierung aus Ihrer Typargumentliste, die überladen ist nicht berechtigt, die aufgerufen werden.  
  
-   Wenn Sie Argumente, die erfordern erweiternden angeben, stellen Sie ihre Datentypen, die so nah wie möglich an die entsprechenden Parameter-Datentypen. Wenn zwei oder mehr Überladungen Argumentdatentypen akzeptieren, löst der Compiler den Aufruf an die Überladung, die für die geringste Menge an erweiternde aufruft.  
  
 Sie können die Wahrscheinlichkeit, dass datentypenkonflikte reduzieren, indem Sie mit der [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) Konvertierungsschlüsselwort bei der Vorbereitung Ihrer Argumente.  
  
### <a name="overload-resolution-failure"></a>Überladen aufgelöst werden konnte  
 Wenn Sie eine überladene Prozedur aufrufen, versucht der Compiler alle bis auf eine der Überladungen zu vermeiden. Wenn dies gelingt, löst es den Aufruf von dieser Überladung. Wenn es nicht, alle Überladungen erforderlich, oder wenn sie die geeigneten Überladungen, die einem einzelnen Kandidaten reduzieren kann, wird ein Fehler generiert.  
  
 Das folgende Beispiel veranschaulicht die überladungsauflösungsprozesses.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 Im ersten Aufruf wird der Compiler beseitigt die erste Überladung, da der Typ des ersten Arguments (`Short`) wird in den Typ des entsprechenden Parameters (`Byte`). Klicken Sie dann beseitigt, die dritte Überladung, da jedes Typargument in der zweiten Überladung (`Short` und `Single`) wird in den entsprechenden Typen in der dritten Überladung erweitert (`Integer` und `Single`). Die zweite Überladung eine geringere Erweiterung erfordert, damit der Compiler für den Aufruf verwendet.  
  
 Im zweiten Aufruf kann nicht vom Compiler Überladung einschränkende vermieden. Die dritte Überladung beseitigt aus demselben Grund wie der erste Aufruf, da die zweite Überladung mit geringerer Erweiterung der Argumenttypen aufgerufen werden kann. Jedoch kann der Compiler zwischen den ersten und zweiten Überladungen nicht auflösen. Jede hat einen definierten Parameter-Typ, der in den entsprechenden Typ in der anderen erweitert wird (`Byte` zu `Short`, aber `Single` zu `Double`). Aus diesem Grund generiert der Compiler einen Fehler bei der objektnamensauflösung Überladung.  
  
 **Richtige Vorgehensweise:** Verwenden Sie zum Aufrufen eine überladene Prozedur eindeutig sein, [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) mit den Datentypen der Argumente mit den Parametertypen übereinstimmen. Das folgende Beispiel zeigt einen Aufruf von `z` wird, die die Auflösung in die zweite Überladung erzwungen.  
  
 [!code-vb[VbVbcnProcedures#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#65)]  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Überladen von Auflösung mit optionalen "und" ParamArray-Argumente  
 Wenn zwei Überladungen einer Prozedur identische Signaturen verfügen, mit dem Unterschied, dass der letzte Parameter deklariert, wird [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in einem und [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in die andere ist der Compiler löst einen Aufruf dieser Prozedur nach der nächsten Übereinstimmung. Weitere Informationen finden Sie unter [Overload Resolution](./overload-resolution.md).  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Function-Prozeduren](./function-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)
- [Überladungsauflösung](./overload-resolution.md)
