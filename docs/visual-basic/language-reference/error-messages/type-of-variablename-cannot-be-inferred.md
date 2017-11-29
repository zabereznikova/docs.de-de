---
title: Typ des &#39; &lt;Variablename&gt;&#39; kann nicht abgeleitet werden, weil die schleifenbegrenzungen und die Step-Variable nicht auf den gleichen Typ erweitert werden
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords: BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 022e29e38a93d2880bbfa250e65a8b95b39ff140
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="type-of-39ltvariablenamegt39-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>Typ des &#39; &lt;Variablename&gt;&#39; kann nicht abgeleitet werden, weil die schleifenbegrenzungen und die Step-Variable nicht auf den gleichen Typ erweitert werden
Sie selbst geschrieben haben eine `For...Next` Schleife, in denen der Compiler keinen Datentyp für die Loop-Steuerelementvariable ableiten, da die folgenden Bedingungen erfüllt sind:  
  
-   Der Datentyp der Schleifensteuerungsvariablen wird nicht mit einer `As` -Klausel angegeben.  
  
-   Die Schleifenbegrenzungen und die step-Variable enthalten mindestens zwei Datentypen.  
  
-   Keine standardmäßigen Konvertierungen werden zwischen den Datentypen vorhanden.  
  
 Aus diesem Grund kann nicht der Compiler den Datentyp, der eine Schleifensteuerungsvariable ableiten.  
  
 Im folgenden Beispiel die Step-Variable ist ein Zeichen, und die schleifenbegrenzungen sind beide ganze Zahlen. Da es sich keine standardkonvertierung zwischen Zeichen mit und ganze Zahlen, wird dieser Fehler gemeldet.  
  
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
  
-   Ändern Sie die Typen von die schleifenbegrenzungen und die Step-Variable nach Bedarf, sodass mindestens einer dieser Anweisungstypen ein Typ, dem die anderen ist, erweitert werden. Ändern Sie den Typ der im vorherigen Beispiel `stepVar` auf `Integer`.  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     – oder –  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   Verwenden Sie explizite Konvertierungsfunktionen, um die schleifenbegrenzungen und die Step-Variable auf die entsprechenden Typen konvertieren. Im vorherigen Beispiel gelten die `Val` -Funktion `stepVar`.  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
