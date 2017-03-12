---
title: "Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc32053"
  - "vbc32053"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32053"
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Eine Prozedur wird mit einem Argument aufgerufen, das den entsprechenden Parametertyp erweitert, und die Konvertierung vom Parameter in das Argument führt zu einer Einschränkung.  
  
 Wenn Sie eine Klasse oder Struktur definieren, können Sie einen oder mehrere Konvertierungsoperatoren festlegen, um den Klassen\- oder Strukturtyp in andere Typen zu konvertieren.  Sie können auch Konvertierungsoperatoren für die umgekehrte Konvertierung festlegen, um die anderen Typen in den Klassen\- oder Strukturtyp zurückzukonvertieren.  Wenn Sie den Klassen\- oder Strukturtyp in einem Prozeduraufruf verwenden, kann [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] mithilfe dieser Konvertierungsoperatoren den Typ eines Arguments in den Typ des entsprechenden Parameters konvertieren.  
  
 Wenn Sie das Argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) übergeben, kopiert [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] zuweilen den Argumentwert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben.  In diesem Fall muss [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] anschließend beim Beenden der Prozedur den Wert der lokalen Variablen in das Argument im aufrufenden Code zurückkopieren.  
  
 Wenn der Wert eines `ByRef`\-Arguments in die Prozedur kopiert wird und Argument sowie Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich.  Wenn sich die Typen jedoch unterscheiden, muss [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] in beide Richtungen konvertieren.  Wenn es sich bei einem der Typen um den Klassen\- oder Strukturtyp handelt, muss [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] beide Typen in den jeweils anderen Typ konvertieren.  Wenn eine dieser Konvertierungen eine Erweiterungskonvertierung ist, ist die umgekehrte Konvertierung möglicherweise eine einschränkende Konvertierung.  
  
 **Fehler\-ID:** BC32053  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie nach Möglichkeit ein aufrufendes Argument von demselben Typ wie der Prozedurparameter, damit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] keine Konvertierung ausführen muss.  
  
-   Wenn Sie die Prozedur mit einem anderen Argumenttyp als dem Parametertyp aufrufen müssen, jedoch in das aufrufende Argument kein Wert zurückgegeben werden muss, definieren Sie den Parameter als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) statt als `ByRef`.  
  
-   Wenn in das aufrufende Argument ein Wert zurückgegeben werden muss, definieren Sie den Operator für die umgekehrte Konvertierung nach Möglichkeit als [Widening](../../../visual-basic/language-reference/modifiers/widening.md).  
  
## Siehe auch  
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)