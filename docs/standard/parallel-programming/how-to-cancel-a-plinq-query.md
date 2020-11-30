---
title: 'Vorgehensweise: Abbrechen einer PLINQ-Abfrage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
ms.openlocfilehash: f8ca723ca3b9b9428c95651ebe2fa7d92e48ebbb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713287"
---
# <a name="how-to-cancel-a-plinq-query"></a>Vorgehensweise: Abbrechen einer PLINQ-Abfrage

In den folgenden Beispielen werden zwei Möglichkeiten zum Ändern einer PLINQ-Abfrage veranschaulicht. Das erste Beispiel zeigt, wie eine Abfrage abgebrochen wird, die größtenteils aus Datendurchlauf besteht. Im zweiten Beispiel wird gezeigt, wie eine Abfrage abgebrochen wird, die eine rechenintensive Benutzerfunktion enthält.

> [!NOTE]
> Wenn „Nur eigenen Code“ aktiviert ist, unterbricht Visual Studio die Ausführung in der Zeile, die die Ausnahme auslöst, und zeigt eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme an. Dieser Fehler hat keine Auswirkungen. Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet. Um zu verhindern, dass Visual Studio beim ersten Fehler abbricht, deaktivieren Sie einfach unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen „Nur eigenen Code“.
>
> Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](understanding-speedup-in-plinq.md).

## <a name="example"></a>Beispiel

[!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
[!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]

Das PLINQ-Framework setzt keine einzelne <xref:System.OperationCanceledException> in eine <xref:System.AggregateException?displayProperty=nameWithType> zurück; die <xref:System.OperationCanceledException> muss in einem separaten Catch-Block behandelt werden. Wenn mindestens ein Benutzerdelegat eine OperationCanceledException(externalCT) (mithilfe einer externen <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) auslöst, aber keine weitere Ausnahme, und die Abfrage als `AsParallel().WithCancellation(externalCT)` definiert wurde, dann gibt PLINQ eine einzelne <xref:System.OperationCanceledException>(externalCT) anstelle einer <xref:System.AggregateException?displayProperty=nameWithType> aus. Löst jedoch ein Benutzerdelegat eine <xref:System.OperationCanceledException> und ein anderer Delegat einen anderen Ausnahmetyp aus, werden beide Ausnahmen in eine <xref:System.AggregateException> zurückgesetzt.

Der allgemeine Leitfaden zum Abbruch lautet wie folgt:

1. Wenn Sie einen Benutzerdelegatenabbruch ausführen, sollten Sie PLINQ über das externe <xref:System.Threading.CancellationToken> informieren und eine <xref:System.OperationCanceledException>(externalCT) auslösen.

2. Wenn ein Abbruch auftritt und keine anderen Ausnahmen ausgelöst werden, sollten Sie eine <xref:System.OperationCanceledException> anstelle einer <xref:System.AggregateException> behandeln.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie einen Abbruch behandeln müssen, wenn der Benutzercode eine rechenintensive Funktion enthält.

[!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
[!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]

Wenn Sie den Abbruch im Benutzercode behandeln, müssen Sie <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> nicht in der Abfragedefinition verwenden. Allerdings sollten Sie <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> verwenden, da <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> keine Auswirkung auf die Abfrageleistung hat und die Behandlung des Abbruchs durch Abfrageoperatoren und Ihren Benutzercode ermöglicht.

Um die Reaktionsfähigkeit des Systems zu gewährleisten, sollten Sie etwa einmal pro Millisekunde prüfen, ob ein Abbruch vorliegt; allerdings ist jeder Zeitraum von bis zu 10 Millisekunden akzeptabel. Diese Häufigkeit sollte sich nicht negativ auf die Leistung Ihres Codes auswirken.

Wenn ein Enumerator verworfen wird, z. B. wenn Code aus einer foreach-Schleife („For Each“ in Visual Basic) ausbricht, die eine Iteration über Abfrageergebnisse durchführt, wird die Abfrage abgebrochen, jedoch keine Ausnahme ausgelöst.

## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](introduction-to-plinq.md)
- [Abbruch in verwalteten Threads](../threading/cancellation-in-managed-threads.md)
