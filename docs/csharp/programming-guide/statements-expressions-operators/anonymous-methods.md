---
title: "Anonyme Methoden (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Anonyme Methoden [C#]"
  - "Delegaten [C#], Anonyme Methoden"
  - "Methoden [C#], Anonyme"
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# Anonyme Methoden (C#-Programmierhandbuch)
In C\#\-Versionen vor 2.0 bestand die einzige Möglichkeit zum Deklarieren eines [Delegaten](../../../csharp/language-reference/keywords/delegate.md) darin, [benannte Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) zu verwenden.  In C\# 2.0 wurden anonyme Methoden eingeführt, und in C\# 3.0 und höher werden diese von Lambda\-Ausdrücken als bevorzugtes Verfahren zum Schreiben von Inlinecode ersetzt.  Die Informationen zu anonymen Methoden in diesem Thema gelten auch für Lambda\-Ausdrücke.  Nur in einem Fall werden durch eine anonyme Methode Funktionen bereitgestellt, die in Lambda\-Ausdrücken nicht zur Verfügung stehen.  Bei anonymen Methoden können Sie auf eine Verwendung der Parameterliste verzichten.  Dies bedeutet, dass eine anonyme Methode mit einer Vielzahl von Signaturen in Delegaten konvertiert werden kann.  Dies ist bei Lambda\-Ausdrücken nicht möglich.  Weitere Informationen speziell zu Lambda\-Ausdrücken finden Sie unter [Lambda\-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 Anonyme Methoden bieten im Wesentlichen eine Möglichkeit, einen Codeblock als Delegatparameter zu übergeben.  Hier zwei Beispiele:  
  
 [!code-cs[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#6)]  
  
 [!code-cs[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#5)]  
  
 Durch anonyme Methoden wird der Codierungsaufwand des Instanziierens von Delegaten reduziert, weil keine separate Methode erstellt werden muss.  
  
 Beispielsweise kann die Angabe eines Codeblocks anstelle eines Delegaten in einer Situation nützlich sein, in der das Erstellen einer Methode als unnötiger Aufwand erscheinen würde.  Ein gutes Beispiel dafür wäre das Starten eines neuen Threads.  Diese Klasse erstellt einen Thread und enthält außerdem den Code, den der Thread ausführt, ohne dass eine zusätzliche Methode für den Delegaten erstellt werden muss.  
  
 [!code-cs[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#7)]  
  
## Hinweise  
 Der Gültigkeitsbereich der Parameter einer anonymen Methode ist der *anonyme Methodenblock*.  
  
 Das Vorhandensein einer Sprunganweisung \(z. B. [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) oder [continue](../../../csharp/language-reference/keywords/continue.md)\) innerhalb des anonymen Methodenblocks ist ein Fehler, wenn das Ziel außerhalb des Blocks liegt.  Umgekehrt ist das Vorhandensein einer Sprunganweisung \(z. B. `goto`, `break` oder `continue`\) außerhalb des anonymen Methodenblocks ebenfalls ein Fehler, wenn das Ziel innerhalb des Blocks liegt.  
  
 Die lokalen Variablen und Parameter, in deren Gültigkeitsbereich eine anonyme Methodendeklaration enthalten ist, werden als *äußere* Variablen der anonymen Methode bezeichnet.  Zum Beispiel ist `n` im folgenden Codesegment eine äußere Variable:  
  
 [!code-cs[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#8)]  
  
 Ein Verweis auf die äußere Variable `n` gilt als  *erfasst* Wenn der Delegat erstellt wird.  Im Gegensatz zu lokalen Variablen erstreckt sich die Lebensdauer einer erfassten Variablen, bis die Delegaten, die anonymen Methoden verweisen, für Garbagecollection freigegeben werden.  
  
 Eine anonyme Methode kann nicht auf den [ref](../../../csharp/language-reference/keywords/ref.md)\-Parameter oder den [out](../../../csharp/language-reference/keywords/out.md)\-Parameter eines äußeren Gültigkeitsbereichs zugreifen.  
  
 Auf unsicheren Code kann innerhalb des *anonymen Methodenblocks* nicht zugegriffen werden.  
  
 Anonyme Methoden sind auf der linken Seite des Operators [is](../../../csharp/language-reference/keywords/is.md) nicht zugelassen.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei Arten veranschaulicht, einen Delegaten zu instanziieren:  
  
-   Das Zuordnen des Delegaten zu einer anonymen Methode.  
  
-   Das Zuordnen des Delegaten zu einer benannten Methode \(`DoWork`\).  
  
 In beiden Fällen wird eine Meldung angezeigt, wenn der Delegat aufgerufen wird.  
  
 [!code-cs[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#4)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)   
 [Lambda\-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Delegaten mit benannten im Vergleich zu anonymen Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)