---
title: Durchführen linker äußerer Verknüpfungen (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie linke äußere Verknüpfungen mit LINQ in C# ausführen.
ms.date: 12/1/2016
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: 329fe9e17640931c5eb39b33b791a7a77a6f7b89
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506595"
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