---
title: Delegaten (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
ms.openlocfilehash: 96de5601c60dd309fe5467414affd20b8bc93d87
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48584198"
---
# <a name="delegates-c-programming-guide"></a>Delegaten (C#-Programmierhandbuch)
Ein [Delegat](../../../csharp/language-reference/keywords/delegate.md) ist ein Typ, der Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp darstellt. Wenn Sie einen Delegaten instanziieren, können Sie jeder Methode seine Instanz mit einer kompatiblen Signatur und dem Rückgabetyp zuordnen. Sie können die Methode über die Delegatinstanz aufrufen.  
  
 Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben. Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden. Wenn Sie eine benutzerdefinierte Methode erstellen, kann eine Klasse wie das Windows-Steuerelement diese Methode aufrufen, sobald ein bestimmtes Ereignis eintritt. Das folgende Beispiel veranschaulicht die Deklaration eines Delegaten:  
  
 [!code-csharp[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]  
  
 Jede Methode einer beliebigen verfügbaren Klasse oder Struktur, die mit dem Delegattyp übereinstimmt, kann dem Delegaten zugewiesen werden. Bei der Methode kann es sich um eine statische Methode oder um eine Instanzenmethode handeln. Dies ermöglicht das programmgesteuerte Ändern von Methodenaufrufen sowie die Integration von neuem Code in bereits vorhandene Klassen.  
  
> [!NOTE]
>  In Verbindung mit dem Überladen von Methoden schließt die Signatur einer Methode den Rückgabewert nicht ein. Bei Delegaten ist der Rückgabewert jedoch in die Signatur eingeschlossen. Mit anderen Worten muss eine Methode denselben Rückgabetyp haben wie der Delegat.  
  
 Diese Fähigkeit, als Parameter auf eine Methode zu verweisen, macht Delegaten ideal für das Definieren von Rückrufmethoden. Beispielsweise kann ein Verweis auf eine Methode, die zwei Objekte vergleicht, als Argument an einen Sortieralgorithmus übergeben werden. Da sich der Vergleichscode in einer separaten Prozedur befindet, kann der Sortieralgorithmus allgemeiner geschrieben werden.  
  
## <a name="delegates-overview"></a>Übersicht über Delegaten  
 Delegaten verfügen über folgende Eigenschaften:  
  
-   Delegaten ähneln C++-Funktionszeigern, sind aber vollständig objektorientiert, und im Gegensatz zu C++-Zeigern auf Memberfunktionen kapseln Delegaten sowohl eine Objektinstanz als auch eine Methode.
  
-   Delegaten ermöglichen es, Methoden als Parameter zu übergeben.  
  
-   Delegaten können zum Definieren von Rückrufmethoden verwendet werden.  
  
-   Delegaten können miteinander verkettet werden. So können beispielsweise mehrere Methoden für ein einziges Ereignis aufgerufen werden.  
  
-   Methoden müssen nicht exakt mit dem Typ des Delegaten übereinstimmen. Weitere Informationen finden Sie unter [Verwenden von Varianz in Delegaten](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).  
  
-   In C#, Version 2.0, wurde das Konzept der [anonymen Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) eingeführt, durch die anstelle einer separat definierten Methode Codeblöcke als Parameter übergeben werden können. In C# 3.0 wurden Lambdaausdrücke als eine präzisere Methode zum Schreiben von Inlinecodeblöcken eingeführt. Sowohl anonyme Methoden als auch Lambda-Ausdrücke werden (in bestimmten Kontexten) in Delegattypen kompiliert. Zusammen werden diese Funktionen jetzt als anonyme Funktionen bezeichnet. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
-   [Verwenden von Delegaten](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [Verwenden von Delegaten anstelle Schnittstellen (C#-Programmierhandbuch)](https://msdn.microsoft.com/library/2e759bdf-7ca4-4005-8597-af92edf6d8f0)  
  
-   [Delegate mit benannten im Vergleich zu anonymen Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [Verwenden von Varianz bei Delegaten](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [How to: Combine Delegates (Multicast Delegates) (Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten))](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [Gewusst wie: Deklarieren, Instanziieren und Verwenden von Delegaten](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a>Enthaltene Buchkapitel  
 [Delegaten, Ereignisse und Lambda-Ausdrücke](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) im [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)  
  
 [Delegaten und Ereignisse](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Delegate>  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Ereignisse](../../../csharp/programming-guide/events/index.md)
