---
title: "How to: Pass Arguments to a Procedure (Visual Basic) | Microsoft Docs"
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
  - "arguments [Visual Basic], passing to procedures"
  - "procedures, arguments"
  - "procedures, parameters"
  - "procedure arguments"
  - "Visual Basic code, procedures"
  - "procedure parameters"
  - "procedures, calling"
  - "argument passing, procedures"
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Pass Arguments to a Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie eine Prozedur aufrufen, geben Sie nach dem Prozedurnamen eine Argumentliste in runden Klammern an.  Stellen Sie für jeden erforderlichen Parameter der Prozedur ein Argument bereit, und geben Sie optional für die als `Optional` definierten Parameter Argumente an.  Wenn Sie im Aufruf einen als `Optional` definierten Parameter nicht angeben, müssen Sie ein Komma einfügen, um dessen Position in der Argumentliste zu markieren, falls Sie nachfolgende Argumente angeben.  
  
 Wenn Sie ein Argument übergeben möchten, das einen anderen Datentyp als der zugehörige Parameter hat, z. B. `Byte` an `String`, dann können Sie den Typüberprüfungsschalter \([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) auf `Off` festlegen.  Wenn `Option Strict` den Wert `On` hat, müssen Sie entweder Erweiterungskonvertierungen oder explizite Konvertierungsschlüsselwörter verwenden.  Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Weitere Informationen finden Sie unter [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md).  
  
### So übergeben Sie ein Argument oder mehrere Argumente an eine Prozedur  
  
1.  Geben Sie in der aufrufenden Anweisung nach dem Prozedurnamen runde Klammern an.  
  
2.  Fügen Sie eine Argumentliste in die Klammern ein.  Fügen Sie ein Argument für jeden erforderlichen Parameter ein, den die Prozedur definiert, und trennen Sie die Argumente durch Kommas.  
  
3.  Stellen Sie sicher, dass jedes Argument ein gültiger Ausdruck ist, der zu einem Datentyp ausgewertet wird, der in den Typ konvertiert werden kann, den die Prozedur für den entsprechenden Parameter definiert.  
  
4.  Wenn ein Parameter als [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) definiert ist, können Sie ihn entweder in die Argumentliste einschließen oder weglassen.  Wenn Sie ihn weglassen, verwendet die Prozedur den für diesen Parameter definierten Standardwert.  
  
5.  Wenn Sie für einen als `Optional` definierten Parameter kein Argument angeben und in der Parameterliste diesem Parameter ein anderer folgt, können Sie die Position des ausgelassenen Arguments in der Argumentliste durch ein zusätzliches Komma markieren.  
  
     Im folgenden Beispiel wird die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>\-Funktion aufgerufen.  
  
     [!code-vb[VbVbcnProcedures#34](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-pass-arguments-to_1.vb)]  
  
     Im vorangehenden Beispiel wird das erforderliche erste Argument angegeben, das der anzuzeigenden Meldungszeichenfolge entspricht.  Ausgelassen wird das Argument für den optionalen zweiten Parameter, der die Schaltflächen festlegt, die im Meldungsfeld angezeigt werden sollten.  Da im Aufruf kein Wert angegeben wird, verwendet `MsgBox` den Standardwert `MsgBoxStyle.OKOnly`, der bewirkt, dass nur die Schaltfläche **OK** angezeigt wird.  
  
     Das zweite Komma in der Argumentliste markiert die Position des ausgelassenen zweiten Arguments, und die letzte Zeichenfolge wird an den optionalen dritten Parameter von `MsgBox` übergeben. Hierbei handelt es sich um den Text, der in der Titelleiste angezeigt wird.  
  
## Siehe auch  
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function\-Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define a Parameter for a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-parameter-for-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Recursive Procedures](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Objektorientiertes Programmieren](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)