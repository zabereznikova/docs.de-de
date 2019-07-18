---
title: Der Typ von '<variablename>' kann nicht abgeleitet werden, weil die Schleifenbegrenzungen und die step-Klausel nicht in denselben Typ konvertiert werden
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: 2dc7793a837c588b98365a97ada58c67dc07fa03
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664266"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>Geben Sie der "\<Variablenname >' kann nicht abgeleitet werden, weil die schleifenbegrenzungen und die Step-Klausel nicht in denselben Typ konvertiert werden
Sie geschrieben haben eine `For...Next` Schleife, in denen der Compiler nicht werden, einen Datentyp für die Schleifensteuerungsvariable abgeleitet kann da die folgenden Bedingungen erfüllt sind:  
  
- Der Datentyp der Schleifensteuerungsvariablen wird nicht mit einer `As` -Klausel angegeben.  
  
- Die Schleifenbegrenzungen und die step-Variable enthalten mindestens zwei Datentypen.  
  
- Keine standardkonvertierungen vorhanden sein, zwischen den Datentypen.  
  
 Aus diesem Grund kann nicht der Compiler den Datentyp, der eine Schleifensteuerungsvariable ableiten.  
  
 Im folgenden Beispiel die Schritt-Variable ist ein Zeichen, und die schleifenbegrenzungen sind sowohl ganze Zahlen. Da es keine standardkonvertierung zwischen Zeichen und ganze Zahlen ist, wird dieser Fehler gemeldet.  
  
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
  
- Ändern Sie die Typen von die schleifenbegrenzungen und Schritt nach Bedarf, sodass mindestens eine von ihnen ein Typ ist, dem die anderen erweitert werden. Ändern Sie im vorherigen Beispiel ist den Typ des `stepVar` zu `Integer`.  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     – oder –  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
- Verwenden Sie explizite Konvertierungsfunktionen, um die schleifenbegrenzungen und Schritt in die entsprechenden Typen konvertieren. Im vorherigen Beispiel, gelten die `Val` -Funktion `stepVar`.  
  
    ```  
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
