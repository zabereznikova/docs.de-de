---
title: Ausführen von selektiven Komponententests
description: Es wird erläutert, wie Sie einen Filterausdruck zum Ausführen selektiver Komponententests mit dem dotnet-Testbefehl in .NET Core verwenden.
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: b9156300587215e68c01c609e298dbc1a2c53d11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77543507"
---
# <a name="running-selective-unit-tests"></a>Ausführen von selektiven Komponententests

Mit dem Befehl `dotnet test` in .NET Core können Sie einen Filterausdruck zum Ausführen selektiver Tests verwenden. In diesem Artikel wird gezeigt, wie Sie die auszuführenden Tests filtern. Die folgenden Beispiele verwenden `dotnet test`. Wenn Sie `vstest.console.exe` verwenden, ersetzen Sie `--filter` mit `--testcasefilter:`.

> [!NOTE]
> Die Verwendung von Filtern, die in `*nix` ein Ausrufezeichen (!) enthalten, erfordert Escapezeichen, da `!` reserviert ist. Dieser Filter überspringt beispielsweise alle Tests, wenn der Namespace IntegrationTests enthält: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.
> Beachten Sie den umgekehrten Schrägstrich, der dem Ausrufezeichen vorangestellt ist.

## <a name="mstest"></a>MSTest

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestCategory("CategoryA")]
        [Priority(1)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [Priority(2)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| expression | Ergebnis |
| ---------- | ------ |
| `dotnet test --filter Method` | Führt Tests aus, dessen `FullyQualifiedName``Method` enthält. Verfügbar in `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Führt Tests aus, dessen Name `TestMethod1` enthält. |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | Führt Tests aus, die sich in der Klasse `MSTestNamespace.UnitTest1` befinden.<br>**Hinweis:** Der Wert `ClassName` muss einen Namespace besitzen, damit `ClassName=UnitTest1` nicht funktioniert. |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | Führt alle Tests außer `MSTestNamespace.UnitTest1.TestMethod1` aus. |
| `dotnet test --filter TestCategory=CategoryA` | Führt Tests aus, die mit `[TestCategory("CategoryA")]` kommentiert sind. |
| `dotnet test --filter Priority=2` | Führt Tests aus, die mit `[Priority(2)]` kommentiert sind.<br>

**Verwenden bedingter Operatoren | und&amp;**

| expression | Ergebnis |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` aufweisen, **oder** `TestCategory` ist `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` aufweisen, **und** `TestCategory` ist `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | Führt Tests aus, in denen `FullyQualifiedName` entweder `UnitTest1` enthält, **und** `TestCategory` ist `CategoryA`, **oder** `Priority` ist 1. |

## <a name="xunit"></a>xUnit

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "CategoryA")]
        [Trait("Priority", "1")]
        [Fact]
        public void Test1()
        {
        }

        [Trait("Priority", "2")]
        [Fact]
        public void Test2()
        {
        }
    }
}
```

| expression | Ergebnis |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | Führt einen Test, `XUnitNamespace.TestClass1.Test1`, aus. |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | Führt alle Tests außer `XUnitNamespace.TestClass1.Test1` aus. |
| `dotnet test --filter DisplayName~TestClass1` | Führt Tests aus, dessen Anzeigename `TestClass1` enthält. |

Im Codebeispiel können die definierten Merkmale mit den Schlüsseln `Category` und `Priority` zum Filtern verwendet werden.

| expression | Ergebnis |
| ---------- | ------ |
| `dotnet test --filter XUnit` | Führt Tests aus, dessen `FullyQualifiedName``XUnit` enthält.  Verfügbar in `vstest 15.1+`. |
| `dotnet test --filter Category=CategoryA` | Führt Tests aus, die `[Trait("Category", "CategoryA")]` besitzen. |

**Verwenden bedingter Operatoren | und&amp;**

| expression | Ergebnis |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | Führt Tests aus, die `TestClass1` in `FullyQualifiedName` aufweisen, **oder** `Category` ist `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | Führt Tests aus, die `TestClass1` in `FullyQualifiedName` aufweisen, **und** `Category` ist `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | Führt Tests aus, in denen `FullyQualifiedName` entweder `TestClass1` enthält, **und** `Category` ist `CategoryA`, **oder** `Priority` ist 1. |

## <a name="nunit"></a>NUnit

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Category("CategoryA")]
        [Property("Priority", 1)]
        [Test]
        public void TestMethod1()
        {
        }

        [Property("Priority", 2)]
        [Test]
        public void TestMethod2()
        {
        }
    }
}
```

| expression | Ergebnis |
| ---------- | ------ |
| `dotnet test --filter Method` | Führt Tests aus, dessen `FullyQualifiedName``Method` enthält. Verfügbar in `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Führt Tests aus, dessen Name `TestMethod1` enthält. |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | Führt Tests aus, die sich in der Klasse `NUnitNamespace.UnitTest1` befinden.<br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | Führt alle Tests außer `NUnitNamespace.UnitTest1.TestMethod1` aus. |
| `dotnet test --filter TestCategory=CategoryA` | Führt Tests aus, die mit `[Category("CategoryA")]` kommentiert sind. |
| `dotnet test --filter Priority=2` | Führt Tests aus, die mit `[Priority(2)]` kommentiert sind.<br>

**Verwenden bedingter Operatoren | und&amp;**

| expression | Ergebnis |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` aufweisen, **oder** `TestCategory` ist `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` aufweisen, **und** `TestCategory` ist `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | Führt Tests aus, in denen `FullyQualifiedName` entweder `UnitTest1` enthält, **und** `TestCategory` ist `CategoryA`, **oder** `Priority` ist 1. |
