---
title: Behandeln von Ausnahmen in Abfrageausdrücken (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie Ausnahmen in LINQ-Abfrageausdrücken in C# verarbeiten.
ms.date: 12/1/2016
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: 5ad98565a74a96ac18829eb87f13eb398aa72967
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528472"
---
# <a name="handle-exceptions-in-query-expressions"></a>Behandeln von Ausnahmen in Abfrageausdrücken

Es ist möglich, jede Methode im Kontext eines Abfrageausdrucks aufzurufen. Es empfiehlt sich jedoch, Methoden in einem Abfrageausdruck aufzurufen, die Nebeneffekte wie die Änderung des Inhalts der Datenquelle oder das Auslösen einer Ausnahme erzeugen können. In diesem Beispiel wird veranschaulicht, wie Sie es beim Aufrufen von Methoden in Abfrageausdrücken vermeiden, Ausnahmen auszulösen, ohne gegen die allgemeinen .NET-Richtlinien für die Behandlung von Ausnahmen zu verstoßen. Gemäß dieser Richtlinien dürfen Sie eine bestimmte Ausnahme abfangen, wenn Sie wissen, warum sie in einem bestimmten Kontext ausgelöst wird. Weitere Informationen finden Sie unter [Best Practices für Ausnahmen](../../standard/exceptions/best-practices-for-exceptions.md).

Im letzten Beispiel wird der Umgang mit diesen Fällen veranschaulicht, wenn Sie während der Ausführung einer Abfrage eine Ausnahme auslösen müssen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie Sie den Ausnahmebehandlungscode aus einem Abfrageausdruck verschieben. Dies ist nur möglich, wenn die Methode von keiner für die Abfrage lokalen Variablen abhängig ist.

[!code-csharp[csProgGuideLINQ#10](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]

## <a name="example"></a>Beispiel

In einigen Fällen ist die möglicherweise beste Antwort auf eine Ausnahme, die von einer Abfrage ausgelöst wird, die Ausführung der Abfrage sofort zu beenden. Im folgenden Beispiel wird der Umgang mit Ausnahmen veranschaulicht, die innerhalb eines Abfragetexts ausgelöst werden können. Angenommen dass `SomeMethodThatMightThrow` zu einer Ausnahme führen kann, derentwegen die Ausführung der Abfrage beenden werden muss.

Beachten Sie, dass der `try`-Block die `foreach`-Schleife und nicht die Abfrage selbst enthält. Das liegt daran, dass die `foreach`-Schleife der Punkt ist, an dem die Abfrage tatsächlich ausgeführt wird. Weitere Informationen finden Sie unter [Introduction to LINQ queries (Einführung in LINQ-Abfragen)](../programming-guide/concepts/linq/introduction-to-linq-queries.md).

[!code-csharp[csProgGuideLINQ#12](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]

## <a name="see-also"></a>Siehe auch

- [Language-Integrated Query (LINQ)](index.md)  
