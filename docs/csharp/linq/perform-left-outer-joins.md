---
title: Durchführen linker äußerer Verknüpfungen (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie linke äußere Verknüpfungen mit LINQ in C# ausführen.
ms.date: 12/01/2016
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: cc08a1c8670623a10d1e0bf10221d02037a8d7bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "61688578"
---
# <a name="perform-left-outer-joins"></a>Ausführen von Left Outer Joins

Ein Left Outer Join ist eine Verknüpfung, die jedes Element der ersten Auflistung zurückgibt, unabhängig davon, ob es entsprechende Elemente in der zweiten Auflistung gibt. Sie können LINQ verwenden, um eine linke äußere Verknüpfung auszuführen, indem die Methode <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> bei den Ergebnissen einer Gruppenverknüpfung aufgerufen wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die Methode <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> bei den Ergebnissen einer Gruppenverknüpfung verwendet wird, um eine linke äußere Verknüpfung auszuführen.

Der erste Schritt zum Erstellen eines Left Outer Join von zwei Auflistungen besteht darin, eine innere Verknüpfung durch Gruppenverknüpfung auszuführen. (Siehe [Ausführen innerer Verknüpfungen](perform-inner-joins.md) für eine Erläuterung dieses Vorgangs.) In diesem Beispiel wird die Liste der `Person`-Objekte mit der Liste der `Pet`-Objekte anhand eines `Person`-Objekts, das mit `Pet.Owner` übereinstimmt, von innen verknüpft.

Der zweite Schritt besteht darin, jedes Element der ersten (linken) Liste in den Ergebnissatz einzuschließen, selbst wenn das Element in der rechten Auflistung keine Übereinstimmungen hat. Dies wird durch den Aufruf von <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> für jede Sequenz von übereinstimmenden Elementen aus der Gruppenverknüpfung erreicht. In diesem Beispiel wird <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> für jede Sequenz von übereinstimmenden `Pet`-Objekten aufgerufen. Diese Methode gibt eine Auflistung zurück, die einen einzelnen Standardwert enthält, wenn die Sequenz von übereinstimmenden `Pet`-Objekten für jedes `Person`-Objekt leer ist, womit die Methode sicherstellt, dass jedes `Person`-Objekt in der Ergebnisauflistung dargestellt wird.

> [!NOTE]
> Der Standardwert für einen Verweistyp ist `null`; deshalb wird im Beispiel nach einem NULL-Verweis gesucht, bevor auf jedes Element jeder `Pet`-Auflistung zugegriffen wird.

[!code-csharp[CsLINQProgJoining#7](~/samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.Enumerable.Join%2A>
- <xref:System.Linq.Enumerable.GroupJoin%2A>
- [Ausführen innerer Verknüpfungen](perform-inner-joins.md)
- [Ausführen von Gruppenverknüpfungen](perform-grouped-joins.md)
- [Anonyme Typen](../programming-guide/classes-and-structs/anonymous-types.md)
