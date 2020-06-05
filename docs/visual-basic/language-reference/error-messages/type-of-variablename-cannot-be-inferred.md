---
title: Der Typ von '<variablename>' kann nicht abgeleitet werden, weil die Schleifenbegrenzungen und die step-Klausel nicht in denselben Typ konvertiert werden
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: 74b690ce3dee87e481c629a254e629be4b40f8cd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387009"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>Der Typ von '\<variablename>' kann nicht abgeleitet werden, weil die Schleifenbegrenzungen und die step-Klausel nicht in denselben Typ konvertiert werden

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

- Ändern Sie die Typen der Schleifen Begrenzungen und die Step-Variable nach Bedarf, damit mindestens einer der Typen ein Typ ist, zu dem die anderen erweitert werden. Ändern Sie im vorherigen Beispiel den Typ von `stepVar` in `Integer` .

  ```vb
  Dim stepVar = 1
  ```

  Oder

  ```vb
  Dim stepVar As Integer = 1
  ```

- Verwenden Sie explizite Konvertierungs Funktionen, um die Schleifen Begrenzungen und die Step-Variable in die entsprechenden Typen zu konvertieren. Wenden Sie im vorherigen Beispiel die- `Val` Funktion auf an `stepVar` .

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [For...Next-Anweisung](../statements/for-next-statement.md)
- [Implizite und explizite Konvertierungen](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md)
- [Option Infer-Anweisung](../statements/option-infer-statement.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
