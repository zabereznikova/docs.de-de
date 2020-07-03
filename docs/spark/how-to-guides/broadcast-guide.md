---
title: Verwenden von Broadcastvariablen in .NET für Apache Spark
description: Erfahren Sie, wie Sie Broadcastvariablen in .NET für Apache Spark-Anwendung verwenden.
ms.date: 06/11/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 391e32cda14a9b3186ac96800351ddcb39a3d359
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105618"
---
# <a name="use-broadcast-variables-in-net-for-apache-spark"></a><span data-ttu-id="9f5d5-103">Verwenden von Broadcastvariablen in .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="9f5d5-103">Use broadcast variables in .NET for Apache Spark</span></span>

<span data-ttu-id="9f5d5-104">In diesem Artikel erfahren Sie, wie Sie Broadcastvariablen in .NET für Apache Spark verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-104">In this article, you learn how to use broadcast variables in .NET for Apache Spark.</span></span> <span data-ttu-id="9f5d5-105">[Broadcastvariablen in Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) sind Mechanismen für die Freigabe von Variablen über Executors hinweg, die schreibgeschützt sein sollen.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-105">[Broadcast variables in Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) are mechanisms for sharing variables across executors that are meant to be read-only.</span></span> <span data-ttu-id="9f5d5-106">Mithilfe von Broadcastvariablen können Sie eine schreibgeschützte Variable auf jedem Computer zwischenspeichern, anstatt eine Kopie davon mit Tasks zu versenden.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-106">Broadcast variables allow you to keep a read-only variable cached on each machine rather than shipping a copy of it with tasks.</span></span> <span data-ttu-id="9f5d5-107">Sie können Broadcastvariablen verwenden, um jeden Knoten effizient mit einer Kopie eines großen Eingabedatasets zu versehen.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-107">You can use broadcast variables to give every node a copy of a large input dataset in an efficient manner.</span></span>

<span data-ttu-id="9f5d5-108">Da Daten nur einmal gesendet werden, haben Broadcastvariablen Vorteile gegenüber lokalen Variablen, die mit jedem Task an die Executors ausgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-108">Because the data is sent only once, broadcast variables have performance benefits when compared to local variables that are shipped to the executors with each task.</span></span> <span data-ttu-id="9f5d5-109">Weitere Informationen zu Broadcastvariablen und deren Verwendung finden Sie in der [offiziellen Dokumentation zu Broadcastvariablen](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables).</span><span class="sxs-lookup"><span data-stu-id="9f5d5-109">Refer to the [official broadcast variable documentation](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) to get a deeper understanding of broadcast variables and why they are used.</span></span>

## <a name="create-broadcast-variables"></a><span data-ttu-id="9f5d5-110">Erstellen von Broadcastvariablen</span><span class="sxs-lookup"><span data-stu-id="9f5d5-110">Create broadcast variables</span></span>

<span data-ttu-id="9f5d5-111">Rufen Sie `SparkContext.Broadcast(v)` für jede Variable `v` auf, um eine Broadcastvariable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-111">To create a broadcast variable, call `SparkContext.Broadcast(v)` for any variable `v`.</span></span> <span data-ttu-id="9f5d5-112">Die Broadcastvariable ist ein Wrapper um die Variable `v`, und auf ihren Wert kann durch Aufrufen der `Value()`-Methode zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-112">The broadcast variable is a wrapper around the variable `v`, and its value can be accessed by calling the `Value()` method.</span></span>

<span data-ttu-id="9f5d5-113">Im folgenden Codeausschnitt wird eine Zeichenfolgenvariable, `v`, erstellt, und eine Broadcastvariable (`bv`) wird erstellt, wenn `SparkContext.Broadcast(v)` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-113">In the following code snippet, a string variable `v` is created, and a broadcast variable `bv` is created when `SparkContext.Broadcast(v)`is called.</span></span> <span data-ttu-id="9f5d5-114">Achten Sie darauf, dass der Typparameter für `Broadcast` („string“) mit dem Typ der Variable übereinstimmt, die übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-114">Notice the type parameter for `Broadcast`, string, matches the type of the variable being broadcasted.</span></span> <span data-ttu-id="9f5d5-115">Die benutzerdefinierte Funktion gibt den Wert `bv` zurück.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-115">The user-defined function (UDF) returns the value of `bv`.</span></span>

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

Func<Column, Column> udf = Udf<string, string>(
    str => $"{str}: {bv.Value()}");
