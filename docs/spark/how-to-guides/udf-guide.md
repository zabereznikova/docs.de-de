---
title: Erstellen benutzerdefinierter Funktionen in .NET für Apache Spark
description: Hier erfahren Sie, wie Sie benutzerdefinierte Funktionen (User-Defined Functions, UDFs) in .NET-Anwendungen für Apache Spark implementieren.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 97afda8ed17d3719c534d72ad3ad026745a70922
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620923"
---
# <a name="create-user-defined-functions-udf-in-net-for-apache-spark"></a><span data-ttu-id="6fb4e-103">Erstellen benutzerdefinierter Funktionen in .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="6fb4e-103">Create user-defined functions (UDF) in .NET for Apache Spark</span></span>

<span data-ttu-id="6fb4e-104">In diesem Artikel erfahren Sie, wie Sie benutzerdefinierte Funktionen in .NET für Apache Spark verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-104">In this article, you learn how to use user-defined functions (UDF) in .NET for Apache Spark.</span></span> <span data-ttu-id="6fb4e-105">Bei [UDFs](https://spark.apache.org/docs/latest/api/java/org/apache/spark/sql/expressions/UserDefinedFunction.html) handelt es sich um ein Feature von Apache Spark, mit dem Sie benutzerdefinierte Funktionen verwenden können, um die integrierten Systemfeatures zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-105">[UDFs)](https://spark.apache.org/docs/latest/api/java/org/apache/spark/sql/expressions/UserDefinedFunction.html) are a Spark feature that allow you to use custom functions to extend the system's built-in functionality.</span></span> <span data-ttu-id="6fb4e-106">UDFs transformieren Werte aus einer Tabellenzeile, um einen entsprechenden Ausgabewert pro Zeile zu erzeugen, der auf der in der UDF definierten Logik basiert.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-106">UDFs transform values from a single row within a table to produce a single corresponding output value per row based on the logic defined in the UDF.</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="define-udfs"></a><span data-ttu-id="6fb4e-107">Definieren von UDFs</span><span class="sxs-lookup"><span data-stu-id="6fb4e-107">Define UDFs</span></span>

<span data-ttu-id="6fb4e-108">Beachten Sie die folgende UDF-Definition:</span><span class="sxs-lookup"><span data-stu-id="6fb4e-108">Review the following UDF definition:</span></span>

```csharp
string s1 = "hello";
Func<Column, Column> udf = Udf<string, string>(
    str => $"{s1} {str}");
```

<span data-ttu-id="6fb4e-109">Die UDF akzeptiert `string` im Format einer [Spalte](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Column.cs#L14) eines [Datenrahmens](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L24) als Eingabe und gibt eine `string`-Variable zurück, dabei wird `hello` vor der Eingabe angefügt.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-109">The UDF takes a `string` as an input in the form of a [Column](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Column.cs#L14) of a [Dataframe](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L24)) and returns a `string` with `hello` appended in front of the input.</span></span>

<span data-ttu-id="6fb4e-110">Der folgende Datenrahmen `df` enthält eine Namensliste:</span><span class="sxs-lookup"><span data-stu-id="6fb4e-110">The following DataFrame `df` contains a list of names:</span></span>

```text
+-------+
|   name|
+-------+
|Michael|
|   Andy|
| Justin|
+-------+
```

<span data-ttu-id="6fb4e-111">Wenden Sie jetzt die oben definierte `udf` auf den Datenrahmen `df` an:</span><span class="sxs-lookup"><span data-stu-id="6fb4e-111">Now let's apply the above defined `udf` to the DataFrame `df`:</span></span>

```csharp
DataFrame udfResult = df.Select(udf(df["name"]));
```

<span data-ttu-id="6fb4e-112">Der folgende Datenrahmen `udfResult` ist das Ergebnis der UDF:</span><span class="sxs-lookup"><span data-stu-id="6fb4e-112">The following DataFrame `udfResult` is the result of the UDF:</span></span>

```text
+-------------+
|         name|
+-------------+
|hello Michael|
|   hello Andy|
| hello Justin|
+-------------+
```

<span data-ttu-id="6fb4e-113">Mithilfe der [UDF-Hilfsfunktionen](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Functions.cs#L3616) und [Beispiele](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark.E2ETest/UdfTests/UdfSimpleTypesTests.cs#L49) auf GitHub können Sie sich ein besseres Verständnis für die Implementierung von UDFs aneignen.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-113">To better understand how to implement UDFs, review the [UDF helper functions](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Functions.cs#L3616) and [examples](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark.E2ETest/UdfTests/UdfSimpleTypesTests.cs#L49) on GitHub.</span></span>

## <a name="udf-serialization"></a><span data-ttu-id="6fb4e-114">UDF-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="6fb4e-114">UDF serialization</span></span>

<span data-ttu-id="6fb4e-115">Da es sich bei UDFs um Funktionen handelt, die auf Workern ausgeführt werden, müssen sie serialisiert und als Teil der Nutzlast des Treibers an die Worker gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-115">Because UDFs are functions that need to be executed on workers, they have to be serialized and sent to the workers as part of the payload from the driver.</span></span> <span data-ttu-id="6fb4e-116">Der [Delegat](../../csharp/programming-guide/delegates/index.md), der einen Verweis auf die Methode darstellt, muss genau wie sein [Ziel](xref:System.Delegate.Target%2A) serialisiert werden, bei dem es sich um die Klasseninstanz handelt, in der der aktuelle Delegat die Instanzmethode aufruft.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-116">The [delegate](../../csharp/programming-guide/delegates/index.md), which is a reference to the method, needs to be serialized as well as its [target](xref:System.Delegate.Target%2A), which is the class instance on which the current delegate invokes the instance method.</span></span> <span data-ttu-id="6fb4e-117">Sehen Sie sich dieses [Codebeispiel](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Utils/CommandSerDe.cs#L149) auf GitHub an, um sich ein besseres Verständnis für die UDF-Serialisierung anzueignen.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-117">Review this [code example in GitHub](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Utils/CommandSerDe.cs#L149) to get a better understanding of how UDF serialization is being done.</span></span>

<span data-ttu-id="6fb4e-118">.NET für Apache Spark verwendet .NET Core. Dort wird die Serialisierung von Delegaten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-118">.NET for Apache Spark uses .NET Core, which doesn't support serializing delegates.</span></span> <span data-ttu-id="6fb4e-119">Stattdessen wird Reflektion verwendet, um das Ziel zu serialisieren, in dem der Delegat definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-119">Instead, reflection is used to serialize the target where the delegate is defined.</span></span> <span data-ttu-id="6fb4e-120">Wenn mehrere Delegaten in einem gemeinsamen Gültigkeitsbereich definiert sind, verfügen sie über einen gemeinsamen Abschluss, der zum Ziel der Reflektion für die Serialisierung wird.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-120">When multiple delegates are defined in a common scope, they have a shared closure that becomes the target of reflection for serialization.</span></span>

### <a name="serialization-example"></a><span data-ttu-id="6fb4e-121">Serialisierungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="6fb4e-121">Serialization example</span></span>

<span data-ttu-id="6fb4e-122">Im folgenden Codeausschnitt werden zwei Zeichenfolgenvariablen definiert, auf die in zwei Funktionsdelegaten verwiesen wird, die die entsprechenden Zeichenfolgen als Ergebnis zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="6fb4e-122">The following code snippet defines two string variables that are being referenced in two function delegates that return the respective strings as a result:</span></span>

```csharp
using System;

public class C {
    public void M() {
        string s1 = "s1";
        string s2 = "s2";
        Func<string, string> a = str => s1;
        Func<string, string> b = str => s2;
    }
}
```

<span data-ttu-id="6fb4e-123">Der obige C#-Code generiert den folgenden C#-Disassemblierungscode (Quelle: [sharplab.io](https://sharplab.io)) für den Compiler:</span><span class="sxs-lookup"><span data-stu-id="6fb4e-123">The above C# code generates the following C# disassembly (credit source: [sharplab.io](https://sharplab.io)) code from the compiler:</span></span>

```csharp
public class C
{
    [CompilerGenerated]
    private sealed class <>c__DisplayClass0_0
    {
        public string s1;

        public string s2;

        internal string <M>b__0(string str)
        {
            return s1;
        }

        internal string <M>b__1(string str)
        {
            return s2;
        }
    }

    public void M()
    {
        <>c__DisplayClass0_0 <>c__DisplayClass0_ = new <>c__DisplayClass0_0();
        <>c__DisplayClass0_.s1 = "s1";
        <>c__DisplayClass0_.s2 = "s2";
        Func<string, string> func = new Func<string, string>(<>c__DisplayClass0_.<M>b__0);
        Func<string, string> func2 = new Func<string, string>(<>c__DisplayClass0_.<M>b__1);
    }
}
```

<span data-ttu-id="6fb4e-124">Der Abschluss von `func` und `func2` ist `<>c__DisplayClass0_0`. Dabei handelt es sich um das Ziel, das bei der Serialisierung der Delegaten `func` und `func2` serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-124">Both `func` and `func2` share the same closure `<>c__DisplayClass0_0`, which is the target that is serialized when serializing the delegates `func` and `func2`.</span></span> <span data-ttu-id="6fb4e-125">Obwohl `Func<string, string> a` nur auf `s1` verweist wird auch `s2` serialisiert, wenn die Bytes an die Worker gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-125">Even though `Func<string, string> a` is only referencing `s1`, `s2` is also serialized when the bytes are sent to the workers.</span></span>

<span data-ttu-id="6fb4e-126">Dadurch kann es zur Laufzeit zu unerwarteten Verhaltensweisen kommen (z. B. bei Verwendung von [Broadcastvariablen](broadcast-guide.md)). Deshalb wird empfohlen, die Sichtbarkeit der in einer Funktion verwendeten Variablen auf den Gültigkeitsbereich der Funktion zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-126">This can lead to some unexpected behaviors at runtime (like in the case of using [broadcast variables](broadcast-guide.md)), which is why we recommend that you restrict the visibility of the variables used in a function to that function's scope.</span></span>

<span data-ttu-id="6fb4e-127">Der folgende Codeausschnitt stellt die empfohlene Variante für die Implementierung des gewünschten Serialisierungsverhaltens dar:</span><span class="sxs-lookup"><span data-stu-id="6fb4e-127">The following code snippet is the recommended way to implement the desired serialization behavior:</span></span>

```csharp
using System;

public class C {
    public void M() {
        {
            string s1 = "s1";
            Func<string, string> a = str => s1;
        }
        {
            string s2 = "s2";
            Func<string, string> b = str => s2;
        }
    }
}
```

<span data-ttu-id="6fb4e-128">Der obige C#-Code generiert den folgenden C#-Disassemblierungscode (Quelle: [sharplab.io](https://sharplab.io)) für den Compiler:</span><span class="sxs-lookup"><span data-stu-id="6fb4e-128">The above C# code generates the following C# disassembly (credit source: [sharplab.io](https://sharplab.io)) code from the compiler:</span></span>

```csharp
public class C
{
    [CompilerGenerated]
    private sealed class <>c__DisplayClass0_0
    {
        public string s1;

        internal string <M>b__0(string str)
        {
            return s1;
        }
    }

    [CompilerGenerated]
    private sealed class <>c__DisplayClass0_1
    {
        public string s2;

        internal string <M>b__1(string str)
        {
            return s2;
        }
    }

    public void M()
    {
        <>c__DisplayClass0_0 <>c__DisplayClass0_ = new <>c__DisplayClass0_0();
        <>c__DisplayClass0_.s1 = "s1";
        Func<string, string> func = new Func<string, string>(<>c__DisplayClass0_.<M>b__0);
        <>c__DisplayClass0_1 <>c__DisplayClass0_2 = new <>c__DisplayClass0_1();
        <>c__DisplayClass0_2.s2 = "s2";
        Func<string, string> func2 = new Func<string, string>(<>c__DisplayClass0_2.<M>b__1);
    }
}
```

<span data-ttu-id="6fb4e-129">Sie sehen, dass `func` und `func2` sich keinen Abschluss mehr teilen, sondern separat mit `<>c__DisplayClass0_0` bzw. `<>c__DisplayClass0_1` abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-129">Notice that `func` and `func2` no longer share a closure, and they have their own separate closures `<>c__DisplayClass0_0` and `<>c__DisplayClass0_1` respectively.</span></span> <span data-ttu-id="6fb4e-130">Somit werden die als Ziel der Serialisierung angegebenen Variablen des Delegaten serialisiert.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-130">When used as the target for serialization, nothing other than the referenced variables will get serialized for the delegate.</span></span> <span data-ttu-id="6fb4e-131">Berücksichtigen Sie dieses Verhalten, wenn Sie mehrere UDFs in einem gemeinsamen Gültigkeitsbereich implementieren.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-131">This behavior is important to keep in mind while implementing multiple UDFs in a common scope.</span></span>

## <a name="some-spark-udf-caveats"></a><span data-ttu-id="6fb4e-132">Einschränkungen bei Spark-UDFs</span><span class="sxs-lookup"><span data-stu-id="6fb4e-132">Some Spark UDF caveats</span></span>

* <span data-ttu-id="6fb4e-133">NULL-Werte in UDFs können Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-133">Null values in UDFs can throw exceptions.</span></span> <span data-ttu-id="6fb4e-134">Diese müssen vom Entwickler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-134">It's the responsibility of the developer to handle them.</span></span>
* <span data-ttu-id="6fb4e-135">UDFs nutzen nicht die Optimierungen der integrierten Spark-Funktionen. Sie sollten also nach Möglichkeit die integrierten Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="6fb4e-135">UDFs don't leverage the optimizations provided by Spark's built-in functions, so it's recommended to use built-in functions where possible.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6fb4e-136">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6fb4e-136">Next steps</span></span>

* [<span data-ttu-id="6fb4e-137">Erste Schritte mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="6fb4e-137">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="6fb4e-138">Debuggen einer .NET für Apache Spark-Anwendung unter Windows</span><span class="sxs-lookup"><span data-stu-id="6fb4e-138">Debug a .NET for Apache Spark application on Windows</span></span>](debug.md)
