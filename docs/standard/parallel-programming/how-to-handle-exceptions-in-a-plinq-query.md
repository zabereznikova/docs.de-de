---
title: 'Gewusst wie: Behandeln von Ausnahmen in einer PLINQ-Abfrage'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
ms.openlocfilehash: 5ccddfb01d6b173900dfffc465292c7812626ddc
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "80587986"
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a>Gewusst wie: Behandeln von Ausnahmen in einer PLINQ-Abfrage

Das erste Beispiel in diesem Thema zeigt, wie die <xref:System.AggregateException?displayProperty=nameWithType> behandelt wird, die während der Ausführung von einer PLINQ-Abfrage ausgelöst werden kann. Das zweite Beispiel zeigt, wie try-catch-Blöcke in Delegaten so nah wie möglich an der Position platziert werden, an der die Ausnahme ausgelöst wird. Auf diese Weise können Sie sie sofort nach dem Auftreten abfangen und die Ausführung der Abfrage möglicherweise fortsetzen. Wenn Ausnahmen mittels Bubbling wieder an den Verbindungsthread übergeben werden können, ist es möglich, dass eine Abfrage nach dem Auslösen der Ausnahme weiterhin einige Elemente verarbeitet.

Wenn PLINQ auf die sequenzielle Ausführung zurückgreift und eine Ausnahme auftritt, kann die Ausnahme in einigen Fällen direkt weitergegeben werden und muss nicht mit einer <xref:System.AggregateException> umschlossen werden. <xref:System.Threading.ThreadAbortException>s werden darüber hinaus immer direkt weitergegeben.

> [!NOTE]
> Wenn „Nur eigenen Code“ aktiviert ist, unterbricht Visual Studio die Ausführung in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt. Dieser Fehler hat keine Auswirkungen. Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet. Um zu verhindern, dass Visual Studio die Ausführung beim ersten Fehler unterbricht, deaktivieren Sie unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen „Nur eigenen Code“.
>
> Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie die try-catch-Blöcke um den Code herum platziert werden, der die Abfrage ausführt, um alle ausgelösten <xref:System.AggregateException?displayProperty=nameWithType>s abzufangen.

[!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
[!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]

In diesem Beispiel kann die Abfrage nach dem Auslösen der Ausnahme nicht fortgesetzt werden. Zu dem Zeitpunkt, an dem Ihr Anwendungscode die Ausnahme abfängt, hat PLINQ die Abfrage bereits in allen Threads beendet.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie einen try-catch-Block in einem Delegaten platzieren, um zu ermöglichen, dass eine Ausnahme abgefangen und die Ausführung der Abfrage fortgesetzt wird.

[!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
[!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

- Um diese Beispiele zu kompilieren und auszuführen, kopieren Sie sie in das PLINQ Data Sample-Beispiel und rufen die Methode aus „Main“ auf.

## <a name="robust-programming"></a>Stabile Programmierung

Fangen Sie Ausnahmen nur ab, wenn Sie wissen, wie sie behandelt werden müssen, damit der Status Ihres Programms nicht beschädigt wird.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
