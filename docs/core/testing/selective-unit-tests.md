---
title: "Ausführen von selektiven Komponententests"
description: "Zeigt, wie Sie einen Filterausdruck zum Ausführen selektiver Komponententests mit dem dotnet-Testbefehl verwenden."
keywords: .NET, .NET Core, Komponententest, selektiver Test
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 13d01272-bbf8-456c-a97a-560001d1a7f2
ms.workload: dotnetcore
ms.openlocfilehash: a650e971afd63171b0cc12f679d81bc222a609a5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="running-selective-unit-tests"></a>Ausführen von selektiven Komponententests

Die folgenden Beispiele verwenden `dotnet test`. Wenn Sie `vstest.console.exe` verwenden, ersetzen Sie `--filter ` mit `--testcasefilter:`.

## <a name="mstest"></a>MSTest

```csharp
namespace MSTestNamespace
{
    using Microsoft.VisualStudio.TestTools.UnitTesting;

    [TestClass]
    public class UnitTestClass1
    {
        [Priority(2)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [TestCategory("CategoryA")]
        [Priority(3)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| Ausdruck | Ergebnis |
| ---------- | ------ |
| `dotnet test --filter Method` | Führt Tests aus, dessen `FullyQualifiedName` `Method` enthält. Verfügbar in `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Führt Tests aus, dessen Name `TestMethod1` enthält. |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | Führt Tests aus, die sich in der Klasse `MSTestNamespace.UnitTestClass1` befinden.<br>**Hinweis:** Der Wert `ClassName` muss einen Namespace besitzen, damit `ClassName=UnitTestClass1` nicht funktioniert. |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | Führt alle Tests außer `MSTestNamespace.UnitTestClass1.TestMethod1` aus. |
| `dotnet test --filter TestCategory=CategoryA` | Führt Tests aus, die mit `[TestCategory("CategoryA")]` kommentiert sind. |
| `dotnet test --filter Priority=3` | Führt Tests aus, die mit `[Priority(3)]` kommentiert sind.<br>**Hinweis:** `Priority~3` ist ein ungültiger Wert, da er keine Zeichenfolge ist. |

**Verwenden bedingter Operatoren | und&amp;**

| Ausdruck | Ergebnis |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | Führt Tests aus, die `UnitTestClass1` in `FullyQualifiedName` besitzen, **oder** `TestCategory` ist `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | Führt Tests aus, die `UnitTestClass1` in `FullyQualifiedName` besitzen, **und** `TestCategory` ist `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | Führt Tests aus, in denen `FullyQualifiedName` entweder `UnitTestClass1` enthalten ist, **und** `TestCategory` ist `CategoryA`, **oder** `Priority` ist 1. |

## <a name="xunit"></a>xUnit

```csharp
namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "bvt")]
        [Trait("Priority", "1")]
        [Fact]
        public void foo()
        {
        }

        [Trait("Category", "Nightly")]
        [Trait("Priority", "2")]
        [Fact]
        public void bar()
        {
        }
    }
}
```

| Ausdruck | Ergebnis |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | Führt einen Test, `XUnitNamespace.TestClass1.Test1`, aus. |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | Führt alle Tests außer `XUnitNamespace.TestClass1.Test1` aus. |
| `dotnet test --filter DisplayName~TestClass1` | Führt Tests aus, dessen Anzeigename `TestClass1` enthält. |

Im Codebeispiel können die definierten Merkmale mit den Schlüsseln `Category` und `Priority` zum Filtern verwendet werden.

| Ausdruck | Ergebnis |
| ---------- | ------ |
| `dotnet test --filter XUnit` | Führt Tests aus, dessen `FullyQualifiedName` `XUnit` enthält.  Verfügbar in `vstest 15.1+`. |
| `dotnet test --filter Category=bvt` | Führt Tests aus, die `[Trait("Category", "bvt")]` besitzen. |

**Verwenden bedingter Operatoren | und&amp;**

| Ausdruck | Ergebnis |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | Führt Tests aus, die `TestClass1` in `FullyQualifiedName` besitzen, **oder** `Category` ist `Nightly`. |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | Führt Tests aus, die `TestClass1` in `FullyQualifiedName` besitzen, **und** `Category` ist `Nightly`. |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | Führt Tests aus, in denen `FullyQualifiedName` entweder `TestClass1` enthalten ist, **und** `Category` ist `CategoryA`, **oder** `Priority` ist 1. |
