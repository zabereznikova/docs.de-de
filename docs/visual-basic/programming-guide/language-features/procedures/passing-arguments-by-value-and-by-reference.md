---
title: "Passing Arguments by Value and by Reference (Visual Basic) | Microsoft Docs"
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
  - "ByRef keyword, passing arguments by reference"
  - "Visual Basic code, procedures"
  - "passing arguments, by value or by reference"
  - "ByVal keyword, passing arguments by value"
  - "arguments [Visual Basic], passing by value or by reference"
  - "argument passing, by value or by reference"
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Passing Arguments by Value and by Reference (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] kann ein Argument *als Wert* oder *als Verweis* an eine Prozedur übergeben werden.  Dies wird als *Übergabemechanismus* bezeichnet und legt fest, ob die Prozedur das Programmelement, das dem Argument im Aufrufcode zugrunde liegt, ändern kann.  In der Prozedurdeklaration wird der Übergabemechanismus durch die Angabe des [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)\-Schlüsselworts oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)\-Schlüsselworts für jeden Parameter festgelegt.  
  
## Unterscheidungen  
 Wenn ein Argument an eine Prozedur übergeben wird, sind verschiedene Unterscheidungen zu beachten, zwischen denen eine Wechselwirkung besteht:  
  
-   Ob das zugrunde liegende Programmierelement änderbar oder nicht veränderbar ist  
  
-   Ob das Argument selbst änderbar oder nicht veränderbar ist  
  
-   Ob das Argument als Wert oder als Verweis übergeben wird  
  
-   Ob der Argumentdatentyp ein Werttyp oder ein Verweistyp ist  
  
 Weitere Informationen finden Sie unter [Differences Between Modifiable and Nonmodifiable Arguments](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md) und [Differences Between Passing an Argument By Value and By Reference](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## Wahl des Übergabemechanismus  
 Sie sollten den Übergabemechanismus für jedes Argument sorgfältig auswählen.  
  
-   **Schutz**.  Bei der Wahl eines der beiden Übergabemechanismen fällt vor allem ins Gewicht, ob die Aufrufvariablen geändert werden dürfen oder nicht.  Der Vorteil der Argumentübergabe `ByRef` besteht darin, dass die Prozedur durch dieses Argument einen Wert an den Aufrufcode zurückgeben kann.  Der Vorteil der Argumentübergabe `ByVal` besteht darin, dass die Variable vor Änderungen durch die Prozedur geschützt wird.  
  
-   **Leistung**.  Möglicherweise wirkt sich der Übergabemechanismus auf die Leistung des Codes aus, jedoch ist dies normalerweise unbedeutend.  Eine Ausnahme bildet ein `ByVal` übergebener Werttyp.  Hier kopiert [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] den gesamten Dateninhalt des Arguments.  Deshalb kann die Übergabe `ByRef` bei umfassenden Werttypen wie Strukturen effizienter sein.  
  
     Bei Verweistypen wird lediglich der Zeiger auf die Daten kopiert \(vier Bytes bei 32\-Bit\-Plattformen, acht Bytes bei 64\-Bit\-Plattformen\).  Deshalb können Argumente vom Typ `String` oder vom Typ `Object` ohne Leistungseinbußen als Wert übergeben werden.  
  
## Bestimmen des Übergabemechanismus  
 Die Prozedurdeklaration gibt den Übergabemechanismus für jeden Parameter an.  Der Aufrufcode kann einen `ByVal` \- Mechanismus nicht überschreiben.  
  
 Wenn ein Parameter mit `ByRef` deklariert wird, kann der Aufrufcode den Mechanismus für `ByVal` erzwingen, indem er den Argumentnamen in Klammern im \- Aufruf einschließt.  Weitere Informationen finden Sie unter [How to: Force an Argument to Be Passed by Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md).  
  
 Standardmäßig werden Argumente in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] als Wert übergeben.  
  
## Wann ein Argument als Wert übergeben werden sollte  
  
-   Wenn das aufrufende Codeelement, das dem Argument zugrunde liegt, ein nicht veränderbares Element ist, deklarieren Sie den entsprechenden Parameter mit [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  Der Wert eines nicht veränderbaren Elements kann nicht geändert werden.  
  
-   Wenn das zugrunde liegende Element änderbar ist, die Prozedur dessen Wert aber nicht ändern können soll, deklarieren Sie den Parameter mit `ByVal`.  Nur der Aufrufcode kann den Wert eines änderbaren Elements ändern, das als Wert übergeben wird.  
  
## Wann ein Argument als Verweis übergeben werden sollte  
  
-   Falls die Prozedur das zugrunde liegende Element im Aufrufcode unbedingt ändern können muss, deklarieren Sie den entsprechenden Parameter mit [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  
  
-   Wenn die ordnungsgemäße Codeausführung von der Prozedur abhängt, die das zugrunde liegende Element im Aufrufcode ändert, deklarieren Sie den Parameter mit `ByRef`.  Wenn er als Wert übergeben wird oder wenn der Aufrufcode den `ByRef`\-Übergabemechanismus überschreibt, indem das Argument in Klammern angegeben wird, kann der Prozeduraufruf zu unerwarteten Ergebnissen führen.  
  
## Beispiel  
  
### Description  
 Im folgenden Beispiel wird veranschaulicht, in welchen Fällen Argumente als Wert und in welchen Fällen als Verweis zu übergeben sind.  Die Prozedur `Calculate` verfügt über einen `ByVal`\-Parameter und einen `ByRef`\-Parameter.  Gegeben sind ein Zinssatz \(`rate`\) und ein Betrag \(`debt`\). Die Aufgabe der Prozedur besteht darin, einen neuen Wert für `debt` zu berechnen, der sich aus der Anwendung des Zinssatzes auf den Ursprungswert von `debt` ergibt.  Da `debt` ein `ByRef`\-Parameter ist, wird der neue Gesamtbetrag im Wert des Arguments im aufrufenden Code widergespiegelt, der `debt` entspricht.  Der Parameter `rate` ist ein `ByVal`\-Parameter, da sein Wert von `Calculate` nicht geändert werden darf.  
  
### Code  
 [!code-vb[VbVbcnProcedures#74](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/passing-arguments-by-val_1.vb)]  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [How to: Change the Value of a Procedure Argument](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [How to: Protect a Procedure Argument Against Value Changes](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [How to: Force an Argument to Be Passed by Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)