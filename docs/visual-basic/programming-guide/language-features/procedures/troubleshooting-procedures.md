---
title: Verfahren zur Problembehandlung
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: 8d4c4929e299efb12d283492a101c18ae794110b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352518"
---
# <a name="troubleshooting-procedures-visual-basic"></a>Problem Behandlungs Prozeduren (Visual Basic)

Auf dieser Seite werden einige allgemeine Probleme aufgelistet, die bei der Arbeit mit Prozeduren auftreten können.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>Zurückgeben eines Array Typs aus einer Funktions Prozedur

Wenn eine `Function` Prozedur einen Array Datentyp zurückgibt, können Sie den `Function` Namen nicht verwenden, um Werte in den Elementen des Arrays zu speichern. Wenn Sie versuchen, dies zu tun, interpretiert der Compiler ihn als einen aufzurufenden `Function`. Im folgenden Beispiel werden Compilerfehler generiert:
  
```vb
Function AllOnes(n As Integer) As Integer()
   For i As Integer = 1 To n - 1  
      ' The following statement generates a COMPILER ERROR.  
      AllOnes(i) = 1  
   Next  

   ' The following statement generates a COMPILER ERROR.  
   Return AllOnes()  
End Function
```

Die Anweisung `AllOnes(i) = 1` generiert einen Compilerfehler, da Sie `AllOnes` mit einem Argument des falschen Datentyps (ein Skalar`Integer` anstelle eines `Integer` Arrays) aufruft. Die Anweisung `Return AllOnes()` generiert einen Compilerfehler, da Sie anscheinend `AllOnes` ohne Argument aufruft.  
  
 **Korrekter Ansatz:** Um die Elemente eines Arrays ändern zu können, das zurückgegeben werden soll, definieren Sie ein internes Array als lokale Variable. Im folgenden Beispiel wird ohne Fehler kompiliert:

 [!code-vb[VbVbcnProcedures#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#66)]

## <a name="argument-not-modified-by-procedure-call"></a>Argument, das nicht durch Prozedur Aufrufe geändert wurde

Wenn Sie möchten, dass eine Prozedur ein Programmier Element, das einem Argument im aufrufenden Code zugrunde liegt, ändern kann, müssen Sie es als Verweis übergeben. Eine Prozedur kann jedoch auch auf die Elemente eines Verweistyp Arguments zugreifen, auch wenn Sie Sie als Wert übergeben.

- **Zugrunde liegende Variable**. Damit die Prozedur den Wert des zugrunde liegenden Variablen Elements selbst ersetzen kann, muss die Prozedur den Parameter [ByRef](../../../language-reference/modifiers/byref.md)deklarieren. Außerdem darf der aufrufende Code das Argument nicht in Klammern einschließen, da dies den `ByRef` Übergabe Mechanismus überschreiben würde.

- **Verweistyp Elemente**. Wenn Sie einen Parameter [ByVal](../../../language-reference/modifiers/byval.md)deklarieren, kann die Prozedur das zugrunde liegende Variablen Element nicht selbst ändern. Wenn das Argument jedoch ein Verweistyp ist, kann die Prozedur die Member des Objekts, auf das es verweist, ändern, auch wenn es den Wert der Variablen nicht ersetzen kann. Wenn das Argument z. b. eine Array Variable ist, kann die Prozedur kein neues Array zuweisen, kann jedoch ein oder mehrere Elemente ändern. Die geänderten Elemente werden in der zugrunde liegenden Array Variablen im aufrufenden Code widergespiegelt.

Im folgenden Beispiel werden zwei Prozeduren definiert, die eine Array Variable nach Wert akzeptieren und deren Elemente verarbeiten. Prozedur `increase` dem Element einfach ein Element hinzugefügt wird. Die Prozedur `replace` weist dem Parameter `a()` ein neues Array zu und fügt dann jedem Element eine hinzu. Die Neuzuweisung wirkt sich jedoch nicht auf die zugrunde liegende Array Variable im aufrufenden Code aus, da `a()` als `ByVal`deklariert ist.

[!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]

[!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]

Im folgenden Beispiel werden Aufrufe an `increase` und `replace`durchführt:

[!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]
  
Der erste `MsgBox`-aufrufsbefehl zeigt "After Increase (n): 11, 21, 31, 41" an. Da `n` ein Verweistyp ist, kann `increase` seine Member ändern, auch wenn er `ByVal`weitergegeben wurde.

Der zweite `MsgBox`-Aufrufe zeigt "After replace (n): 11, 21, 31, 41" an. Da `n` `ByVal`übermittelt wird, können `replace` die Variable `n` nicht ändern, indem Sie Ihr ein neues Array zuweisen. Wenn `replace` die neue Array Instanz erstellt `k` und Sie der lokalen Variablen `a`zuweist, verliert Sie den Verweis auf `n`, die vom aufrufenden Code übermittelt werden. Wenn die Member von `a`Inkrementen werden, ist nur das lokale Array `k` betroffen.

**Korrekter Ansatz:** Um ein zugrunde liegendes Variablen Element selbst ändern zu können, übergeben Sie es als Verweis. Das folgende Beispiel zeigt die Änderung in der Deklaration von `replace`, die es ermöglicht, ein Array durch ein anderes im aufrufenden Code zu ersetzen:

[!code-vb[VbVbcnProcedures#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#64)]

## <a name="unable-to-define-an-overload"></a>Eine Überladung kann nicht definiert werden.

Wenn Sie eine überladene Version einer Prozedur definieren möchten, müssen Sie denselben Namen, aber eine andere Signatur verwenden. Wenn der Compiler die Deklaration nicht von einer Überladung mit derselben Signatur unterscheiden kann, generiert er einen Fehler.

Die *Signatur* einer Prozedur wird durch den Prozedur Namen und die Parameterliste bestimmt. Jede Überladung muss denselben Namen haben wie alle anderen über Ladungen, muss sich jedoch von allen anderen Komponenten der Signatur unterscheiden. Weitere Informationen finden Sie unter [Procedure Overloading](./procedure-overloading.md).

Die folgenden Elemente, auch wenn Sie die Parameterliste betreffen, sind keine Komponenten der Signatur einer Prozedur:

- Prozedur Modifiziererschlüsselwörter, z. b. `Public`, `Shared`und `Static`.
- Parameter Namen.
- Parametermodifiziererschlüsselwörter wie `ByRef` und `Optional`.
- Der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungs Operators).

Eine Prozedur kann nicht überladen werden, indem Sie nur ein oder mehrere der vorangehenden Elemente unterscheiden.

**Korrekter Ansatz:** Damit eine Prozedur Überladung definiert werden kann, müssen Sie die Signatur verändern. Da Sie denselben Namen verwenden müssen, müssen Sie die Anzahl, Reihenfolge oder Datentypen der Parameter variieren. In einer generischen Prozedur können Sie die Anzahl von Typparametern variieren. In einem Konvertierungs Operator ([CType-Funktion](../../../language-reference/functions/ctype-function.md)) können Sie den Rückgabetyp variieren.

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Überladungs Auflösung mit optionalen und ParamArray-Argumenten

Wenn Sie eine Prozedur mit einem oder mehreren [optionalen](../../../language-reference/modifiers/optional.md) Parametern oder einem [ParamArray](../../../language-reference/modifiers/paramarray.md) -Parameter überladen, müssen Sie das Duplizieren der *impliziten über Ladungen*vermeiden. Weitere Informationen finden Sie unter [Überlegungen zum Überladen von Prozeduren](./considerations-in-overloading-procedures.md).

## <a name="calling-the-wrong-version-of-an-overloaded-procedure"></a>Aufrufen der falschen Version einer überladenen Prozedur

Wenn eine Prozedur über mehrere überladene Versionen verfügt, sollten Sie mit all ihren Parameterlisten vertraut sein und verstehen, wie Visual Basic Aufrufe zwischen den über Ladungen auflöst. Andernfalls können Sie eine Überladung aufrufen, die nicht die gewünschte Überladung ist.

Wenn Sie ermittelt haben, welche Überladung Sie aufrufen möchten, achten Sie darauf, dass Sie die folgenden Regeln beachten:

- Geben Sie die richtige Anzahl von Argumenten und in der richtigen Reihenfolge an.  
- Im Idealfall sollten ihre Argumente genau dieselben Datentypen wie die entsprechenden Parameter aufweisen. In jedem Fall muss der Datentyp jedes Arguments in den entsprechenden Parameter erweitert werden. Dies gilt auch, wenn die [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md) auf `Off`festgelegt ist. Wenn eine Überladung eine einschränkende Konvertierung von ihrer Argumentliste erfordert, kann diese Überladung nicht aufgerufen werden.
- Wenn Sie Argumente angeben, die erweitert werden müssen, legen Sie die Datentypen so nah wie möglich an den entsprechenden Parameter Datentypen. Wenn zwei oder mehr über Ladungen ihre Argument Datentypen akzeptieren, löst der Compiler den Aufruf der-Überladung auf, die für den geringsten Erweiterungs Aufwand aufruft.

Sie können das Risiko von Datentyp Konflikten verringern, indem Sie beim Vorbereiten Ihrer Argumente das Konvertierungs [Schlüsselwort der CType-Funktion](../../../language-reference/functions/ctype-function.md) verwenden.

### <a name="overload-resolution-failure"></a>Fehler bei Überladungs Auflösung

Wenn Sie eine überladene Prozedur aufzurufen, versucht der Compiler, alle außer einer der über Ladungen auszuschließen. Wenn dies erfolgreich ist, wird der Aufrufen dieser Überladung aufgelöst. Wenn alle über Ladungen entfernt werden oder die berechtigten über Ladungen für einen einzelnen Kandidaten nicht reduziert werden können, wird ein Fehler generiert.

Im folgenden Beispiel wird der Überladungs Auflösungsprozess veranschaulicht:

[!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]

[!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]
  
Beim ersten Aufrufen entfernt der Compiler die erste Überladung, da der Typ des ersten Arguments (`Short`) auf den Typ des entsprechenden Parameters (`Byte`) beschränkt wird. Anschließend entfällt die dritte Überladung, da jeder Argumenttyp in der zweiten Überladung (`Short` und `Single`) zum entsprechenden Typ in der dritten Überladung (`Integer` und `Single`) erweitert wird. Die zweite Überladung erfordert weniger Erweiterungen, sodass der Compiler Sie für den-Befehl verwendet.

Im zweiten-Befehl kann der Compiler keine der über Ladungen auf der Basis der Einschränkung ausschließen. Die dritte Überladung wird aus demselben Grund wie beim ersten-Befehl entfernt, da Sie die zweite Überladung mit einer geringeren Erweiterung der Argument Typen aufrufen kann. Der Compiler kann jedoch nicht zwischen der ersten und der zweiten Überladung aufgelöst werden. Jede verfügt über einen definierten Parametertyp, der auf den entsprechenden Typ im anderen erweitert wird (`Byte` `Short`, aber `Single` an `Double`). Der Compiler generiert daher einen Fehler bei der Überladungs Auflösung.

**Korrekter Ansatz:** Um eine überladene Prozedur ohne Mehrdeutigkeit aufrufen zu können, verwenden Sie die [CType-Funktion](../../../language-reference/functions/ctype-function.md) , um die Argument Datentypen mit den Parametertypen abzugleichen. Das folgende Beispiel zeigt einen-`z`, der die Auflösung der zweiten Überladung erzwingt.

[!code-vb[VbVbcnProcedures#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#65)]

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Überladungs Auflösung mit optionalen und ParamArray-Argumenten

Wenn zwei über Ladungen einer Prozedur identische Signaturen aufweisen, mit dem Unterschied, dass der letzte Parameter in einem und [ParamArray](../../../language-reference/modifiers/paramarray.md) in der anderen als [optional](../../../language-reference/modifiers/optional.md) deklariert wird, löst der Compiler einen aufzurufenden Vorgang entsprechend der nächstgelegenen Übereinstimmung auf. Weitere Informationen finden Sie unter [Overload Resolution](./overload-resolution.md).

## <a name="see-also"></a>Siehe auch

- [Verfahren](index.md)
- [Sub-Prozeduren](sub-procedures.md)
- [Function-Prozeduren](function-procedures.md)
- [Eigenschaftenprozeduren](property-procedures.md)
- [Operatorprozeduren](operator-procedures.md)
- [Parameter und Argumente von Prozeduren](procedure-parameters-and-arguments.md)
- [Prozedurüberladung](procedure-overloading.md)
- [Überlegungen zur Prozedurüberladung](considerations-in-overloading-procedures.md)
- [Überladungsauflösung](overload-resolution.md)