```

## <a name="delete-broadcast-variables"></a><span data-ttu-id="9f5d5-116">Löschen von Broadcastvariablen</span><span class="sxs-lookup"><span data-stu-id="9f5d5-116">Delete broadcast variables</span></span>

<span data-ttu-id="9f5d5-117">Die Broadcastvariable kann durch Aufrufen der `Destroy()`-Methode aus allen Executoren gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-117">The broadcast variable can be deleted from all executors by calling the `Destroy()` method.</span></span>

```csharp
bv.Destroy();
```

<span data-ttu-id="9f5d5-118">`Destroy()` löscht alle Daten und Metadaten, die mit der Broadcastvariable verknüpft sind, und sollte mit Vorsicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-118">`Destroy()` deletes all data and metadata related to the broadcast variable and should be used with caution.</span></span> <span data-ttu-id="9f5d5-119">Sobald eine Broadcastvariable zerstört wurde, kann sie nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-119">Once a broadcast variable is destroyed, it can't be used again.</span></span>

## <a name="limit-broadcast-variable-scope-in-udfs"></a><span data-ttu-id="9f5d5-120">Einschränken des Bereichs von Broadcastvariablen in benutzerdefinierten Funktionen</span><span class="sxs-lookup"><span data-stu-id="9f5d5-120">Limit broadcast variable scope in UDFs</span></span>

<span data-ttu-id="9f5d5-121">Wenn Sie Broadcastvariablen in benutzerdefinierten Funktionen (User-Defined Functions, UDFs) verwenden, müssen Sie den Bereich der Variable auf die UDF beschränken, die auf die Variable verweist.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-121">When you use broadcast variables in UDFs, you need to limit the scope of the variable to only the UDF that is referencing the variable.</span></span> <span data-ttu-id="9f5d5-122">Im [Leitfaden zum Verwenden von UDFs](udf-guide.md) wird dieses Phänomen ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-122">The [guide to using UDFs](udf-guide.md) describes this phenomenon in detail.</span></span> <span data-ttu-id="9f5d5-123">Der Bereich ist besonders wichtig, wenn Sie `Destroy()` in der Broadcastvariable aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-123">Scope is especially crucial when you call `Destroy()` on the broadcast variable.</span></span>

<span data-ttu-id="9f5d5-124">Wenn die Broadcastvariable, die zerstört wurde, für andere UDFs sichtbar wird bzw. diese auf sie zugreifen können, wird sie von allen UDFs für die Serialisierung übernommen, auch wenn sie nicht von ihnen referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-124">If the broadcast variable that has been destroyed is visible to or accessible from other UDFs, it gets picked up for serialization by all of the UDFs, even if it is not being referenced by them.</span></span> <span data-ttu-id="9f5d5-125">.NET für Apache Spark kann die zerstörte Broadcastvariable nicht serialisieren, was zu einem Fehler führt.</span><span class="sxs-lookup"><span data-stu-id="9f5d5-125">.NET for Apache Spark is unable to serialize the destroyed broadcast variable, which results in an error.</span></span> <span data-ttu-id="9f5d5-126">Im folgenden Codeausschnitt wird dieser Fehler veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="9f5d5-126">The following code snippet demonstrates this error:</span></span>

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

<span data-ttu-id="9f5d5-127">Im folgenden Codeausschnitt wird erläutert, wie sichergestellt wird, dass sich die Zerstörung von `bv` nicht auf `udf2` aufgrund eines unerwarteten Serialisierungsverhaltens auswirkt:</span><span class="sxs-lookup"><span data-stu-id="9f5d5-127">The following code snippet demonstrates how to ensure that destroying `bv` doesn't affect `udf2` because of an unexpected serialization behavior:</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="9f5d5-128">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9f5d5-128">Next steps</span></span>

* [<span data-ttu-id="9f5d5-129">Erste Schritte mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="9f5d5-129">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="9f5d5-130">Debuggen einer .NET für Apache Spark-Anwendung unter Windows</span><span class="sxs-lookup"><span data-stu-id="9f5d5-130">Debug a .NET for Apache Spark application on Windows</span></span>](debug.md)
* [<span data-ttu-id="9f5d5-131">Bereitstellen des .NET für Apache Spark-Workers und für benutzerdefinierte Funktionsbinärdateien</span><span class="sxs-lookup"><span data-stu-id="9f5d5-131">Deploy .NET for Apache Spark worker and user-defined function binaries</span></span>](deploy-worker-udf-binaries.md)
