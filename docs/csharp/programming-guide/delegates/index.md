---
title: "Delegaten (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Delegaten"
  - "Delegaten [C#]"
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Delegaten (C#-Programmierhandbuch)
Ein [Delegat](../../../csharp/language-reference/keywords/delegate.md) ist ein Typ, der Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp darstellt.  Wenn Sie einen Delegaten instanziieren, können Sie jeder Methode seine Instanz mit einer kompatiblen Signatur und dem Rückgabetyp zuordnen.  Sie können die Methode über die Delegatinstanz aufrufen.  
  
 Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.  Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden.  Wenn Sie eine benutzerdefinierte Methode erstellen, kann eine Klasse wie das Windows\-Steuerelement diese Methode aufrufen, sobald ein bestimmtes Ereignis eintritt.  Das folgende Beispiel veranschaulicht die Deklaration eines Delegaten:  
  
 [!code-cs[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]  
  
 Jede Methode einer beliebigen verfügbaren Klasse oder Struktur, die mit dem Delegattyp übereinstimmt, kann dem Delegaten zugewiesen werden.  Bei der Methode kann es sich um eine statische Methode oder um eine Instanzenmethode handeln.  Dies ermöglicht das programmgesteuerte Ändern von Methodenaufrufen sowie die Integration von neuem Code in bereits vorhandene Klassen.  
  
> [!NOTE]
>  In Verbindung mit dem Überladen von Methoden schließt die Signatur einer Methode den Rückgabewert nicht ein.  Bei Delegaten ist der Rückgabewert jedoch in die Signatur eingeschlossen.  Mit anderen Worten muss eine Methode denselben Rückgabetyp haben wie der Delegat.  
  
 Diese Fähigkeit, als Parameter auf eine Methode zu verweisen, macht Delegaten ideal für das Definieren von Rückrufmethoden.  Beispielsweise kann ein Verweis auf eine Methode, die zwei Objekte vergleicht, als Argument an einen Sortieralgorithmus übergeben werden.  Da sich der Vergleichscode in einer separaten Prozedur befindet, kann der Sortieralgorithmus allgemeiner geschrieben werden.  
  
## Übersicht über Delegaten  
 Delegaten verfügen über folgende Eigenschaften:  
  
-   Delegaten ähneln C\+\+\-Funktionszeigern, sind aber typsicher.  
  
-   Delegaten ermöglichen es, Methoden als Parameter zu übergeben.  
  
-   Delegaten können zum Definieren von Rückrufmethoden verwendet werden.  
  
-   Delegaten können miteinander verkettet werden. So können beispielsweise mehrere Methoden für ein einziges Ereignis aufgerufen werden.  
  
-   Methoden müssen nicht exakt mit dem Typ des Delegaten übereinstimmen.  Weitere Informationen finden Sie unter [Verwenden von Varianz bei Delegaten](../Topic/Using%20Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md).  
  
-   In C\#, Version 2.0, wurde das Konzept der [anonymen Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) eingeführt, durch die anstelle einer separat definierten Methode Codeblöcke als Parameter übergeben werden können.  In C\# 3.0 wurden Lambda\-Ausdrücke als eine präzisere Methode zum Schreiben von Inlinecodeblöcken eingeführt.  Sowohl anonyme Methoden als auch Lambda\-Ausdrücke werden \(in bestimmten Kontexten\) in Delegattypen kompiliert.  Zusammen werden diese Features jetzt als anonyme Funktionen bezeichnet.  Weitere Informationen zu Lambdaausdrücken finden Sie unter [Anonyme Funktionen](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## In diesem Abschnitt  
  
-   [Verwenden von Delegaten](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [When to Use Delegates Instead of Interfaces \(C\# Programming Guide\)](http://msdn.microsoft.com/de-de/2e759bdf-7ca4-4005-8597-af92edf6d8f0)  
  
-   [Delegaten mit benannten im Vergleich zu anonymen Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [Verwenden von Varianz bei Delegaten](../Topic/Using%20Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md)  
  
-   [Gewusst wie: Kombinieren von Delegaten \(Multicastdelegaten\)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [Gewusst wie: Deklarieren, Instanziieren und Verwenden von Delegaten](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Enthaltene Buchkapitel  
 [Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C\# 3.0 Cookbook, Third Edition: More than 250 solutions for C\# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)  
  
 [Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C\# 3.0: Master the fundamentals of C\# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)  
  
## Siehe auch  
 <xref:System.Delegate>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ereignisse](../../../csharp/programming-guide/events/index.md)