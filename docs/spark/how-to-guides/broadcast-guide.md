---
title: Verwenden von Broadcastvariablen in .NET für Apache Spark
description: Erfahren Sie, wie Sie Broadcastvariablen in .NET für Apache Spark-Anwendung verwenden.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 55a52754439020bd2a925aa3e987fb4ad99c9c3d
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224004"
---
# <a name="use-broadcast-variables-in-net-for-apache-spark"></a>Verwenden von Broadcastvariablen in .NET für Apache Spark

In diesem Artikel erfahren Sie, wie Sie Broadcastvariablen in .NET für Apache Spark verwenden. [Broadcastvariablen in Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) sind Mechanismen für die Freigabe von Variablen über Executors hinweg, die schreibgeschützt sein sollen. Mithilfe von Broadcastvariablen können Sie eine schreibgeschützte Variable auf jedem Computer zwischenspeichern, anstatt eine Kopie davon mit Tasks zu versenden. Sie können Broadcastvariablen verwenden, um jeden Knoten effizient mit einer Kopie eines großen Eingabedatasets zu versehen.

Da Daten nur einmal gesendet werden, haben Broadcastvariablen Vorteile gegenüber lokalen Variablen, die mit jedem Task an die Executors ausgeliefert werden. Weitere Informationen zu Broadcastvariablen und deren Verwendung finden Sie in der [offiziellen Dokumentation zu Broadcastvariablen](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables).

## <a name="create-broadcast-variables"></a>Erstellen von Broadcastvariablen

Rufen Sie `SparkContext.Broadcast(v)` für jede Variable `v` auf, um eine Broadcastvariable zu erstellen. Die Broadcastvariable ist ein Wrapper um die Variable `v`, und auf ihren Wert kann durch Aufrufen der `Value()`-Methode zugegriffen werden.

Im folgenden Codeausschnitt wird eine Zeichenfolgenvariable, `v`, erstellt, und eine Broadcastvariable (`bv`) wird erstellt, wenn `SparkContext.Broadcast(v)` aufgerufen wird. Achten Sie darauf, dass der Typparameter für `Broadcast` („string“) mit dem Typ der Variable übereinstimmt, die übertragen wird. Die benutzerdefinierte Funktion gibt den Wert `bv` zurück.

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

Func<Column, Column> udf = Udf<string, string>(
    str => $"{str}: {bv.Value()}");
```

## <a name="delete-broadcast-variables"></a>Löschen von Broadcastvariablen

Die Broadcastvariable kann durch Aufrufen der `Destroy()`-Methode aus allen Executoren gelöscht werden.

```csharp
bv.Destroy();
```

`Destroy()` löscht alle Daten und Metadaten, die mit der Broadcastvariable verknüpft sind, und sollte mit Vorsicht verwendet werden. Sobald eine Broadcastvariable zerstört wurde, kann sie nicht mehr verwendet werden.

## <a name="limit-broadcast-variable-scope-in-udfs"></a>Einschränken des Bereichs von Broadcastvariablen in benutzerdefinierten Funktionen

Wenn Sie Broadcastvariablen in benutzerdefinierten Funktionen (User-Defined Functions, UDFs) verwenden, müssen Sie den Bereich der Variable auf die UDF beschränken, die auf die Variable verweist. Im [Leitfaden zum Verwenden von UDFs](udf-guide.md) wird dieses Phänomen ausführlich beschrieben. Der Bereich ist besonders wichtig, wenn Sie `Destroy()` in der Broadcastvariable aufrufen.

Wenn die Broadcastvariable, die zerstört wurde, für andere UDFs sichtbar wird bzw. diese auf sie zugreifen können, wird sie von allen UDFs für die Serialisierung übernommen, auch wenn sie nicht von ihnen referenziert wird. .NET für Apache Spark kann die zerstörte Broadcastvariable nicht serialisieren, was zu einem Fehler führt. Im folgenden Codeausschnitt wird dieser Fehler veranschaulicht:

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

// Using the broadcast variable in a UDF:
Func<Column, Column> udf1 = Udf<string, string>(
    str => $"{str}: {bv.Value()}");

// Destroying bv
bv.Destroy();

// Calling udf1 after destroying bv throws the following expected exception:
// org.apache.spark.SparkException: Attempted to use Broadcast(0) after it was destroyed
df.Select(udf1(df["_1"])).Show();

// Different UDF udf2 that is not referencing bv
Func<Column, Column> udf2 = Udf<string, string>(
    str => $"{str}: not referencing broadcast variable");

// Calling udf2 throws the following (unexpected) exception:
// [Error] [JvmBridge] org.apache.spark.SparkException: Task not serializable
df.Select(udf2(df["_1"])).Show();
```

Im folgenden Codeausschnitt wird erläutert, wie sichergestellt wird, dass sich die Zerstörung von `bv` nicht auf `udf2` aufgrund eines unerwarteten Serialisierungsverhaltens auswirkt:

```csharp
string v = "Variable to be broadcasted";
// Restricting the visibility of bv to only the UDF referencing it
{
    Broadcast<string> bv = SparkContext.Broadcast(v);

    // Using the broadcast variable in a UDF:
    Func<Column, Column> udf1 = Udf<string, string>(
        str => $"{str}: {bv.Value()}");

    // Destroying bv
    bv.Destroy();
}

// Different UDF udf2 that is not referencing bv
Func<Column, Column> udf2 = Udf<string, string>(
    str => $"{str}: not referencing broadcast variable");

// Calling udf2 works fine as expected
df.Select(udf2(df["_1"])).Show();
```

## <a name="next-steps"></a>Nächste Schritte

* [Erste Schritte mit .NET für Apache Spark](../tutorials/get-started.md)
* [Debuggen einer .NET für Apache Spark-Anwendung unter Windows](debug.md)
* [Bereitstellen des .NET für Apache Spark-Workers und für benutzerdefinierte Funktionsbinärdateien](deploy-worker-udf-binaries.md)
