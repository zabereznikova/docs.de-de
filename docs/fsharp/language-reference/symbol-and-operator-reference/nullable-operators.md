---
title: Operatoren, die NULL-Werte zulassen
description: 'Erfahren Sie mehr über die Operatoren, die NULL-Werte zulassen und in der Programmiersprache F # verfügbar sind.'
ms.date: 05/16/2016
ms.openlocfilehash: 9ac6afc2c3f4277ee6e93b1ccb3d21f892926b4b
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740366"
---
# <a name="nullable-operators"></a>Operatoren, die NULL-Werte zulassen

NULL-Werte zulassen sind binäre Arithmetik oder Vergleichs Operatoren, die auf einer oder beiden Seiten mit auf NULL festleg baren arithmetischen Typen funktionieren. Typen, die NULL-Werte zulassen, treten häufig auf, wenn Sie mit Daten aus Quellen wie Datenbanken arbeiten, die NULL-Werte anstelle von tatsächlichen Werten zulassen. Auf NULL festleg Bare Operatoren werden in Abfrage Ausdrücken häufig verwendet. Zusätzlich zu den Operatoren, die NULL-Werte zulassen, können Konvertierungs Operatoren zum Konvertieren zwischen Typen verwendet werden, die NULL-Werte zulassen. Es gibt auch Versionen bestimmter Abfrage Operatoren, die NULL-Werte zulassen.

## <a name="table-of-nullable-operators"></a>Tabelle mit NULL-Wert-Operatoren

In der folgenden Tabelle sind die NULL-Werte zulässig, die in der Sprache F # unterstützt werden

|Links lässt NULL-Werte zu|NULL-Werte auf der rechten Seite|Beide Seiten NULL-Werte zulassen|
|---|---|---|
|[? >=](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E=%20))|[>=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3E=?%20))|[? >=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E=?%20))|
|[? >](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E%20))|[>?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3E?%20))|[? >?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E?%20))|
|[? <=](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C=%20))|[<=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3C=?%20))|[? <=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C=?%20))|
|[? <](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C%20))|[<?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3C?%20))|[? <?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C?%20))|
|[?=](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?=%20))|[=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20=?%20))|[?=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?=?%20))|
|[? <>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C%3E%20))|[<>?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3C%3E?%20))|[? <>?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C%3E?%20))|
|[?+](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?+%20))|[+?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20+?%20))|[?+?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?+?%20))|
|[?-](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?-%20))|[-?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20-?%20))|[?-?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?-?%20))|
|[?*](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?*%20))|[*?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20*?%20))|[?*?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?*?%20))|
|[?/](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?/%20))|[/?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20/?%20))|[?/?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?/?%20))|
|[?%](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%%20))|[%?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%?%20))|[?%?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%?%20))|

## <a name="remarks"></a>Bemerkungen

Die Operatoren, die NULL-Werte zulassen, sind im [nullableoperators](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html) -Modul im Namespace [FSharp. Linq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq.html)enthalten. Der Typ für Werte zulässt-Daten ist `System.Nullable<'T>` .

In Abfrage Ausdrücken treten Werte zulässt-Typen auf, wenn Daten aus einer Datenquelle ausgewählt werden, die Nullen anstelle von Werten zulässt. In einer SQL Server-Datenbank verfügt jede Datenspalte in einer Tabelle über ein Attribut, das angibt, ob Nullen zulässig sind. Wenn NULL-Werten zulässig sind, können die Daten, die von der Datenbank zurückgegeben werden, NULL-Werten enthalten, die nicht durch einen primitiven Datentyp `int` , z. b., usw., dargestellt werden können `float` . Daher werden die Daten als `System.Nullable<int>` anstelle von `int` und anstelle von zurückgegeben `System.Nullable<float>` `float` . Der tatsächliche Wert kann mithilfe der-Eigenschaft von einem-Objekt abgerufen werden `System.Nullable<'T>` `Value` , und Sie können bestimmen, ob ein- `System.Nullable<'T>` Objekt über einen Wert verfügt, indem Sie die- `HasValue` Methode aufrufen. Eine weitere nützliche Methode ist die- `System.Nullable<'T>.GetValueOrDefault` Methode, die es Ihnen ermöglicht, den Wert oder einen Standardwert des entsprechenden Typs zu erhalten. Der Standardwert ist eine Form des Werts "Null", z. b. 0, 0,0 oder `false` .

Typen, die NULL-Werte zulassen, können in primitive Typen konvertiert werden, die keine NULL-Werte `int` zulassen `float` Es ist auch möglich, einen Typ, der NULL-Werte zulässt, mithilfe der Konvertierungs Operatoren für Werte zulässt-Typen in einen anderen Typ zu konvertieren Die entsprechenden Konvertierungs Operatoren haben den gleichen Namen wie die standardmäßigen, Sie befinden sich jedoch in einem separaten Modul, dem [Nullable](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullablemodule.html) -Modul im [FSharp. Linq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq.html) -Namespace. In der Regel öffnen Sie diesen Namespace bei der Arbeit mit Abfrage Ausdrücken. In diesem Fall können Sie die Konvertierungs Operatoren, die NULL-Werte zulassen, verwenden, indem Sie das Präfix dem `Nullable.` entsprechenden Konvertierungs Operator hinzufügen, wie im folgenden Code gezeigt.

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn $"%f{float nullableFloat}"
```

Die Ausgabe lautet `10.000000`.

Abfrage Operatoren für Datenfelder, die NULL-Werte zulassen, wie z `sumByNullable` . b., können auch in Abfrage Ausdrücken verwendet werden. Die Abfrage Operatoren für Typen, die keine NULL-Werte zulassen, sind nicht typkompatibel mit Typen, die NULL-Werte zulassen. Daher müssen Sie beim Arbeiten mit Datenwerten, die NULL-Werte zulassen, die Version des entsprechenden Abfrage Operators verwenden. Weitere Informationen finden Sie unter [Abfrage Ausdrücke](../query-expressions.md).

Das folgende Beispiel zeigt die Verwendung von NULL-Werten für Operatoren in einem F #-Abfrage Ausdruck. Die erste Abfrage zeigt, wie Sie eine Abfrage ohne einen Werte zulässt-Operator schreiben würden. die zweite Abfrage zeigt eine entsprechende Abfrage, die einen Operator verwendet, der NULL-Werte zulässt. Den vollständigen Kontext, einschließlich Informationen zum Einrichten der Datenbank für die Verwendung dieses Beispielcodes, finden Sie unter Exemplarische Vorgehensweise [: Zugreifen auf eine SQL-Datenbank mithilfe von typanbietern](../../tutorials/type-providers/index.md).

```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq

[<Generate>]
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">

let db = dbSchema.GetDataContext()

query {
    for row in db.Table2 do
    where (row.TestData1.HasValue && row.TestData1.Value > 2)
    select row
} |> Seq.iter (fun row -> printfn $"%d{row.TestData1.Value} %s{row.Name}")

query {
    for row in db.Table2 do
    // Use a nullable operator ?>
    where (row.TestData1 ?> 2)
    select row
} |> Seq.iter (fun row -> printfn "%d{row.TestData1.GetValueOrDefault()} %s{row.Name}")
```

## <a name="see-also"></a>Weitere Informationen

- [Typanbieter](../../tutorials/type-providers/index.md)
- [Abfrageausdrücke](../query-expressions.md)
