---
title: Delegaten – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
ms.openlocfilehash: c0f28716926d4c9d74cde58fd00e27d1fdfa7ce1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705365"
---
# <a name="delegates-c-programming-guide"></a>Delegaten (C#-Programmierhandbuch)
Ein [Delegat](../../language-reference/builtin-types/reference-types.md) ist ein Typ, der Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp darstellt. Nach Instanziierung eines Delegaten können Sie die Instanz mit einer beliebigen Methode verknüpfen, die eine kompatible Signatur und einen kompatiblen Rückgabetyp aufweist. Sie können die Methode über die Delegatinstanz aufrufen.  
  
 Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben. Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden. Wenn Sie eine benutzerdefinierte Methode erstellen, kann eine Klasse wie das Windows-Steuerelement diese Methode aufrufen, sobald ein bestimmtes Ereignis eintritt. Das folgende Beispiel veranschaulicht die Deklaration eines Delegaten:  
  
 [!code-csharp[csProgGuideDelegates#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#20)]  
  
 Jede Methode einer beliebigen verfügbaren Klasse oder Struktur, die mit dem Delegattyp übereinstimmt, kann dem Delegaten zugewiesen werden. Bei der Methode kann es sich um eine statische Methode oder um eine Instanzenmethode handeln. Dies ermöglicht das programmgesteuerte Ändern von Methodenaufrufen sowie die Integration von neuem Code in bereits vorhandene Klassen.  
  
> [!NOTE]
> In Verbindung mit dem Überladen von Methoden schließt die Signatur einer Methode den Rückgabewert nicht ein. Bei Delegaten ist der Rückgabewert jedoch in die Signatur eingeschlossen. Mit anderen Worten muss eine Methode denselben Rückgabetyp haben wie der Delegat.  
  
 Diese Fähigkeit, als Parameter auf eine Methode zu verweisen, macht Delegaten ideal für das Definieren von Rückrufmethoden. Beispielsweise kann ein Verweis auf eine Methode, die zwei Objekte vergleicht, als Argument an einen Sortieralgorithmus übergeben werden. Da sich der Vergleichscode in einer separaten Prozedur befindet, kann der Sortieralgorithmus allgemeiner geschrieben werden.  
  
## <a name="delegates-overview"></a>Übersicht über Delegaten  
 Delegaten verfügen über folgende Eigenschaften:  
  
- Delegaten ähneln C++-Funktionszeigern, sind aber vollständig objektorientiert, und im Gegensatz zu C++-Zeigern auf Memberfunktionen kapseln Delegaten sowohl eine Objektinstanz als auch eine Methode.
  
- Delegaten ermöglichen es, Methoden als Parameter zu übergeben.  
  
- Delegaten können zum Definieren von Rückrufmethoden verwendet werden.  
  
- Delegaten können miteinander verkettet werden. So können beispielsweise mehrere Methoden für ein einziges Ereignis aufgerufen werden.  
  
- Methoden müssen nicht exakt mit dem Typ des Delegaten übereinstimmen. Weitere Informationen finden Sie unter [Verwenden von Varianz in Delegaten](../concepts/covariance-contravariance/using-variance-in-delegates.md).  
  
- In C#, Version 2.0, wurde das Konzept der [anonymen Methoden](../../language-reference/operators/delegate-operator.md) eingeführt, durch die anstelle einer separat definierten Methode Codeblöcke als Parameter übergeben werden können. In C# 3.0 wurden Lambdaausdrücke als eine präzisere Methode zum Schreiben von Inlinecodeblöcken eingeführt. Sowohl anonyme Methoden als auch Lambda-Ausdrücke werden (in bestimmten Kontexten) in Delegattypen kompiliert. Zusammen werden diese Funktionen jetzt als anonyme Funktionen bezeichnet. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambdaausdrücke](../statements-expressions-operators/lambda-expressions.md).
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
- [Verwenden von Delegaten](./using-delegates.md)  
  
- [Verwenden von Delegaten anstelle Schnittstellen (C#-Programmierhandbuch)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))  
  
- [Delegate mit benannten im Vergleich zu anonymen Methoden](./delegates-with-named-vs-anonymous-methods.md)  
  
- [Verwenden von Varianz bei Delegaten](../concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
- [Kombinieren von Delegaten (Multicastdelegaten)](./how-to-combine-delegates-multicast-delegates.md)  
  
- [Deklarieren, Instanziieren und Verwenden von Delegaten](./how-to-declare-instantiate-and-use-a-delegate.md)

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

Weitere Informationen erhalten Sie unter [Delegaten](~/_csharplang/spec/delegates.md) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
  
## <a name="featured-book-chapters"></a>Enthaltene Buchkapitel  
 [Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegaten, Ereignisse und Lambda-Ausdrücke) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (C# 3.0-Cookbook, 3. Auflage: Mehr als 250 Lösungen für C# 3.0-Programmierer)  
  
 [Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) (Delegaten und Ereignisse) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29) (Erlernen von C# 3.0: Die Grundlagen von C# 3.0)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Delegate>
- [C#-Programmierhandbuch](../index.md)
- [Ereignisse](../events/index.md)
