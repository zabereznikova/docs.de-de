---
title: 'Vorgehensweise: Ausführen von parallelen Vorgängen mithilfe von „Parallel.Invoke“'
description: Erfahren Sie, wie Sie die Methode Parallel.Invoke aus der Task Parallel Library (TPL) verwenden, die parallele Vorgänge für eine gemeinsame Datenquelle in .NET ausführt.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
ms.openlocfilehash: 6ec8f03216cc6225e909f5dc3128469047826166
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825480"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Vorgehensweise: Ausführen von parallelen Vorgängen mithilfe von „Parallel.Invoke“

In diesem Beispiel wird veranschaulicht, wie Vorgänge parallelisiert werden können, indem <xref:System.Threading.Tasks.Parallel.Invoke%2A> in der Task Parallel Library verwendet wird. Es werden drei Vorgänge für eine freigegebene Datenquelle ausgeführt. Die Vorgänge können auf einfache Weise parallel ausgeführt werden, da die Quelle durch keinen von ihnen geändert wird.

> [!NOTE]
> Diese Dokumentation definiert Delegaten in TPL mithilfe von Lambdaausdrücken. Falls Sie mit Lambdaausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambdaausdrücke in PLINQ und TPL](lambda-expressions-in-plinq-and-tpl.md).

## <a name="example"></a>Beispiel

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

Mit <xref:System.Threading.Tasks.Parallel.Invoke%2A> geben Sie nur an, welche Aktionen gleichzeitig ausgeführt werden sollen. Alle Details der Threadplanung, einschließlich automatischem Skalieren entsprechend der Anzahl von Kernen auf dem Hostcomputer, werden von der Common Language Runtime verwaltet.

In diesem Beispiel werden die Vorgänge, nicht die Daten parallelisiert. Eine alternative Vorgehensweise besteht darin, die LINQ-Abfragen mithilfe von PLINQ zu parallelisieren und die Abfragen sequenziell auszuführen. Sie könnten die Daten aber auch parallelisieren, indem Sie PLINQ verwenden. Eine weitere Möglichkeit ist, sowohl die Abfragen als auch die Aufgaben zu parallelisieren. Durch den resultierenden Mehraufwand kann zwar die Leistung auf Hostcomputern mit relativ wenigen Prozessoren beeinträchtigt werden, die Skalierung auf Computern mit vielen Prozessoren ist jedoch besser.

## <a name="compile-the-code"></a>Kompilieren des Codes

Kopieren Sie das gesamte Beispiel, fügen Sie es in ein Microsoft Visual Studio-Projekt ein, und drücken Sie **F5**.

## <a name="see-also"></a>Siehe auch

- [Parallele Programmierung](index.md)
- [How to: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente](how-to-cancel-a-task-and-its-children.md)
- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](introduction-to-plinq.md)
