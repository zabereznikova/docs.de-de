---
title: Problembehandlung bei Prozeduren (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures, troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures, about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a5445d6da982e4eea5b1047505e4bee3380ed472
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-procedures-visual-basic"></a>Problembehandlung bei Prozeduren (Visual Basic)
Diese Seite listet einige der häufigsten Probleme, die beim Arbeiten mit Prozeduren auftreten können.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>Zurückgeben eines Arraytyps aus einer Function-Prozedur  
 Wenn ein `Function` -Prozedur einen Arraydatentyp zurückgibt, können Sie verwenden die `Function` Namen zum Speichern von Werten in den Elementen des Arrays. Wenn Sie dies dennoch versuchen, legt der Compiler als Aufruf der `Function`. Im folgende Beispiel werden Compilerfehler generiert.  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 Die Anweisung `allOnes(i) = 1` generiert einen Compilerfehler, da sie aufrufen, `allOnes` mit einem Argument des falschen Datentyps (Singleton `Integer` anstelle von einer `Integer` Array). Die Anweisung `Return allOnes()` generiert einen Compilerfehler, da sie aufrufen, `allOnes` ohne Argument.  
  
 **Richtige Ansatz:** um die Elemente eines Arrays zu ändern, die zurückgegeben werden soll, definieren Sie ein internes Array als lokale Variable. Im folgenden Beispiel wird ohne Fehler kompiliert wird.  
  
 [!code-vb[VbVbcnProcedures&#66;](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]  
  
## <a name="argument-not-being-modified-by-procedure-call"></a>Argument nicht geändert wird vom Prozeduraufruf  
 Wenn Sie beabsichtigen, eine Prozedur ein Programmierelement zugrunde liegende Argument im aufrufenden Code ändern können, müssen Sie es als Verweis übergeben. Aber eine Prozedur kann auf die Elemente eines Typarguments Verweis zugreifen, selbst wenn er als Wert übergeben.  
  
-   **Zugrunde liegende Variable**. Um die Prozedur den Wert des zugrunde liegenden Variablenelement ersetzen soll, muss die Prozedur deklarieren Sie den Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). Auch der aufrufende Code muss nicht setzen Sie das Argument in Klammern ein, da dies überschreiben würde die `ByRef` Mechanismus übergeben.  
  
-   **Verweisen Sie Elemente vom Typ**. Wenn Sie einen Parameter deklarieren [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), die Prozedur nicht das zugrunde liegende Variablenelement nicht ändern. Jedoch, wenn das Argument ein Verweistyp ist, kann die Prozedur ändern die Member des Objekts, die es verweist, obwohl er nicht den Wert der Variablen ersetzen kann. Ist das Argument eine Arrayvariable, z. B. die Prozedur ein neues Array kann nicht zugewiesen werden, damit, jedoch kann es sich mindestens eines seiner Elemente ändern. Die geänderten Elemente werden in der zugrunde liegenden Arrayvariablen im Aufrufcode wiedergegeben.  
  
 Das folgende Beispiel definiert zwei Prozeduren, die eine Arrayvariable als Wert übernehmen und ausgeführt werden, auf deren Elemente. Prozedur `increase` einfach zu jedem Element hinzufügt. Prozedur `replace` weist ein neues Array an den Parameter `a()` und fügt dann jedem Element&1; hinzu. Die erneute Zuweisung ist jedoch nicht der zugrunde liegenden Arrayvariablen im Aufrufcode beeinträchtigen, da `a()` deklariert `ByVal`.  
  
 [!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures&#38;](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]  
  
 Im folgenden Beispiel werden Aufrufe von `increase` und `replace`.  
  
 [!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]  
  
 Die erste `MsgBox` -Aufruf zeigt "After increase(n):: 11, 21, 31, 41". Da `n` ist ein Verweistyp, `increase` kann seine Member ändern, obwohl es übergeben wird `ByVal`.  
  
 Die zweite `MsgBox` -Aufruf zeigt "After replace(n):: 11, 21, 31, 41". Da `n` übergeben `ByVal`, `replace` die Variable kann nicht geändert werden `n` durch ein neues Array zuweisen. Wenn `replace` neue Arrayinstanz erstellt `k` und weist sie auf die lokale Variable `a`, verliert den Verweis auf `n` vom aufrufenden Code übergeben. Wenn es erhöht die Mitglieder `a`, nur auf das lokale Array `k` betroffen ist.  
  
 **Richtige Ansatz:** um ein zugrunde liegendes Variablenelement selbst ändern können, als Verweis übergeben. Das folgende Beispiel zeigt die Änderung in der Deklaration von `replace` , die ein Array mit einem anderen in der aufrufende Code ersetzen können.  
  
 [!code-vb[VbVbcnProcedures&#64;](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]  
  
## <a name="unable-to-define-an-overload"></a>Definieren eine Überladung kann nicht  
 Wenn Sie eine überladene Version einer Prozedur definieren möchten, müssen Sie den gleichen Namen, jedoch eine andere Signatur verwenden. Wenn der Compiler die Deklaration nicht von einer Überladung mit der gleichen Signatur unterscheiden kann, wird einen Fehler generiert.  
  
 Die *Signatur* einer Prozedur wird durch den Prozedurnamen und die Parameterliste bestimmt. Jede Überladung muss den gleichen Namen wie die anderen Überladungen, allerdings muss sich von allen in mindestens einer der anderen Komponenten der Signatur unterscheiden. Weitere Informationen finden Sie unter [Prozedurüberladung](./procedure-overloading.md).  
  
 Die folgenden Elemente sind, obwohl sie die Parameterliste betreffen nicht Komponenten der Signatur einer Prozedur:  
  
-   Schlüsselwörter für Prozedurmodifizierer, z. B. `Public`, `Shared`, und`Static`  
  
-   Parameternamen  
  
-   Schlüsselwörter für Parametermodifizierer, z. B. `ByRef` und`Optional`  
  
-   Der Datentyp des Rückgabewerts (außer einem Konvertierungsoperator)  
  
 Eine Prozedur kann nicht durch die Veränderung nur eine oder mehrere der vorhergehenden Elemente überladen werden.  
  
 **Richtige Ansatz:** um eine Überladung Prozedur definieren können, müssen Sie die Signatur variieren. Da Sie den gleichen Namen verwenden müssen, müssen Sie die Anzahl, Reihenfolge oder Datentypen der Parameter variieren. In einer generischen Prozedur können Sie die Anzahl von Typparametern variieren. In einem Konvertierungsoperator ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)), können Sie den Rückgabetyp variieren.  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Überladen Sie, Auflösung und optionale und ParamArray-Argumente  
 Wenn Sie eine Prozedur mit einem oder mehreren überladen werden [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) Parameter oder ein [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) -Parameter müssen Sie vermeiden Duplizieren eines der *implizite Überladungen*. Weitere Informationen finden Sie unter [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a>Aufrufen einer falschen Version einer überladenen Prozedur  
 Wenn eine Prozedur mehrere überlastete Versionen aufweist, sollten Sie mit ihre Parameterlisten vertraut sein und verstehen, wie [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] löst Aufrufe zwischen Überladungen. Andernfalls können Sie eine Überladung als dem beabsichtigten aufrufen.  
  
 Wenn Sie die Überladung, die für Sie aufrufen möchten ermittelt haben, achten Sie darauf, dass Sie die folgenden Regeln beachten:  
  
-   Geben Sie die richtige Anzahl von Argumenten und in der richtigen Reihenfolge.  
  
-   Im Idealfall sollten die Argumente den genau gleichen Datentypen wie die entsprechenden Parameter aufweisen. In jedem Fall muss der Datentyp der einzelnen Argumente, des entsprechenden Parameters erweitert werden. Dies gilt auch für die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) festgelegt `Off`. Wenn eine Überladung erfordert eine einschränkende Konvertierung aus der Argumentliste, die überladen ist nicht berechtigt, die aufgerufen werden.  
  
-   Wenn Sie Argumente, die Erweiterung benötigen angeben, sollten Sie deren Datentypen sich so nah wie möglich an die entsprechenden Parameterdatentypen. Wenn zwei oder mehr Überladungen Argumentdatentypen akzeptieren, löst der Compiler den Aufruf an die Überladung, die für den geringsten erweiternde aufruft.  
  
 Sie können die Wahrscheinlichkeit von Datentypenkonflikten reduzieren, indem Sie mit der [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) Konvertierungsschlüsselwort bei der Vorbereitung der Argumente.  
  
### <a name="overload-resolution-failure"></a>Überladen aufgelöst werden konnte  
 Beim Aufrufen einer überladenen Prozedur versucht der Compiler, alle außer einer Überladung zu beseitigen. Wenn dies gelingt, den Aufruf in diese Überladung aufgelöst. Wenn alle Überladungen beseitigt oder geeignete Überladung, die einem einzelnen Kandidaten reduziert werden kann, wird einen Fehler generiert.  
  
 Das folgende Beispiel veranschaulicht die überladungsauflösungsprozesses.  
  
 [!code-vb[VbVbcnProcedures&#62;](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]  
  
 [!code-vb[VbVbcnProcedures&#63;](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]  
  
 Im ersten Aufruf beseitigt der Compiler die erste Überladung, da der Typ des ersten Arguments (`Short`) wird in den Typ des entsprechenden Parameters (`Byte`). Klicken Sie dann die dritte Überladung beseitigt, da jeder Argumenttyp der zweiten Überladung (`Short` und `Single`) in den entsprechenden Typ der dritten Überladung erweitert (`Integer` und `Single`). Die zweite Überladung eine geringere Erweiterung erfordert, damit der Compiler für den Aufruf verwendet.  
  
 Im zweiten Aufruf kann nicht der Compiler keine Überladung durch Einschränken beseitigen. Die dritte Überladung beseitigt aus demselben Grund wie im ersten Aufruf, da die zweite Überladung mit geringerer Erweiterung der Argumenttypen aufgerufen werden kann. Jedoch kann der Compiler zwischen der ersten und zweiten Überladung nicht auflösen. Jede verfügt über einen definierten Parametertyp, der in den entsprechenden Typ in einer anderen erweitert wird (`Byte` auf `Short`, aber `Single` , `Double`). Aus diesem Grund generiert der Compiler einen Überladungsauflösungsfehler.  
  
 **Richtige Vorgehensweise:** verwenden, um eine überladene Prozedur ohne Zweideutigkeit aufrufen zu können, [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) die Argumentdatentypen mit den Parametertypen übereinstimmen. Das folgende Beispiel zeigt einen Aufruf von `z` , die Auflösung in die zweite Überladung erzwingt.  
  
 [!code-vb[VbVbcnProcedures&#65;](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Überladen Sie, Auflösung und optionale und ParamArray-Argumente  
 Wenn zwei Überladungen einer Prozedur identische Signaturen verfügen, mit der Ausnahme, dass der letzte Parameter deklariert ist [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in einem und [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in einer anderen, löst der Compiler einen Aufruf für diese Prozedur entsprechend am ehesten entspricht. Weitere Informationen finden Sie unter [Overload Resolution](./overload-resolution.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Sub-Prozeduren](./sub-procedures.md)   
 [Function-Prozeduren](./function-procedures.md)   
 [Property-Prozeduren](./property-procedures.md)   
 [Operatorprozeduren](./operator-procedures.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Prozedurüberladung](./procedure-overloading.md)   
 [Überlegungen zur prozedurüberladung](./considerations-in-overloading-procedures.md)   
 [Überladungsauflösung](./overload-resolution.md)
