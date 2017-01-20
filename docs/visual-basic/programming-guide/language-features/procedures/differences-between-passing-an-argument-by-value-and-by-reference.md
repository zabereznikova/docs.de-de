---
title: "Differences Between Passing an Argument By Value and By Reference (Visual Basic) | Microsoft Docs"
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
  - "ByRef keyword, passing arguments by reference"
  - "Visual Basic code, procedures"
  - "procedures, passing arguments"
  - "ByVal keyword, passing arguments by value"
  - "arguments [Visual Basic], passing by value or by reference"
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Differences Between Passing an Argument By Value and By Reference (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wenn Sie einer Prozedur ein oder mehrere Argumente übergeben, ist jedes Argument einem zugrunde liegenden Programmierelement im Aufrufcode zugeordnet.  Sie können entweder den Wert dieses zugrunde liegenden Elements oder einen Verweis darauf übergeben.  Dies wird als *Übergabemechanismus* bezeichnet.  
  
## Übergabe als Wert  
 Sie übergeben ein Argument *als Wert*, indem Sie das [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)\-Schlüsselwort für den entsprechenden Parameter in der Prozedurdefinition angeben.  Bei Verwendung dieses Übergabemechanismus kopiert [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] den Wert des zugrunde liegenden Programmierelements in eine lokale Variable der Prozedur.  Der Prozedurcode hat keinen Zugriff auf das zugrunde liegende Element im Aufrufcode.  
  
## Übergabe als Verweis  
 Sie übergeben ein Argument *als Verweis*, indem Sie das [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)\-Schlüsselwort für den entsprechenden Parameter in der Prozedurdefinition angeben.  Bei Verwendung dieses Übergabemechanismus übergibt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] im Aufrufcode einen direkten Verweis auf das zugrunde liegende Programmierelement an die Prozedur.  
  
## Übergabemechanismus und Elementtyp  
 Die Auswahl des Übergabemechanismus ist nicht das Gleiche wie die Klassifizierung des zugrunde liegenden Elementtyps.  Die Übergabe als Wert oder als Verweis bezieht sich darauf, was [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] für den Prozedurcode bereitstellt.  Ein Werttyp oder ein Verweistyp verweist darauf, wie ein Programmierelement im Arbeitsspeicher gespeichert wird.  
  
 Es besteht jedoch ein Zusammenhang zwischen Übergabemechanismus und Elementtyp.  Der Wert eines Verweistyps ist ein Zeiger auf die Daten, die sich an einer anderen Position im Arbeitsspeicher befinden.  Das bedeutet, dass der Prozedurcode bei der Übergabe eines Referenztyps als Wert über einen Zeiger auf die Daten des zugrunde liegenden Elements verfügt, auch wenn er nicht auf das zugrunde liegende Programmierelement selbst zugreifen kann.  Wenn das Element beispielsweise eine Arrayvariable ist, hat der Prozedurcode keinen Zugriff auf die eigentliche Variable, aber er kann auf die Arraymember zugreifen.  
  
## Änderungsmöglichkeit  
 Ein als Argument übergebenes nicht veränderbares Element kann von der Prozedur nie im Aufrufcode geändert werden. Dabei spielt es keine Rolle, ob es mit `ByVal` oder `ByRef` übergeben wurde.  
  
 In der folgenden Tabelle wird die Interaktion zwischen dem Elementtyp und dem Übergabemechanismus bei änderbaren Elementen dargestellt.  
  
|Elementtyp|Übergabe mit `ByVal`|Übergabe mit `ByRef`|  
|----------------|--------------------------|--------------------------|  
|Werttyp \(enthält nur einen Wert\)|Die Variable und ihre Member können in der Prozedur nicht geändert werden.|Die Variable und ihre Member können in der Prozedur geändert werden.|  
|Verweistyp \(enthält einen Zeiger auf eine Klassen\- oder Strukturinstanz\)|Die Prozedur kann die Variable nicht ändern, jedoch die Member der Instanz, auf die sie zeigt.|Die Variable und die Member der Instanz, auf die sie zeigt, können in der Prozedur geändert werden.|  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Differences Between Modifiable and Nonmodifiable Arguments](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [How to: Change the Value of a Procedure Argument](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [How to: Protect a Procedure Argument Against Value Changes](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [How to: Force an Argument to Be Passed by Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)