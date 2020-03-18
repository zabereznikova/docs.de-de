---
title: Typbeziehungen in LINQ-Abfragevorgängen (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- inferring type information [LINQ in C#]
- data sources [LINQ in C#], type relationships
- queries [LINQ in C#], type relationships
- relationships [LINQ in C#]
- type relationships [LINQ in C#]
- variable relationships [LINQ in C#]
- type information inferred [LINQ in C#]
- data transformations [LINQ in C#]
- LINQ [C#], type relationships
ms.assetid: 99118938-d47c-4d7e-bb22-2657a9f95268
ms.openlocfilehash: 41853e6858fae9e8d449aeed95a6a84f343d5874
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635612"
---
# <a name="type-relationships-in-linq-query-operations-c"></a>Typbeziehungen in LINQ-Abfragevorgängen (C#)
Um Abfragen effektiv erstellen zu können, ist es wichtig, dass Sie verstehen, wie die Variablentypen in einer vollständigen Abfrageoperation miteinander zusammenhängen. Wenn Sie diese Beziehungen verstehen, können Sie die LINQ-Beispiele und die Codebeispiele in der Dokumentation besser nachvollziehen. Weiterhin können Sie dann besser verstehen, was im Hintergrund abläuft, wenn Variablen implizit mithilfe von `var` typisiert werden.  
  
 LINQ-Abfrageoperationen sind in der Datenquelle, in der Abfrage selbst und in der Abfrageausführung stark typisiert. Die Variablentypen in der Abfrage müssen mit den Elementtypen in der Datenquelle und mit dem Typ der Iterationsvariablen in der `foreach`-Anweisung kompatibel sein. Diese starke Typisierung stellt sicher, dass Typfehler zur Kompilierzeit abgefangen werden, sodass sie korrigiert werden können, bevor die Benutzer sie ausführen.  
  
 Um diese Typbeziehungen zu veranschaulichen, wird in den meisten folgenden Beispielen explizite Typisierung für alle Variablen angewendet. Im letzten Beispiel wird gezeigt, wie diese Prinzipien auch dann gelten, wenn Sie die implizite Typisierung mithilfe von [var](../../../language-reference/keywords/var.md) verwenden.  
  
## <a name="queries-that-do-not-transform-the-source-data"></a>Abfragen, bei denen die Quelldaten nicht transformiert werden  
 Die folgende Abbildung zeigt eine LINQ to Objects-Abfrageoperation für Objekte, die keine Transformationen der Daten ausführt. Die Quelle enthält eine Sequenz von Zeichenfolgen, und die Abfrageausgabe ist ebenfalls eine Sequenz von Zeichenfolgen.  
  
 ![Diagramm, dass die Beziehung von Datentypen in einer LINQ-Abfrage zeigt.](./media/type-relationships-in-linq-query-operations/linq-query-data-type-relation.png)  
  
1. Das Typargument der Datenquelle bestimmt den Typ der Bereichsvariablen.  
  
2. Der Typ des Objekts, das ausgewählt ist, bestimmt den Typ der Abfragevariablen. In diesem Beispiel ist `name` eine Zeichenfolge. Daher ist die Abfragevariable ein `IEnumerable<string>`.  
  
3. Die Abfragevariable durchläuft in der `foreach`-Anweisung verschiedene Iterationen. Da die Abfragevariable eine Sequenz von Zeichenfolgen ist, ist die Iterationsvariable ebenfalls eine Zeichenfolge.  
  
## <a name="queries-that-transform-the-source-data"></a>Abfragen, bei denen die Quelldaten transformiert werden  
 Die folgende Abbildung zeigt eine [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]-Abfrageoperation, die eine einfache Datentransformation ausführt. Die Abfrage verwendet eine Sequenz von `Customer`-Objekten als Eingabe und wählt nur die `Name`-Eigenschaft im Ergebnis aus. Da `Name` eine Zeichenfolge ist, erzeugt die Abfrage eine Sequenz von Zeichenfolgen als Ausgabe.  
  
 ![Diagramm, das eine Abfrage zeigt, die den Datentyp transformiert.](./media/type-relationships-in-linq-query-operations/linq-query-transform-data-type.png)  
  
1. Das Typargument der Datenquelle bestimmt den Typ der Bereichsvariablen.  
  
2. Die `select`-Anweisung gibt die `Name`-Eigenschaft statt des vollständigen `Customer`-Objekts zurück. Da `Name` eine Zeichenfolge ist, lautet das Typargument von `custNameQuery` nicht `string`, sondern `Customer`.  
  
3. Da `custNameQuery` eine Sequenz von Zeichenfolgen ist, muss die Iterationsvariable der `foreach`-Schleife auch ein `string` sein.  
  
 Die folgende Abbildung zeigt eine etwas komplexere Transformation. Die `select`-Anweisung gibt einen anonymen Typ zurück, der nur zwei Member des ursprünglichen `Customer`-Objekts erfasst.  
  
 ![Diagramm, das eine komplexere Abfrage zeigt, die den Datentyp transformiert.](./media/type-relationships-in-linq-query-operations/linq-complex-query-transform-data-type.png)  
  
1. Das Typargument der Datenquelle ist immer der Typ der Bereichsvariablen in der Abfrage.  
  
2. Da die `select`-Anweisung einen anonymen Typ erzeugt, muss die Abfragevariable mithilfe von `var` implizit typisiert werden.  
  
3. Da der Typ der Abfragevariablen implizit ist, muss die Iterationsvariable in der `foreach`-Schleife auch implizit sein.  
  
## <a name="letting-the-compiler-infer-type-information"></a>Ableiten von Typinformationen durch den Compiler  
 Auch wenn Sie die Typbeziehungen einer Abfrageoperation grundsätzlich verstehen sollten, haben Sie die Option, den Compiler alle Arbeitsschritte ausführen zu lassen. Das [var](../../../language-reference/keywords/var.md)-Schlüsselwort kann in einer Abfrageoperation für jede lokale Variable verwendet werden. Die folgende Abbildung ähnelt Beispiel Nummer 2, das zuvor erläutert wurde. Allerdings stellt der Compiler den starken Typ für jede Variable in der Abfrageoperation bereit.  
  
 ![Diagramm, das den Typenfluss mit implizierter Typisierung zeigt.](./media/type-relationships-in-linq-query-operations/linq-type-flow-implicit-typing.png)  
  
 Weitere Informationen zu `var` finden Sie unter [Implizit typisierte lokale Variablen](../../classes-and-structs/implicitly-typed-local-variables.md).  
