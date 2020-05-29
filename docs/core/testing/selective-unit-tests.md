---
title: Ausführen selektiver Komponententests
description: Es wird erläutert, wie Sie einen Filterausdruck zum Ausführen selektiver Komponententests mit dem dotnet-Testbefehl in .NET Core verwenden.
author: smadala
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: 6a6bbb0687742d1e3288d64fb88f6825dc678e28
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702980"
---
# <a name="run-selective-unit-tests"></a>Ausführen selektiver Komponententests

Mit dem Befehl [`dotnet test`](../tools/dotnet-test.md) in .NET Core können Sie einen Filterausdruck zum Ausführen selektiver Tests verwenden. In diesem Artikel wird gezeigt, wie Sie die auszuführenden Tests filtern. Die folgenden Beispiele verwenden `dotnet test`. Wenn Sie `vstest.console.exe` verwenden, ersetzen Sie `--filter` mit `--testcasefilter:`.

## <a name="character-escaping"></a>Escapezeichen

Die Verwendung von Filtern, die in `*nix` ein Ausrufezeichen `!` enthalten, erfordert Escapezeichen, da `!` reserviert ist. Dieser Filter überspringt beispielsweise alle Tests, wenn der Namespace IntegrationTests enthält:

```dotnetcli
dotnet test --filter FullyQualifiedName\!~IntegrationTests
```

> [!IMPORTANT]
> Der umgekehrte Schrägstrich ist dem Ausrufezeichen vorangestellt, um anzugeben, dass es sich um ein Escapezeichen `\!` handelt.

Für `FullyQualifiedName`-Werte, die ein Komma für generische Typparameter enthalten, versehen Sie das Komma mit dem Escapezeichen `%2C`. Zum Beispiel:

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

:::zone pivot="mstest"

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestMethod, Priority(1), TestCategory("CategoryA")]
        public void TestMethod1()
        {
        }

        [TestMethod, Priority(2)]
        public void TestMethod2()
        {
        }
    }
}
```

| expression | Ergebnis |
|--|--|
| `dotnet test --filter Method` | Führt Tests aus, dessen <xref:System.Reflection.Module.FullyQualifiedName>`Method` enthält. Verfügbar in `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Führt Tests aus, dessen Name `TestMethod1` enthält. |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | Führt Tests aus, die sich in der Klasse `MSTestNamespace.UnitTest1` befinden.<br>**Hinweis**: Der Wert `ClassName` muss einen Namespace besitzen, damit `ClassName=UnitTest1` nicht funktioniert. |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | Führt alle Tests außer `MSTestNamespace.UnitTest1.TestMethod1` aus. |
| `dotnet test --filter TestCategory=CategoryA` | Führt Tests aus, die mit `[TestCategory("CategoryA")]` annotiert sind. |
| `dotnet test --filter Priority=2` | Führt Tests aus, die mit `[Priority(2)]` annotiert sind. |

Beispiele für die Verwendung der bedingten Operatoren `|` und `&`:

Zum Ausführen von Tests, bei denen `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> enthalten **oder** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> `"CategoryA"` ist.

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

Zum Ausführen von Tests, bei denen `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> enthalten **und** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> `"CategoryA"` ist.

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

Zum Ausführen von Tests, bei denen entweder <xref:System.Reflection.Module.FullyQualifiedName> `UnitTest1` enthält **und** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> `"CategoryA"` ist **oder** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute> die Priorität `1` hat.

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

:::zone-end
:::zone pivot="xunit"

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Fact, Trait("Priority", "1"), Trait("Category", "CategoryA")]
        public void Test1()
        {
        }

        [Fact, Trait("Priority", "2")]
        public void Test2()
        {
        }
    }
}
```

| expression | Ergebnis |
|--|--|
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | Führt einen Test, `XUnitNamespace.TestClass1.Test1`, aus. |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | Führt alle Tests außer `XUnitNamespace.TestClass1.Test1` aus. |
| `dotnet test --filter DisplayName~TestClass1` | Führt Tests aus, dessen Anzeigename `TestClass1` enthält. |

Im Codebeispiel können die definierten Merkmale mit den Schlüsseln `"Category"` und `"Priority"` zum Filtern verwendet werden.

| expression | Ergebnis |
|--|--|
| `dotnet test --filter XUnit` | Führt Tests aus, dessen <xref:System.Reflection.Module.FullyQualifiedName>`XUnit` enthält.  Verfügbar in `vstest 15.1+`. |
| `dotnet test --filter Category=CategoryA` | Führt Tests aus, die `[Trait("Category", "CategoryA")]` enthalten. |

Beispiele für die Verwendung der bedingten Operatoren `|` und `&`:

Zum Ausführen von Tests, bei denen `TestClass1` ihren <xref:System.Reflection.Module.FullyQualifiedName> enthält **oder** die über einen `Trait` mit dem Schlüssel `"Category"` und dem Wert `"CategoryA"` verfügen.

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1|Category=CategoryA"
```

Zum Ausführen von Tests, bei denen `TestClass1` ihren <xref:System.Reflection.Module.FullyQualifiedName> enthält **und** die über einen `Trait` mit dem Schlüssel `"Category"` und dem Wert `"CategoryA"` verfügen.

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"
```

Zum Ausführen von Tests, bei denen entweder <xref:System.Reflection.Module.FullyQualifiedName> `TestClass1` enthält **und** die über einen `Trait` mit dem Schlüssel `"Category"` und dem Wert `"CategoryA"` verfügen **oder** die über einen `Trait` mit dem Schlüssel `"Priority"` und dem Wert `1` verfügen.

```dotnetcli
dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)|Priority=1"
```

:::zone-end
:::zone pivot="nunit"

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Test, Property("Priority", 1), Category("CategoryA")]
        public void TestMethod1()
        {
        }

        [Test, Property("Priority", 2)]
        public void TestMethod2()
        {
        }
    }
}
```

| expression | Ergebnis |
|--|--|
| `dotnet test --filter Method` | Führt Tests aus, dessen <xref:System.Reflection.Module.FullyQualifiedName>`Method` enthält. Verfügbar in `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Führt Tests aus, dessen Name `TestMethod1` enthält. |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | Führt Tests aus, die sich in der Klasse `NUnitNamespace.UnitTest1` befinden. |
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | Führt alle Tests außer `NUnitNamespace.UnitTest1.TestMethod1` aus. |
| `dotnet test --filter TestCategory=CategoryA` | Führt Tests aus, die mit `[Category("CategoryA")]` annotiert sind. |
| `dotnet test --filter Priority=2` | Führt Tests aus, die mit `[Priority(2)]` annotiert sind. |

Beispiele für die Verwendung der bedingten Operatoren `|` und `&`:

Zum Ausführen von Tests, bei denen `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> enthalten **oder** `Category` `"CategoryA"` ist.

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

Zum Ausführen von Tests, bei denen `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> enthalten **und** `Category` `"CategoryA"` ist.

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

Zum Ausführen von Tests, bei denen entweder <xref:System.Reflection.Module.FullyQualifiedName> `UnitTest1` enthält **und** `Category` `"CategoryA"` ist **oder** `Property` die `"Priority"` `1`hat.

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

Weitere Informationen finden Sie unter [TestCase-Filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).

:::zone-end

## <a name="see-also"></a>Siehe auch

- [dotnet test](../tools/dotnet-test.md)
- [dotnet test --filter](../tools/dotnet-test.md#filter-option-details)

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Festlegen einer Reihenfolge von Komponententests](order-unit-tests.md)
