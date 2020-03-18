---
title: Abfragen einer Sammlung von Objekten (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie Abfragesammlungen mit LINQ in C# erstellen.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 9b2f5dd09c540800e9a2498d48883357f58c0116
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659812"
---
# <a name="query-a-collection-of-objects"></a>Abfrage einer Auflistung von Objekten

In diesem Beispiel wird veranschaulicht, wie eine einfache Abfrage für eine Liste von `Student`-Objekten ausgeführt wird. Jedes `Student`-Objekt enthält grundlegende Informationen über den Studenten und eine Liste, die die Ergebnisse des Studenten aus vier Prüfungen darstellt.  
  
Diese Anwendung dient als Rahmen für viele andere Beispiele in diesem Bereich, bei denen dieselbe `students`-Datenquelle verwendet wird.  
  
## <a name="example"></a>Beispiel

Die folgende Abfrage gibt die Studenten zurück, die ein Ergebnis von 90 oder höher in ihrer ersten Prüfung erzielt haben.  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
Diese Abfrage wurde absichtlich einfach gehalten, damit Sie damit experimentieren können. Sie können z.B. weitere Bedingungen in der `where`-Klausel ausprobieren oder eine `orderby`-Klausel verwenden, um die Ergebnisse zu sortieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Language-Integrated Query (LINQ)](index.md)
- [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md)
