---
title: Problembehandlung bei Prozeduren (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e54c965dc15131734be2c5bcfe04ad70292bf23
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="troubleshooting-procedures-visual-basic"></a>Problembehandlung bei Prozeduren (Visual Basic)
Auf dieser Seite sind einige allgemeine Probleme, die beim Arbeiten mit Prozeduren auftreten können.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>Rückgabe eines Arraytyps aus einer Funktionsprozedur  
 Wenn eine `Function` Prozedur gibt den Datentyp eines Arrays, können Sie verwenden die `Function` Namen zum Speichern der Werte in der Elemente des Arrays. Wenn Sie dies dennoch versuchen, interpretiert der Compiler ihn als einen Aufruf der `Function`. Im folgende Beispiel werden Compilerfehler generiert.  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 Die Anweisung `allOnes(i) = 1` generiert einen Compilerfehler, weil sie anscheinend Aufrufen `allOnes` mit dem Argument den falschen Datentyp (ein Singleton `Integer` anstelle von einer `Integer` Array). Die Anweisung `Return allOnes()` generiert einen Compilerfehler, weil sie anscheinend Aufrufen `allOnes` ohne Argument.  
  
 **Richtige Ansatz:** um in der Lage, die Elemente eines Arrays zu ändern, die zurückgegeben werden soll, definieren Sie ein internes Array als lokale Variable. Im folgende Beispiel wird ohne Fehler kompiliert.  
  
 [!code-vb[VbVbcnProcedures#66](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]  
  
## <a name="argument-not-being-modified-by-procedure-call"></a>Argument nicht geändert wird durch Prozeduraufruf  
 Wenn Sie beabsichtigen, eine Prozedur so ändern Sie ein Programmierelement ein Argument im aufrufenden Code zugrunde liegt, zu ermöglichen, müssen Sie als Verweis übergeben werden. Aber eine Prozedur kann die Elemente eines Typarguments Verweis zugreifen, selbst wenn er als Wert übergeben.  
  
-   **Zugrunde liegende Variable**. Damit wird die Prozedur den Wert des zugrunde liegenden Variable Elements selbst zu ersetzen, muss die Prozedur deklarieren Sie den Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). Darüber hinaus der aufrufende Code muss nicht setzen Sie das Argument in Klammern, da dies überschreiben würde die `ByRef` Übergabemechanismus.  
  
-   **Verweisen auf Elementen des Typs**. Wenn Sie einen Parameter deklarieren [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), die Prozedur den zugrunde liegenden Variable-Element selbst kann nicht geändert werden. Jedoch wenn das Argument ein Verweistyp ist, kann die Prozedur ändern die Member des Objekts auf den er zeigt, obwohl er nicht den Wert der Variablen ersetzen kann. Wenn das Argument eine Arrayvariable ist, z. B. die Prozedur kann nicht weisen Sie ein neues Array zu, aber können sie eine oder mehrere der Elemente ändern. Die geänderten Elemente werden in der zugrunde liegenden Arrayvariablen im aufrufenden Code widergespiegelt.  
  
 Im folgende Beispiel werden zwei Prozeduren, die eine Arrayvariable als Wert übernehmen und den Betrieb auf seine Elemente definiert. Prozedur `increase` einfach zu jedem Element hinzufügt. Prozedur `replace` weist ein neues Array an den Parameter `a()` , und klicken Sie dann auf jedes Element hinzugefügt. Die erneute Zuweisung ist jedoch nicht die zugrunde liegende Arrayvariable im aufrufenden Code beeinträchtigen, da `a()` deklariert `ByVal`.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]  
  
 Im folgenden Beispiel wird die Aufrufe an `increase` und `replace`.  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]  
  
 Die erste `MsgBox` -Aufruf zeigt "After increase(n):: 11, 21, 31, 41". Da `n` ist ein Verweistyp `increase` können Membern, ändern, obwohl sie übergeben wird `ByVal`.  
  
 Die zweite `MsgBox` -Aufruf zeigt "After replace(n):: 11, 21, 31, 41". Da `n` übergeben `ByVal`, `replace` die Variable kann nicht geändert werden `n` indem Sie ein neues Array zuweisen. Wenn `replace` die Instanz des neuen Arrays erstellt `k` und weist sie auf die lokale Variable `a`, geht den Verweis auf `n` vom aufrufenden Code übergeben. Wenn sie die Mitglieder der erhöht `a`, nur die lokale Array `k` betroffen ist.  
  
 **Richtige Ansatz:** um eine zugrunde liegende Variable-Element selbst ändern zu können, als Verweis übergeben. Das folgende Beispiel zeigt die Änderung in der Deklaration eines `replace` , die ein Array mit einem anderen im aufrufenden Code ersetzen können.  
  
 [!code-vb[VbVbcnProcedures#64](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]  
  
## <a name="unable-to-define-an-overload"></a>Definieren Sie eine Überladung kann nicht  
 Wenn Sie eine überladene Version einer Prozedur definieren möchten, müssen Sie den gleichen Namen, aber einer anderen Signatur verwenden. Wenn der Compiler die Deklaration aus einer Überladung mit der gleichen Signatur unterscheiden kann, wird einen Fehler generiert.  
  
 Die *Signatur* einer Prozedur wird durch den Namen der Prozedur und der Parameterliste bestimmt. Jede Überladung muss den gleichen Namen wie die anderen Überladungen haben, muss von allen von ihnen in mindestens einer der anderen Komponenten der Signatur unterscheiden sich jedoch. Weitere Informationen finden Sie unter [Prozedurüberladung](./procedure-overloading.md).  
  
 Die folgenden Elemente sind, obwohl sie die Parameterliste gehören keine Komponenten der Signatur einer Prozedur:  
  
-   Schlüsselwörter für Prozedurmodifizierer, z. B. `Public`, `Shared`, und `Static`  
  
-   Parameternamen  
  
-   Parametermodifiziererschlüsselwörter, wie z. B. `ByRef` und `Optional`  
  
-   Der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungsoperators)  
  
 Eine Prozedur kann nicht durch Variierung der nur eine oder mehrere der vorhergehenden Elemente überladen werden.  
  
 **Richtige Ansatz:** um eine Überladung Prozedur definieren können, müssen Sie die Signatur variieren. Da Sie den gleichen Namen verwenden müssen, müssen Sie die Anzahl, Reihenfolge oder Datentypen der Parameter variieren. In einer generischen Prozedur können Sie die Anzahl von Typparametern variieren. In einem Konvertierungsoperator ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)), Sie können den Rückgabetyp unterscheiden.  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Überladen von Auflösung mit optionalen und ParamArray-Argumente  
 Wenn Sie eine Prozedur mit einem oder mehreren überladen werden [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) Parameter oder eine [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Parameter müssen vermeiden Duplizieren eines der *implizite Überladungen*. Informationen finden Sie unter [Überlegungen in Überladen von Prozeduren](./considerations-in-overloading-procedures.md).  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a>Eine falsche Version einer überladenen Prozedur aufrufen  
 Wenn eine Prozedur mehrere überladene Versionen aufweist, sollten Sie mit ihren Parameterlisten vertraut sein und verstehen, wie Visual Basic Aufrufe zwischen Überladungen aufgelöst. Andernfalls können Sie eine Überladung als der vorgesehene aufrufen.  
  
 Wenn Sie die Überladung, die für Sie aufrufen möchten bestimmt haben, achten Sie darauf, dass Sie die folgenden Regeln beachten:  
  
-   Geben Sie die richtige Anzahl von Argumenten, und klicken Sie in der richtigen Reihenfolge.  
  
-   Im Idealfall sollten die Argumente genau dieselben Datentypen wie die entsprechenden Parameter aufweisen. In jedem Fall muss der Datentyp der einzelnen Argumente, des entsprechenden Parameters erweitert werden. Dies gilt auch bei der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) festgelegt `Off`. Wenn eine Überladung erfordert einschränkende Konvertierung aus Ihrer Typargumentliste, die überladen ist nicht berechtigt, die aufgerufen wird.  
  
