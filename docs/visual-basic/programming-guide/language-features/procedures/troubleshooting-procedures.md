---
title: "Troubleshooting Procedures (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "troubleshooting Visual Basic, procedures"
  - "procedures, troubleshooting"
  - "Visual Basic code, procedures"
  - "troubleshooting procedures"
  - "procedures, about procedures"
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Troubleshooting Procedures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Auf dieser Seite werden einige allgemeine Probleme aufgeführt, die beim Arbeiten mit Prozeduren auftreten können.  
  
## Zurückgeben eines Arraytyps aus einer Function\-Prozedur  
 Wenn eine `Function`\-Prozedur einen Arraydatentyp zurückgibt, können Sie den `Function`\-Namen nicht zum Speichern von Werten in den Elementen des Arrays verwenden.  Einen entsprechenden Versuch legt der Compiler als Aufruf der `Function`\-Prozedur aus.  Im folgenden Beispiel werden Compilerfehler generiert.  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 Die `allOnes(i) = 1`\-Anweisung generiert einen Compilerfehler, da sie `allOnes` anscheinend mit einem Argument des falschen Datentyps \(einem einzelnen `Integer`\-Wert anstelle eines `Integer`\-Arrays\) aufruft.  Die `Return allOnes()`\-Anweisung generiert einen Compilerfehler, da sie `allOnes` anscheinend ohne Argument aufruft.  
  
 **Richtige Vorgehensweise:** Um die Elemente eines zurückzugebenden Arrays ändern zu können, definieren Sie ein internes Array als lokale Variable.  Im folgenden Beispiel treten keine Compilerfehler auf.  
  
 [!code-vb[VbVbcnProcedures#66](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/troubleshooting-procedures_1.vb)]  
  
## Argument, das vom Prozeduraufruf nicht geändert wird  
 Wenn Sie einer Prozedur gestatten möchten, ein Programmierelement zu ändern, das einem Argument im Aufrufcode zugrunde liegt, müssen Sie das Element als Verweis übergeben.  Eine Prozedur kann jedoch auch dann auf die Elemente eines Verweistyparguments zugreifen, wenn dieses als Wert übergeben wird.  
  
-   **Zugrunde liegende Variable**.  Wenn die Prozedur den Wert des zugrunde liegenden Variablenelements ersetzen soll, muss die Prozedur den [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)\-Parameter deklarieren.  Zudem darf das Argument im Aufrufcode nicht in runde Klammern eingeschlossen werden, da dies den `ByRef`\-Übergabemechanismus überschreiben würde.  
  
-   **Verweistypelemente**.  Wenn Sie einen Parameter mit [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) deklarieren, kann die Prozedur das zugrunde liegende Variablenelement nicht ändern.  Wenn es sich bei dem Argument jedoch um einen Verweistyp handelt, kann die Prozedur die Member des Objekts ändern, auf welches das Argument zeigt. Die Prozedur kann allerdings nicht den Wert der Variablen ersetzen.  Wenn es sich bei dem Argument beispielsweise um eine Arrayvariable handelt, kann die Prozedur ihm zwar kein neues Array zuweisen, jedoch seine einzelnen Elemente ändern.  Die geänderten Elemente werden in der zugrunde liegenden Arrayvariablen im Aufrufcode wiedergegeben.  
  
 Im folgenden Beispiel werden zwei Prozeduren definiert, die eine Arrayvariable als Wert erwarten und auf deren Elemente anwenden.  Mit der `increase`\-Prozedur wird einfach zu jedem Element 1 addiert.  Mit der `replace`\-Prozedur wird dem `a()`\-Parameter ein neues Array zugewiesen und zu jedem Element 1 addiert.  Die Neuzuweisung wirkt sich jedoch nicht auf die zugrunde liegende Arrayvariable im Aufrufcode aus, da `a()` als `ByVal` deklariert ist.  
  
 [!code-vb[VbVbcnProcedures#35](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/troubleshooting-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/troubleshooting-procedures_3.vb)]  
  
 Im folgenden Beispiel werden `increase` und `replace` aufgerufen.  
  
 [!code-vb[VbVbcnProcedures#37](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/troubleshooting-procedures_4.vb)]  
  
 Beim ersten `MsgBox`\-Aufruf wird Folgendes angezeigt: "After increase\(n\): 11, 21, 31, 41".  Da `n` ein Verweistyp ist, kann `increase` seine Member ändern, obwohl es mit `ByVal` übergeben wird.  
  
 Beim zweiten `MsgBox`\-Aufruf wird Folgendes angezeigt: "After replace\(n\): 11, 21, 31, 41".  Da `n` mit `ByVal` übergeben wird, kann `replace` die Variable `n` durch Zuweisen eines neuen Arrays nicht ändern.  Wenn `replace` die neue Arrayinstanz `k` erstellt und diese der lokalen `a`\-Variablen zuweist, geht der im Aufrufcode übergebene Verweis auf `n` verloren.  Wenn die Member von `a` inkrementiert werden, wirkt sich dies nur auf das lokale Array `k` aus.  
  
 **Richtige Vorgehensweise:** Um ein zugrunde liegendes Variablenelement selbst zu ändern, übergeben Sie es als Verweis.  Das folgende Beispiel zeigt die Änderung in der Deklaration von `replace`. Aufgrund dieser Änderung kann ein Array im Aufrufcode durch ein anderes ersetzt werden.  
  
 [!code-vb[VbVbcnProcedures#64](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/troubleshooting-procedures_5.vb)]  
  
## Definieren einer Überladung nicht möglich  
 Wenn Sie eine überladene Version einer Prozedur definieren möchten, müssen Sie den gleichen Namen, jedoch eine andere Signatur verwenden.  Wenn der Compiler die Deklaration nicht von einer Überladung mit der gleichen Signatur unterscheiden kann, wird ein Fehler generiert.  
  
 Die *Signatur* einer Prozedur wird durch den Prozedurnamen und die Parameterliste bestimmt.  Alle Überladungen müssen den gleichen Namen haben, jede Überladung muss sich jedoch in mindestens einer der anderen Komponenten der Signatur von allen übrigen Überladungen unterscheiden.  Weitere Informationen finden Sie unter [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
 Die folgenden Elemente gehören zwar zur Parameterliste, sie sind jedoch keine Komponenten der Signatur einer Prozedur:  
  
-   Schlüsselwörter für Prozedurmodifizierer, z. B. `Public`, `Shared` und `Static`  
  
-   Parameternamen  
  
-   Schlüsselwörter für Parametermodifizierer, z. B. `ByRef` und `Optional`  
  
-   Datentyp des Rückgabewerts \(außer bei einem Konvertierungsoperator\)  
  
 Sie können keine Prozedur überladen, indem Sie nur eines oder mehrere der oben genannten Elemente variabel gestalten.  
  
 **Richtige Vorgehensweise:** Um eine Prozedurüberladung definieren zu können, müssen Sie die Signaturen variabel gestalten.  Da Sie den gleichen Namen verwenden müssen, müssen Sie die Anzahl, Reihenfolge oder Datentypen der Parameter variabel gestalten.  In einer generischen Prozedur können Sie die Anzahl der Typparameter variabel gestalten.  In einem Konvertierungsoperator \([CType\-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)\) können Sie den Rückgabetyp variabel gestalten.  
  
### Überladungsauflösung mit den Argumenten Optional und ParamArray  
 Wenn Sie eine Prozedur mit einem oder mehreren [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)\-Parametern oder mit einem [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)\-Parameter überladen, müssen Sie eine Duplizierung einer der *impliziten Überladungen* vermeiden.  Nähere Informationen finden Sie unter [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
## Aufrufen einer falschen Version einer überladenen Prozedur  
 Wenn es zu einer Prozedur mehrere überladene Versionen gibt, sollten Sie alle Parameterlisten dieser Versionen kennen und wissen, wie [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] Aufrufe zwischen den Überladungen auflöst.  Andernfalls rufen Sie eventuell nicht die beabsichtigte Überladung auf.  
  
 Wenn Sie festgelegt haben, welche Überladung aufgerufen werden soll, beachten Sie die folgenden Regeln:  
  
-   Geben Sie die richtige Anzahl von Argumenten in der richtigen Reihenfolge an.  
  
-   Im Idealfall sollten die Argumente genau den gleichen Datentyp aufweisen wie die entsprechenden Parameter.  In jeden Fall muss der Datentyp jedes Arguments zu dem des entsprechenden Parameters erweitert werden.  Dies gilt auch dann, wenn die [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) auf `Off` festgelegt ist.  Wenn eine Überladung eine eingrenzende Konvertierung aus der Argumentliste erfordert, kann diese Überladung nicht aufgerufen werden.  
  
-   Wenn Sie Argumente angeben, die erweitert werden müssen, sollten deren Datentypen möglichst eng an die entsprechenden Parameterdatentypen angelehnt sein.  Wenn die Argumentdatentypen von zwei oder mehr Überladungen akzeptiert werden, löst der Compiler den Aufruf in die Überladung mit dem geringsten Erweiterungsaufwand auf.  
  
 Die Wahrscheinlichkeit von Datentypenkonflikten reduzieren Sie, indem Sie beim Erstellen der Argumente das [CType\-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)\-Konvertierungsschlüsselwort verwenden.  
  
### Fehler bei der Auflösung von Überladungen  
 Wenn Sie eine überladene Prozedur aufrufen, versucht der Compiler, alle Überladungen bis auf eine zu beseitigen.  Im Erfolgsfall wird der Aufruf in diese Überladung aufgelöst.  Wenn der Compiler alle Überladungen beseitigt oder wenn er die in Frage kommenden Überladungen nicht auf eine einzige reduzieren kann, wird ein Fehler generiert.  
  
 Im folgenden Beispiel wird der Prozess der Überladungsauflösung dargestellt.  
  
 [!code-vb[VbVbcnProcedures#62](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/troubleshooting-procedures_6.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/troubleshooting-procedures_7.vb)]  
  
 Im ersten Aufruf beseitigt der Compiler die erste Überladung, da der Typ des ersten Arguments \(`Short`\) auf den Typ des entsprechenden Parameters \(`Byte`\) eingeschränkt wird.  Anschließend wird die dritte Überladung beseitigt, da jeder Argumenttyp der zweiten Überladung \(`Short` und `Single`\) in den entsprechenden Typ der dritten Überladung \(`Integer` und `Single`\) erweitert wird.  Da die zweite Überladung eine geringere Erweiterung erfordert, wird sie vom Compiler für den Aufruf verwendet.  
  
 Im zweiten Aufruf kann der Compiler keine Überladung durch Einschränken ausschließen.  Die dritte Überladung wird aus dem gleichen Grund beseitigt wie im ersten Aufruf, da nämlich die zweite Überladung mit geringerer Erweiterung der Argumenttypen aufgerufen werden kann.  Zwischen der ersten und zweiten Überladung kann der Compiler jedoch keine Auflösung ausführen.  Jede Überladung hat einen definierten Parametertyp, der in der anderen Überladung in den entsprechenden Typ erweitert wird \(`Byte` in `Short` und `Single` in `Double`\).  Aus diesem Grund generiert der Compiler einen Überladungsauflösungsfehler.  
  
 **Richtige Vorgehensweise:** Um eine überladene Prozedur ohne Zweideutigkeit aufrufen zu können, verwenden Sie die [CType\-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md), damit die Argumentdatentypen mit den Parametertypen übereinstimmen.  Im folgenden Beispiel wird ein Aufruf von `z` dargestellt, der die Auflösung in die zweite Überladung erzwingt.  
  
 [!code-vb[VbVbcnProcedures#65](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/troubleshooting-procedures_8.vb)]  
  
### Überladungsauflösung mit den Argumenten Optional und ParamArray  
 Wenn die Signaturen von zwei Überladungen einer Prozedur sich nur darin unterscheiden, dass der letzte Parameter in der einen Prozedur als [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) und in der anderen als [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) deklariert ist, löst der Compiler einen Aufruf dieser Prozedur nach der größten Übereinstimmung auf.  Weitere Informationen finden Sie unter [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md).  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function\-Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)