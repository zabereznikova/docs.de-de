---
title: "How to: Define a Parameter for a Procedure (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedure parameters, defining data types for"
  - "procedures, parameters"
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "procedure parameters, defining"
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Define a Parameter for a Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ein *Parameter* ermöglicht es dem Aufrufcode, einen Wert an die Prozedur zu übergeben, wenn sie vom Code aufgerufen wird.  Parameter für Prozeduren werden auf dieselbe Weise deklariert wie Variablen, d. h., Sie müssen Namen und Datentyp des Parameters angeben.  Darüber hinaus muss der Übergabemechanismus angegeben und festgelegt werden, ob es sich um einen optionalen Parameter handelt.  
  
 Weitere Informationen finden Sie unter [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md).  
  
### So definieren Sie einen Prozedurparameter  
  
1.  Fügen Sie in der Prozedurdeklaration den Parameternamen zur Parameterliste der Prozedur hinzu, und trennen Sie ihn durch ein Komma von anderen Parametern.  
  
2.  Legen Sie den Datentyp des Parameters fest.  
  
3.  Fügen Sie nach dem Parameternamen eine `As`\-Klausel ein, um den Datentyp anzugeben.  
  
4.  Legen Sie den gewünschten Übergabemechanismus für den Parameter fest.  Normalerweise wird ein Parameter als Wert übergeben, es sei denn, die Prozedur soll den Wert des Parameters im Aufrufcode ändern können.  
  
5.  Stellen Sie dem Parameternamen [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) voran, um den Übergabemechanismus anzugeben.  Weitere Informationen finden Sie unter [Differences Between Passing an Argument By Value and By Reference](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6.  Wenn der Parameter optional ist, stellen Sie dem Übergabemechanismus [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) voran, und geben Sie nach dem Datentyp des Parameters ein Gleichheitszeichen \(`=`\) und einen Standardwert ein.  
  
     Im folgenden Beispiel wird die Gliederung einer `Sub`\-Prozedur mit drei Parametern definiert.  Die ersten beiden Parameter sind erforderlich, der dritte ist optional.  Die Parameterdeklarationen werden in der Parameterliste durch Kommas getrennt.  
  
     [!code-vb[VbVbcnProcedures#33](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-define-a-parameter-f_1.vb)]  
  
     Der erste Parameter nimmt ein `customer` \-Objekt an, und `updateCustomer` kann die Variable, die an `c` übergeben wird, direkt aktualisieren, da das Argument mit [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) übergeben wird.  Die Prozedur kann die Werte der beiden letzten Argumente nicht ändern, da sie mit [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) übergeben werden.  
  
     Wenn der Aufrufcode keinen Wert für den `level` \-Parameter enthält, wird er von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] auf den Standardwert 0 festgelegt.  
  
     Wenn die Typüberprüfung \([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) den Wert `Off` hat, ist die `As`\-Klausel bei der Definition eines Parameters optional.  Sobald jedoch ein Parameter eine `As`\-Klausel verwendet, muss sie von allen Parametern verwendet werden.  Wenn die Typüberprüfung den Wert `On` hat, muss die `As`\-Klausel bei jeder Parameterdefinition verwendet werden.  
  
     Die Angabe von Datentypen für alle Programmierelemente wird als *starke Typisierung* bezeichnet.  Wenn Sie `Option Strict On` auswählen, erzwingt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] die starke Typisierung.  Dies wird aus den folgenden Gründen dringend empfohlen:  
  
    -   Dadurch wird die IntelliSense\-Unterstützung für die von Ihnen erstellten Variablen und Parameter aktiviert.  Auf diese Weise können Sie bei der Eingabe des Codes die Eigenschaften der Variablen und Parameter sowie andere Member anzeigen.  
  
    -   Der Compiler kann eine Typüberprüfung durchführen.  Anweisungen, die zur Laufzeit beispielsweise aufgrund eines Überlaufs oder anderer Fehler fehlschlagen können, können dadurch abgefangen werden.  Außerdem werden Aufrufe von Methoden für Objekte, die diese nicht unterstützen, abgefangen.  
  
    -   Sie ermöglicht die schnellere Ausführung des Codes.  Ein Grund hierfür ist, dass der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler dem Programmierelement den `Object`\-Datentyp zuweist, wenn Sie keinen Datentyp dafür festlegen.  Der kompilierte Code müsste zwischen `Object` und anderen Datentypen hin und her konvertieren, wodurch die Leistung reduziert wird.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function\-Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Recursive Procedures](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Objektorientiertes Programmieren](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)