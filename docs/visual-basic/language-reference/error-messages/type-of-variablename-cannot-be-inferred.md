---
title: "Type of &#39;&lt;variablename&gt;&#39; cannot be inferred because the loop bounds and the step variable do not widen to the same type | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30982"
  - "vbc30982"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30982"
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# Type of &#39;&lt;variablename&gt;&#39; cannot be inferred because the loop bounds and the step variable do not widen to the same type
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Sie haben eine `For...Next`\-Schleife geschrieben, in der der Compiler aufgrund der folgenden Bedingungen keinen Datentyp für die Schleifensteuerungsvariable ableiten kann:  
  
-   Der Datentyp der Schleifensteuerungsvariablen wird nicht mit einer `As`\-Klausel angegeben.  
  
-   Die Schleifenbegrenzungen und die step\-Variable enthalten mindestens zwei Datentypen.  
  
-   Zwischen den Datentypen werden keine Standardkonvertierungen unterstützt.  
  
 Daher kann der Compiler den Datentyp einer Schleifensteuerungsvariablen nicht ableiten.  
  
 Im folgenden Beispiel entspricht die step\-Variable einem Zeichen, und die Schleifenbegrenzungen sind ganze Zahlen.  Da es keine Standardkonvertierung zwischen Zeichen und ganzen Zahlen gibt, wird dieser Fehler gemeldet.  
  
```vb#  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 **Fehler\-ID:** BC30982  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie ggf. die Typen der Schleifenbegrenzungen und step\-Variablen, sodass mindestens eine einem Typ entspricht, in den andere erweitert werden können.  Ändern Sie im vorhergehenden Beispiel den Typ von `stepVar` auf `Integer`.  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     \- oder \-  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   Verwenden Sie explizite Konvertierungsfunktionen, um Schleifenbegrenzungen und step\-Variable in die entsprechenden Typen zu konvertieren.  Wenden Sie im vorhergehenden Beispiel die `Val`\-Funktion auf `stepVar` an.  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>   
 [For...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)