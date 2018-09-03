---
title: Abfragen einer Sammlung von Objekten (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie Abfragesammlungen mit LINQ in C# erstellen.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 7bc59e7009f9ae8d8f66c24e9519d9100404c9c4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480919"
---
# <a name="query-a-collection-of-objects"></a>Abfrage einer Auflistung von Objekten

In diesem Beispiel wird veranschaulicht, wie eine einfache Abfrage für eine Liste von `Student`-Objekten ausgeführt wird. Jedes `Student`-Objekt enthält grundlegende Informationen über den Studenten und eine Liste, die die Ergebnisse des Studenten aus vier Prüfungen darstellt.  
  
Diese Anwendung dient als Rahmen für viele andere Beispiele in diesem Bereich, bei denen dieselbe `students`-Datenquelle verwendet wird.  
  
## <a name="example"></a>Beispiel

Die folgende Abfrage gibt die Studenten zurück, die ein Ergebnis von 90 oder höher in ihrer ersten Prüfung erzielt haben.  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
Diese Abfrage wurde absichtlich einfach gehalten, damit Sie damit experimentieren können. Sie können z.B. weitere Bedingungen in der `where`-Klausel ausprobieren oder eine `orderby`-Klausel verwenden, um die Ergebnisse zu sortieren.  
  
## <a name="see-also"></a>Siehe auch

- [Language-Integrated Query (LINQ)](index.md)  
- [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md)