---
title: Schreiben eines einfachen parallelen Programms mit Parallel.ForEach
ms.date: 09/12/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cdf4aeb6de027e26687d41d6311b6d7da49e7948
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46562215"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Gewusst wie: Schreiben einer einfachen Parallel.ForEach-Schleife

Dieses Beispiel zeigt die Verwendung einer <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Schleife, um alle <xref:System.Collections.IEnumerable?displayProperty=nameWithType>- oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>-Datenquellen übergreifende Datenparallelität zu ermöglichen.

> [!NOTE]
> In dieser Dokumentation werden Delegaten in PLINQ mithilfe von Lambdaausdrücken definiert. Falls Sie mit der Verwendung von Lambda-Ausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

## <a name="example"></a>Beispiel

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

Eine <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Schleife funktioniert wie eine <xref:System.Threading.Tasks.Parallel.For%2A>-Schleife. Die Quellsammlung ist partitioniert, und für die Arbeit sind basierend auf der Systemumgebung mehrere Threads eingeplant. Je mehr Prozessoren das System aufweist, desto schneller wird die parallele Methode ausgeführt. Bei manchen Quellsammlungen wird eine sequenzielle Schleife je nach Größe der Quelle und Art der Arbeit vielleicht schneller ausgeführt. Weitere Informationen zur Leistung finden Sie unter [Potenzielle Fehler bei Daten- und Aufgabenparallelität](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md).

Weitere Informationen zu parallelen Schleifen finden Sie unter [Gewusst wie: Schreiben einer einfachen Parallel.For-Schleife](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).

Um <xref:System.Threading.Tasks.Parallel.ForEach%2A> mit einer nicht generischen Sammlung zu verwenden, können Sie die Sammlung mithilfe der <xref:System.Linq.Enumerable.Cast%2A>-Erweiterungsmethode in eine generische Sammlung umwandeln, wie im folgenden Beispiel gezeigt:

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

Sie können auch Parallel LINQ (PLINQ) verwenden, um die Verarbeitung von <xref:System.Collections.Generic.IEnumerable%601>-Datenquellen zu parallelisieren. Mit PLINQ können Sie deklarative Abfragesyntax verwenden, um das Schleifenverhalten auszudrücken. Weitere Informationen finden Sie unter [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).

## <a name="compile-and-run-the-code"></a>Kompilieren und Ausführen des Codes

- Kopieren Sie diesen Code, und fügen Sie ihn in ein Visual Studio-**Konsolenanwendungsprojekt** ein.

- Fügen Sie einen Verweis auf „System.Drawing.dll“ hinzu.

- Drücken Sie **F5**.

## <a name="see-also"></a>Siehe auch

- [Datenparallelität](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)
- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
