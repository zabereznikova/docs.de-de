---
title: Erstellen benutzerdefinierter Funktionen in .NET für Apache Spark
description: Hier erfahren Sie, wie Sie benutzerdefinierte Funktionen (User-Defined Functions, UDFs) in .NET-Anwendungen für Apache Spark implementieren.
ms.date: 06/11/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: fe3dec187f94f84adb1217c39ff6aabc4b4db1c5
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "85142016"
---
# <a name="create-user-defined-functions-udf-in-net-for-apache-spark"></a>Erstellen benutzerdefinierter Funktionen in .NET für Apache Spark

In diesem Artikel erfahren Sie, wie Sie benutzerdefinierte Funktionen in .NET für Apache Spark verwenden. Bei [UDFs](https://spark.apache.org/docs/latest/api/java/org/apache/spark/sql/expressions/UserDefinedFunction.html) handelt es sich um ein Feature von Apache Spark, mit dem Sie benutzerdefinierte Funktionen verwenden können, um die integrierten Systemfeatures zu erweitern. UDFs transformieren Werte aus einer Tabellenzeile, um einen entsprechenden Ausgabewert pro Zeile zu erzeugen, der auf der in der UDF definierten Logik basiert.

## <a name="define-udfs"></a>Definieren von UDFs

Beachten Sie die folgende UDF-Definition:

```csharp
string s1 = "hello";
Func<Column, Column> udf = Udf<string, string>(
    str => $"{s1} {str}");
```

Die UDF akzeptiert `string` im Format einer [Spalte](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Column.cs#L14) eines [Datenrahmens](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L24) als Eingabe und gibt eine `string`-Variable zurück, dabei wird `hello` vor der Eingabe angefügt.

Der folgende Datenrahmen `df` enthält eine Namensliste:

```text
+-------+
|   name|
+-------+
|Michael|
|   Andy|
| Justin|
+-------+
```

Wenden Sie jetzt die oben definierte `udf` auf den Datenrahmen `df` an:

```csharp
DataFrame udfResult = df.Select(udf(df["name"]));
```

Der folgende Datenrahmen `udfResult` ist das Ergebnis der UDF:

```text
+-------------+
|         name|
+-------------+
|hello Michael|
|   hello Andy|
| hello Justin|
+-------------+
```

Mithilfe der [UDF-Hilfsfunktionen](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Functions.cs#L3616) und [Beispiele](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark.E2ETest/UdfTests/UdfSimpleTypesTests.cs#L49) auf GitHub können Sie sich ein besseres Verständnis für die Implementierung von UDFs aneignen.

## <a name="udf-serialization"></a>UDF-Serialisierung

Da es sich bei UDFs um Funktionen handelt, die auf Workern ausgeführt werden, müssen sie serialisiert und als Teil der Nutzlast des Treibers an die Worker gesendet werden. Der [Delegat](../../csharp/programming-guide/delegates/index.md), der einen Verweis auf die Methode darstellt, muss genau wie sein [Ziel](xref:System.Delegate.Target%2A) serialisiert werden, bei dem es sich um die Klasseninstanz handelt, in der der aktuelle Delegat die Instanzmethode aufruft. Sehen Sie sich dieses [Codebeispiel](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Utils/CommandSerDe.cs#L149) auf GitHub an, um sich ein besseres Verständnis für die UDF-Serialisierung anzueignen.

.NET für Apache Spark verwendet .NET Core. Dort wird die Serialisierung von Delegaten nicht unterstützt. Stattdessen wird Reflektion verwendet, um das Ziel zu serialisieren, in dem der Delegat definiert ist. Wenn mehrere Delegaten in einem gemeinsamen Gültigkeitsbereich definiert sind, verfügen sie über einen gemeinsamen Abschluss, der zum Ziel der Reflektion für die Serialisierung wird.

### <a name="serialization-example"></a>Serialisierungsbeispiel

Im folgenden Codeausschnitt werden zwei Zeichenfolgenvariablen definiert, auf die in zwei Funktionsdelegaten verwiesen wird, die die entsprechenden Zeichenfolgen als Ergebnis zurückgeben:

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

Der obige C#-Code generiert den folgenden C#-Disassemblierungscode (Quelle: [sharplab.io](https://sharplab.io)) für den Compiler:

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

Der Abschluss von `func` und `func2` ist `<>c__DisplayClass0_0`. Dabei handelt es sich um das Ziel, das bei der Serialisierung der Delegaten `func` und `func2` serialisiert wird. Obwohl `Func<string, string> a` nur auf `s1` verweist wird auch `s2` serialisiert, wenn die Bytes an die Worker gesendet werden.

Dadurch kann es zur Laufzeit zu unerwarteten Verhaltensweisen kommen (z. B. bei Verwendung von [Broadcastvariablen](broadcast-guide.md)). Deshalb wird empfohlen, die Sichtbarkeit der in einer Funktion verwendeten Variablen auf den Gültigkeitsbereich der Funktion zu beschränken.

Der folgende Codeausschnitt stellt die empfohlene Variante für die Implementierung des gewünschten Serialisierungsverhaltens dar:

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

Der obige C#-Code generiert den folgenden C#-Disassemblierungscode (Quelle: [sharplab.io](https://sharplab.io)) für den Compiler:

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

Sie sehen, dass `func` und `func2` sich keinen Abschluss mehr teilen, sondern separat mit `<>c__DisplayClass0_0` bzw. `<>c__DisplayClass0_1` abgeschlossen werden. Somit werden die als Ziel der Serialisierung angegebenen Variablen des Delegaten serialisiert. Berücksichtigen Sie dieses Verhalten, wenn Sie mehrere UDFs in einem gemeinsamen Gültigkeitsbereich implementieren.

## <a name="some-spark-udf-caveats"></a>Einschränkungen bei Spark-UDFs

* NULL-Werte in UDFs können Ausnahmen auslösen. Diese müssen vom Entwickler behandelt werden.
* UDFs nutzen nicht die Optimierungen der integrierten Spark-Funktionen. Sie sollten also nach Möglichkeit die integrierten Funktionen verwenden.

## <a name="next-steps"></a>Nächste Schritte

* [Erste Schritte mit .NET für Apache Spark](../tutorials/get-started.md)
* [Debuggen einer .NET für Apache Spark-Anwendung unter Windows](debug.md)