-   Wenn Sie Argumente, die erweiternde erfordern angeben, stellen Sie Datentypen, die so nah wie möglich an den entsprechenden Parameterdatentypen an. Wenn zwei oder mehr Überladungen Ihre Argumentdatentypen annehmen, löst der Compiler den Aufruf an die Überladung, die für die Argumentdatentypen am wenigsten aufruft.  
  
 Reduziert die Wahrscheinlichkeit von Datentypenkonflikten können mithilfe der [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) Konvertierungsschlüsselwort bei der Vorbereitung Ihrer Argumente.  
  
### <a name="overload-resolution-failure"></a>Fehlers beim Auflösen der Überladung  
 Wenn Sie eine überladene Prozedur aufrufen, versucht der Compiler alle bis auf eine der Überladungen zu vermeiden. Wenn er erfolgreich ausgeführt wird, löst den Aufruf an diese Überladung auf. Wenn sie alle Überladungen eliminiert oder geeigneten Überladungen, die einem einzelnen Kandidaten nicht reduziert werden kann, wird einen Fehler generiert.  
  
 Das folgende Beispiel veranschaulicht die überladungsauflösungsprozesses.  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]  
  
 Beim ersten Aufruf beseitigt der Compiler die erste Überladung, da der Typ des ersten Arguments (`Short`) in den Typ des entsprechenden Parameters schränkt (`Byte`). Sie klicken Sie dann die dritte Überladung beseitigt, da jeder Argumenttyp der zweiten Überladung (`Short` und `Single`) in den entsprechenden Typ in die dritte Überladung erweitert (`Integer` und `Single`). Die zweite Überladung eine geringere Erweiterung erfordert, damit der Compiler für den Funktionsaufruf verwendet.  
  
 Im zweiten Aufruf kann nicht vom Compiler der Überladungen Einschränken vermieden. Die dritte Überladung beseitigt aus demselben Grund wie der erste Aufruf, da die zweite Überladung mit geringerer Erweiterung der Argumenttypen aufgerufen werden kann. Der Compiler kann nicht zwischen den ersten und zweiten Überladungen jedoch aufgelöst werden. Jede verfügt über einen definierten Parametertyp in den entsprechenden Typ in den anderen erweitert (`Byte` auf `Short`, aber `Single` auf `Double`). Aus diesem Grund generiert der Compiler Fehler Auflösung Überladung.  
  
 **Richtige Ansatz:** verwenden, um zu eine überladene Prozedur ohne Mehrdeutigkeit aufrufen können, [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) mit die Argumenttypen für die Daten in die Parametertypen übereinstimmen. Das folgende Beispiel zeigt einen Aufruf von `z` Auflösung in die zweite Überladung erzwingt.  
  
 [!code-vb[VbVbcnProcedures#65](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Überladen von Auflösung mit optionalen und ParamArray-Argumente  
 Wenn zwei Überladungen einer Prozedur identische Signaturen verfügen, mit dem Unterschied, dass der letzte Parameter deklariert wird [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in einem und [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in anderen, löst der Compiler einen Aufruf der Prozedur nach der nächsten Übereinstimmung. Weitere Informationen finden Sie unter [überladen Auflösung](./overload-resolution.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Function-Prozeduren](./function-procedures.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Operatorprozeduren](./operator-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Prozedurüberladung](./procedure-overloading.md)  
 [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)  
 [Überladungsauflösung](./overload-resolution.md)
