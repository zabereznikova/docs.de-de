---
title: C#-Funktionen mit LINQ-Unterstützung
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
ms.openlocfilehash: 9fc8adaa49d02f8b69c2db6e94a28b9fab36b3b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635794"
---
# <a name="c-features-that-support-linq"></a>C#-Funktionen mit LINQ-Unterstützung

Im folgenden Abschnitt werden neue Sprachkonstrukte, die in C# 3.0 eingeführt werden, vorgestellt. Obwohl diese neuen Funktionen zu einem gewissen Grad mit LINQ-Abfragen verwendet werden, sind sie nicht beschränkt auf LINQ und können in jedem Kontext, in dem Sie sie nützlich finden, verwendet werden.

## <a name="query-expressions"></a>Abfrageausdrücke

Abfrageausdrücke verwenden eine deklarative Syntax wie SQL oder XQuery, um eine Abfrage über IEnumerable-Sammlungen zu erstellen. Zur Kompilierzeit wird die Abfragesyntax in Methodenaufrufe an eine LINQ-Implementierung des Anbieters der Erweiterungsmethode des Standardabfrageoperators kompiliert. Applikationen steuern die Standardabfrageoperatoren, die sich durch Angabe des entsprechenden Namespace mit einer `using`-Anweisung innerhalb des Bereichs befinden. Der folgende Abfrageausdruck nimmt ein Array von Zeichenfolgen, gruppiert sie nach dem ersten Zeichen in der Zeichenfolge und sortiert die Gruppen.

```csharp
var query = from str in stringArray
            group str by str[0] into stringGroup
            orderby stringGroup.Key
            select stringGroup;
```

Weitere Informationen finden Sie unter [LINQ-Abfrageausdrücke](../../../linq/index.md).

## <a name="implicitly-typed-variables-var"></a>Implizit typisierte Variablen (var)

Anstatt beim Deklarieren und Initialisieren einer Variablen einen Typ explizit anzugeben, können Sie den [var](../../../language-reference/keywords/var.md)-Modifizierer verwenden, um den Compiler zum Ableiten und Zuweisen des Typs anzuweisen, wie hier gezeigt:

```csharp
var number = 5;
var name = "Virginia";
var query = from str in stringArray
            where str[0] == 'm'
            select str;
```

Variablen, die als `var` deklariert werden, sind ebenso stark typisiert wie Variablen, deren Typ Sie explizit angeben. Die Verwendung von `var` macht es möglich, anonyme Typen zu erstellen, dies ist jedoch nur für lokale Variablen möglich. Arrays können auch mit impliziter Typisierung deklariert werden.

Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../classes-and-structs/implicitly-typed-local-variables.md).

## <a name="object-and-collection-initializers"></a>Objekt- und Auflistungsinitialisierer

Objekt- und Auflistungsinitialisierer ermöglichen das Initialisieren von Objekten ohne expliziten Aufruf eines Konstruktors für das Objekt. Initialisierer werden in der Regel in Abfrageausdrücken verwendet, wenn sie die Quelldaten in einen neuen Datentyp projizieren. In einer Klasse namens `Customer` mit öffentlichen `Name`- und `Phone`-Eigenschaften können Objektinitialisierer wie im folgenden Code verwendet werden:

```csharp
var cust = new Customer { Name = "Mike", Phone = "555-1212" };
```

Wenn Sie mit der `Customer`-Klasse fortfahren, gehen Sie davon aus, dass eine Datenquelle namens `IncomingOrders` vorhanden ist, und dass für jede Bestellung mit einem großen `OrderSize`-Wert ein neues `Customer`-Element basierend auf dieser Bestellung erstellt werden soll. Eine LINQ-Abfrage kann auf dieser Datenquelle ausgeführt werden und verwendet die Objektinitialisierung, um eine Auflistung zu füllen:

```csharp
var newLargeOrderCustomers = from o in IncomingOrders
                            where o.OrderSize > 5
                            select new Customer { Name = o.Name, Phone = o.Phone };
```

Die Datenquelle kann mehr Eigenschaften im Hintergrund haben als die Klasse `Customer`, z.B. `OrderSize`, aber bei der Objektinitialisierung werden die von der Abfrage zurückgegebenen Daten in den gewünschten Datentyp umgewandelt. Wählen Sie die Daten aus, die für Ihre Klasse relevant sind. Daher verfügen wir jetzt über ein `IEnumerable`-Element, das mit den neuen gewünschten `Customer`-Informationen gefüllt ist. Das oben Geschilderte kann auch in der Methodensyntax von LINQ geschrieben werden:

```csharp
var newLargeOrderCustomers = IncomingOrders.Where(x => x.OrderSize > 5).Select(y => new Customer { Name = y.Name, Phone = y.Phone });
```

Weitere Informationen finden Sie unter:

- [Objekt- und Auflistungsinitialisierer](../../classes-and-structs/object-and-collection-initializers.md)

- [Abfrageausdruckssyntax für Standardabfrageoperatoren](./query-expression-syntax-for-standard-query-operators.md)

## <a name="anonymous-types"></a>Anonyme Typen

Ein anonymer Typ wird vom Compiler erstellt, und der Typname ist nur für den Compiler verfügbar. Anonyme Typen stellen eine bequeme Möglichkeit zum vorübergehenden Gruppieren einer Reihe von Eigenschaften in einem Abfrageergebnis bereit, ohne einen separaten benannten Typ definieren zu müssen. Anonyme Typen werden mit einem neuen Ausdruck und einem Objektinitialisierer initialisiert, wie hier gezeigt:

```csharp
select new {name = cust.Name, phone = cust.Phone};
```

Weitere Informationen finden Sie unter [Anonyme Klassentypen](../../classes-and-structs/anonymous-types.md).

## <a name="extension-methods"></a>Erweiterungsmethoden

Eine Erweiterungsmethode ist eine statische Methode, die einem Typ zugeordnet werden kann, sodass sie aufgerufen werden kann, als ob es sich um eine Instanzmethode für den Typ handeln würde. Diese Funktion ermöglicht es Ihnen, neue Methoden zu vorhandenen Typen „hinzuzufügen“, ohne sie tatsächlich zu ändern. Die Standardabfrageoperatoren sind eine Reihe von Erweiterungsmethoden, die LINQ-Abfragefunktionen für jeden Typ bieten, der <xref:System.Collections.Generic.IEnumerable%601> implementiert.

Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../classes-and-structs/extension-methods.md).

## <a name="lambda-expressions"></a>Lambda-Ausdrücke

Ein Lambdaausdruck ist eine Inlinefunktion, die den Operator => verwendet, um Eingabeparameter vom Funktionstext zu trennen, und die zur Kompilierzeit in einen Delegaten oder eine Ausdrucksbaumstruktur konvertiert werden kann. In der LINQ-Programmierung erhalten Sie Lambdaausdrücke, wenn Sie direkte Methodenaufrufe für die Standardabfrageoperatoren vornehmen.

Weitere Informationen finden Sie unter:

- [Anonyme Funktionen](../../statements-expressions-operators/anonymous-functions.md)

- [Lambda-Ausdrücke](../../statements-expressions-operators/lambda-expressions.md)

- [Ausdrucksbaumstrukturen (C#)](../expression-trees/index.md)

## <a name="see-also"></a>Weitere Informationen

- [Language-Integrated Query (LINQ) (C#)](./index.md)
