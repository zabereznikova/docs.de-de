---
title: Ausführen von benutzerdefinierten Verknüpfungsoperationen
description: So führen Sie benutzerdefinierte Verknüpfungsoperationen aus.
ms.date: 12/1/2016
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: df80f4382ad5fa96fcdc41b338cbb53a3d8e6cb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="perform-custom-join-operations"></a>Ausführen von benutzerdefinierten Verknüpfungsoperationen

In diesem Beispiel wird gezeigt, wie Verknüpfungsoperationen ausgeführt werden, die nicht mit der `join`-Klausel möglich sind. In einem Abfrageausdruck ist die `join`-Klausel auf Gleichheitsverknüpfungen, den bei weitem häufigsten Typ einer Verknüpfungsoperation, beschränkt und dafür optimiert. Wenn eine Gleichheitsverknüpfung ausgeführt wird, erhalten Sie die beste Leistung wahrscheinlich immer mit der `join`-Klausel.  
  
 Die `join`-Klausel kann jedoch nicht in den folgenden Fällen verwendet werden:  
  
-   Wenn die Verknüpfung auf einem Ausdruck der Ungleichheit basiert (eine Ungleichheitsverknüpfung)  
  
-   Wenn die Verknüpfung auf mehr als einem Ausdruck der Gleich- oder Ungleichheit basiert  
  
-   Wenn Sie eine temporäre Bereichsvariable für die rechte (innere) Sequenz vor der Verknüpfungsoperation einführen müssen.  
  
 Sie können zum Ausführen von Verknüpfungen, die keine Gleichheitsverknüpfungen sind, mehrere `from`-Klauseln verwenden, um jede Datenquelle einzeln einzuführen. Sie wenden anschließend einen Prädikatsausdruck in einer `where`-Klausel auf die Bereichsvariable für jede Quelle an. Der Ausdruck kann auch die Form eines Methodenaufrufs annehmen.  
  
> [!NOTE]
>  Verwechseln Sie diese Art der benutzerdefinierten Verknüpfungsoperationen nicht mit der Verwendung mehrerer `from`-Klauseln, um auf innere Auflistungen zuzugreifen. Weitere Informationen finden Sie unter [Join-Klausel](../language-reference/keywords/join-clause.md).  
  
## <a name="example"></a>Beispiel  
 Die erste Methode im folgenden Beispiel zeigt eine einfache Kreuzverknüpfung. Kreuzverknüpfungen müssen mit Bedacht verwendet werden, da sie einen sehr großen Ergebnissatz erzeugen können. Sie können jedoch in manchen Szenarios nützlich sein, um Quellsequenzen zu erstellen, mit denen zusätzliche Abfragen ausgeführt werden.  
  
 Die zweite Methode erzeugt eine Sequenz aller Produkte, deren Kategorie-ID in der Kategorieliste auf der linken Seite aufgeführt ist. Beachten Sie, dass Sie mit der Verwendung der `let`-Klausel und der `Contains`-Methode ein temporäres Array erstellen. Es ist auch möglich, das Array vor der Abfrage zu erstellen und die erste `from`-Klausel zu löschen.  
  
 [!code-csharp[csProgGuideLINQ#64](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel muss die Abfrage zwei Sequenzen anhand übereinstimmender Schlüssel verknüpfen, die bei der inneren (rechten) Sequenz nicht vor der eigentlichen Join-Klausel abgerufen werden können. Wenn diese Verknüpfung mit einer `join`-Klausel ausgeführt werden würde, müsste anschließend die `Split`-Methode für jedes Element aufgerufen werden. Mit der Verwendung von mehreren `from`-Klauseln kann die Abfrage den Mehraufwand des wiederholten Methodenaufrufs vermeiden. Da `join` jedoch optimiert ist, könnte es in diesem Sonderfall trotzdem schneller sein als mehrere `from`-Klauseln zu verwenden. Die Ergebnisse variieren hauptsächlich nach Aufwand des Methodenaufrufs.  
  
 [!code-csharp[csProgGuideLINQ#13](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ-Abfrageausdrücke](index.md)  
 [join-Klausel](../language-reference/keywords/join-clause.md)  
 [Sortieren der Ergebnisse einer Join-Klausel](order-the-results-of-a-join-clause.md)
