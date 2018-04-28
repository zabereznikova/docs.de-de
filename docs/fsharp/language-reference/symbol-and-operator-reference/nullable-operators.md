---
title: Operatoren, die NULL-Werte zulassen (F#)
description: Informationen Sie zu den Nullwert-Operatoren, die in der Programmiersprache f# verfügbar sind.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 37025e16768b949b51f6b9f0cff32e88da110ca8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="nullable-operators"></a>Operatoren, die NULL-Werte zulassen

Nullwert-Operatoren sind binäre arithmetischen oder Vergleichsoperation Operatoren, die auf einem oder beiden Seiten mit arithmetischen Typen zu arbeiten. Auf NULL festlegbare Typen treten häufig bei der Arbeit mit Daten aus Quellen wie z. B. Datenbanken, die NULL-Werte anstelle der tatsächlichen Werte zu ermöglichen. Nullwert-Operatoren werden häufig in Abfrageausdrücken verwendet. Zusätzlich zu den Nullwert-Operatoren für arithmetische und Vergleichsoperatoren können Konvertierungsoperatoren zum Konvertieren zwischen Typen mit Nullwert verwendet werden. Es gibt auch NULL-Werte zu Versionen von bestimmten Abfrageoperatoren.


## <a name="table-of-nullable-operators"></a>Tabelle mit Nullwert-Operatoren
Die folgende Tabelle enthält die Nullwert-Operatoren in der Programmiersprache f# unterstützt.

|Auf der linken Seite NULL-Werte zulässt|NULL-Werte zulässt, rechts|Beide Seiten NULL-Werte zulässt|
|---|---|---|
|[?>=](https://msdn.microsoft.com/library/94d29e32-a204-4f60-a527-6b0af86268f3)|[>=?](https://msdn.microsoft.com/library/0a255d8e-8cae-4160-ae61-243a5d96583f)|[?>=?](https://msdn.microsoft.com/library/3051a50f-d276-4c84-9d73-bf2efeddef94)|
|[?>](https://msdn.microsoft.com/library/62dc0021-1312-4ac3-be87-798b60b81bb6)|[>?](https://msdn.microsoft.com/library/0ad1284b-de48-4a04-83d8-b6f13c9c8936)|[?>?](https://msdn.microsoft.com/library/dc18b6fa-30c4-47b0-9057-794439378a05)|
|[?<=](https://msdn.microsoft.com/library/56fddf0a-e4ca-4891-a3be-fad1876be3b6)|[<=?](https://msdn.microsoft.com/library/02454a0f-30ca-4e77-ad84-ee7837461804)|[?<=?](https://msdn.microsoft.com/library/5c37c28c-0b57-4da5-be11-5a123f7e8ee4)|
|[?<](https://msdn.microsoft.com/library/b71897f0-6e29-4c58-b0a7-a5bfa6f88917)|[<?](https://msdn.microsoft.com/library/be9ea40f-a67f-4e98-8067-a14046752e8b)|[?<?](https://msdn.microsoft.com/library/6f1962c8-5605-468c-94ae-f379ae98e17d)|
|[?=](https://msdn.microsoft.com/library/5cdc8ff6-244b-49cf-9376-69ecf249fd7c)|[=?](https://msdn.microsoft.com/library/d2102894-6a51-475d-890a-735568c31f87)|[?=?](https://msdn.microsoft.com/library/5f793f29-1084-4570-b1c1-17c1b7ef764b)|
|[?<>](https://msdn.microsoft.com/library/3643a5a8-2ea5-4ad6-82c4-83927c3884a0)|[<>?](https://msdn.microsoft.com/library/3179aace-70c4-4911-9258-619592214976)|[?<>?](https://msdn.microsoft.com/library/5da813d8-ee75-45b8-9ef4-146dcb6d394d)|
|[?+](https://msdn.microsoft.com/library/2e8ddd05-b3f3-41b3-9d73-938d9e540f3f)|[+?](https://msdn.microsoft.com/library/74772ea8-f010-493e-bdb5-ba347f2fd4f1)|[?+?](https://msdn.microsoft.com/library/57f28137-0f42-43d2-92af-cad8c6c9d05f)|
|[?-](https://msdn.microsoft.com/library/f237a7a6-89f2-48b2-a2fe-f0b98a2bedc2)|[-?](https://msdn.microsoft.com/library/4a345c07-314a-48f1-b557-ce072583589c)|[?-?](https://msdn.microsoft.com/library/e0024142-1d2a-4607-a39c-1eb1e86fa25a)|
|[?*](https://msdn.microsoft.com/library/519da708-5ad6-4075-9d74-d00441cd6078)|[*?](https://msdn.microsoft.com/library/04c47870-de7b-480d-98a0-f47593b4ffac)|[?*?](https://msdn.microsoft.com/library/e57057ba-9c3a-40ec-8401-150c2b25f75b)|
|[?/](https://msdn.microsoft.com/library/add02a42-f556-40a7-a168-fbf2053322e3)|[/?](https://msdn.microsoft.com/library/1de07646-3778-476d-8c61-5d37495d463c)|[?/?](https://msdn.microsoft.com/library/b17be0ac-bf98-4590-861d-a4dd6c6fa535)|
|[?%](https://msdn.microsoft.com/library/44297bba-1bd9-4ed2-a848-f1e1e598db87)|[%?](https://msdn.microsoft.com/library/a4c178e5-eec4-42e8-847f-90b24fc609fe)|[?%?](https://msdn.microsoft.com/library/dd555f20-1be3-4b8d-81f1-bf1921e62fda)|

## <a name="remarks"></a>Hinweise
Nullwert-Operatoren sind in enthalten die [NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007) -Modul im Namespace [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d). Der Typ für NULL-Werte zulassen Daten ist `System.Nullable<'T>`.

In Abfrageausdrücken entstehen auf NULL festlegbare Typen beim Auswählen von Daten aus einer Datenquelle, die NULL-Werte anstelle von Werten zulässt. In einer SQL Server-Datenbank hat jeder Spalte in einer Tabelle ein Attribut, das angibt, ob NULL-Werte zulässig sind. Wenn NULL-Werte zulässig sind, können aus der Datenbank zurückgegebenen Daten enthalten NULL-Werte, die z. B. durch einen primitiven Datentyp dargestellt werden können `int`, `float`und so weiter. Aus diesem Grund wird die Daten zurückgegeben, als eine `System.Nullable<int>` anstelle von `int`, und `System.Nullable<float>` anstelle von `float`. Aus der tatsächliche Wert abgerufen werden kann ein `System.Nullable<'T>` Objekt mithilfe der `Value` -Eigenschaft, und Sie können feststellen, ob eine `System.Nullable<'T>` Objekt hat den Wert durch Aufrufen der `HasValue` Methode. Eine andere nützliche Methode ist die `System.Nullable<'T>.GetValueOrDefault` -Methode, die Ihnen ermöglicht, den Wert oder einen Standardwert des entsprechenden Typs abzurufen. Der Standardwert ist eine Form von "NULL" Wert, z. B. 0, 0,0 ist, oder `false`.

Auf NULL festlegbare Typen konvertiert werden, NULL-primitive Typen, die mit den üblichen Konvertierungsoperatoren wie `int` oder `float`. Es ist auch möglich, die aus einem nullable-Typ zu einem anderen NULL-Werte zu konvertieren, mithilfe der Konvertierungsoperatoren für Typen mit Nullwert. Die entsprechende Konvertierung-Operatoren weisen den gleichen Namen wie die Standardtastenkombinationen, aber sie sind in einem separaten Modul die [Nullable](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e) Modul in die [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d) Namespace. In der Regel öffnen Sie diesen Namespace, bei der Verwendung von Abfrageausdrücken. In diesem Fall können Sie die NULL-Werte zulassen Konvertierungsoperatoren verwenden, indem Sie das Präfix `Nullable.` an den entsprechenden Konvertierungsoperator, wie im folgenden Code gezeigt.

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn "%f" (float nullableFloat)
```

Die Ausgabe lautet `10.000000`.

Abfrageoperatoren Datenfelder NULL-Werte zulässt, wie z. B. `sumByNullable`, auch für die Verwendung in Abfrageausdrücken vorhanden sein. Die Abfrageoperatoren für NULL-Typen sind nicht typkompatibel mit auf NULL festlegbaren Typen, damit Sie die NULL-Werte zu Version von den entsprechenden Abfrage-Operator verwenden müssen, bei der Arbeit mit NULL-Werte zu den Datenwerten. Weitere Informationen finden Sie unter [Abfrageausdrücke](../query-expressions.md).

Das folgende Beispiel zeigt die Verwendung von Nullwert-Operatoren in einer f#-Abfrageausdruck. Die erste Abfrage veranschaulicht, wie Sie eine Abfrage ohne NULL-Werte zulassen Operator schreiben würden; die zweite Abfrage zeigt eine entsprechende Abfrage, die einen NULL-Operator verwendet. Die gesamten Kontexts, einschließlich Informationen zum Einrichten der Datenbank mit diesem Beispielcode finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf eine SQL-Datenbank von mithilfe von Typanbietern](../../tutorials/type-providers/accessing-a-sql-database.md).

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
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
    for row in db.Table2 do
    // Use a nullable operator ?>
    where (row.TestData1 ?> 2)
    select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="see-also"></a>Siehe auch

[Typanbieter](../../tutorials/type-providers/index.md)

[Abfrageausdrücke](../query-expressions.md)
