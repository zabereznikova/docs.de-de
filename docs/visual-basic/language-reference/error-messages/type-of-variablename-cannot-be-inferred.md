---
title: Der Typ von '<variablename>' kann nicht abgeleitet werden, weil die Schleifenbegrenzungen und die step-Klausel nicht in denselben Typ konvertiert werden
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: c3086f79fb71693810bc8f14e8c0f493aa1e6515
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512705"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>Der Typ von\<"VariableName >" kann nicht abgeleitet werden, weil die Schleifen Begrenzungen und die Step-Variable nicht auf denselben Typ ausgedehnt werden.

Sie haben eine `For...Next` Schleife geschrieben, in der der Compiler einen Datentyp für die Schleifen Steuerungs Variable nicht ableiten kann, da die folgenden Bedingungen zutreffen:

- Der Datentyp der Schleifensteuerungsvariablen wird nicht mit einer `As` -Klausel angegeben.

- Die Schleifenbegrenzungen und die step-Variable enthalten mindestens zwei Datentypen.

- Zwischen den Datentypen sind keine Standard Konvertierungen vorhanden.

 Daher kann der Compiler den Datentyp der Steuerungsvariablen einer Schleife nicht ableiten.

 Im folgenden Beispiel ist die Step-Variable ein Zeichen, und die Schleifen Begrenzungen sind beide Integer. Da es keine Standard Konvertierung zwischen Zeichen und ganzen Zahlen gibt, wird dieser Fehler gemeldet.

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

**Fehler-ID:** BC30982

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Ändern Sie die Typen der Schleifen Begrenzungen und die Step-Variable nach Bedarf, damit mindestens einer der Typen ein Typ ist, zu dem die anderen erweitert werden. Ändern Sie im vorherigen Beispiel den Typ von `stepVar` in. `Integer`

  ```vb
  Dim stepVar = 1
  ```

  -oder-

  ```vb
  Dim stepVar As Integer = 1
  ```

- Verwenden Sie explizite Konvertierungs Funktionen, um die Schleifen Begrenzungen und die Step-Variable in die entsprechenden Typen zu konvertieren. Wenden Sie im vorherigen Beispiel die `Val` -Funktion auf an. `stepVar`

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
