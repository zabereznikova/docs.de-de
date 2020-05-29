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
# <a name="run-selective-unit-tests"></a><span data-ttu-id="cda2e-103">Ausführen selektiver Komponententests</span><span class="sxs-lookup"><span data-stu-id="cda2e-103">Run selective unit tests</span></span>

<span data-ttu-id="cda2e-104">Mit dem Befehl [`dotnet test`](../tools/dotnet-test.md) in .NET Core können Sie einen Filterausdruck zum Ausführen selektiver Tests verwenden.</span><span class="sxs-lookup"><span data-stu-id="cda2e-104">With the [`dotnet test`](../tools/dotnet-test.md) command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="cda2e-105">In diesem Artikel wird gezeigt, wie Sie die auszuführenden Tests filtern.</span><span class="sxs-lookup"><span data-stu-id="cda2e-105">This article demonstrates how to filter which tests are run.</span></span> <span data-ttu-id="cda2e-106">Die folgenden Beispiele verwenden `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="cda2e-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="cda2e-107">Wenn Sie `vstest.console.exe` verwenden, ersetzen Sie `--filter` mit `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="cda2e-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="cda2e-108">Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="cda2e-108">Character escaping</span></span>

<span data-ttu-id="cda2e-109">Die Verwendung von Filtern, die in `*nix` ein Ausrufezeichen `!` enthalten, erfordert Escapezeichen, da `!` reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="cda2e-109">Using filters that include exclamation mark `!` on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="cda2e-110">Dieser Filter überspringt beispielsweise alle Tests, wenn der Namespace IntegrationTests enthält:</span><span class="sxs-lookup"><span data-stu-id="cda2e-110">For example, this filter skips all tests if the namespace contains IntegrationTests:</span></span>

```dotnetcli
dotnet test --filter FullyQualifiedName\!~IntegrationTests
```

> [!IMPORTANT]
> <span data-ttu-id="cda2e-111">Der umgekehrte Schrägstrich ist dem Ausrufezeichen vorangestellt, um anzugeben, dass es sich um ein Escapezeichen `\!` handelt.</span><span class="sxs-lookup"><span data-stu-id="cda2e-111">The backslash precedes the exclamation mark to indicate it is an escaped character `\!`.</span></span>

<span data-ttu-id="cda2e-112">Für `FullyQualifiedName`-Werte, die ein Komma für generische Typparameter enthalten, versehen Sie das Komma mit dem Escapezeichen `%2C`.</span><span class="sxs-lookup"><span data-stu-id="cda2e-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="cda2e-113">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cda2e-113">For example:</span></span>

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

| <span data-ttu-id="cda2e-114">expression</span><span class="sxs-lookup"><span data-stu-id="cda2e-114">Expression</span></span> | <span data-ttu-id="cda2e-115">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cda2e-115">Result</span></span> |
|--|--|
| `dotnet test --filter Method` | <span data-ttu-id="cda2e-116">Führt Tests aus, dessen <xref:System.Reflection.Module.FullyQualifiedName>`Method` enthält.</span><span class="sxs-lookup"><span data-stu-id="cda2e-116">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `Method`.</span></span> <span data-ttu-id="cda2e-117">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="cda2e-117">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="cda2e-118">Führt Tests aus, dessen Name `TestMethod1` enthält.</span><span class="sxs-lookup"><span data-stu-id="cda2e-118">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="cda2e-119">Führt Tests aus, die sich in der Klasse `MSTestNamespace.UnitTest1` befinden.</span><span class="sxs-lookup"><span data-stu-id="cda2e-119">Runs tests that are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="cda2e-120">**Hinweis**: Der Wert `ClassName` muss einen Namespace besitzen, damit `ClassName=UnitTest1` nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="cda2e-120">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="cda2e-121">Führt alle Tests außer `MSTestNamespace.UnitTest1.TestMethod1` aus.</span><span class="sxs-lookup"><span data-stu-id="cda2e-121">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="cda2e-122">Führt Tests aus, die mit `[TestCategory("CategoryA")]` annotiert sind.</span><span class="sxs-lookup"><span data-stu-id="cda2e-122">Runs tests that are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="cda2e-123">Führt Tests aus, die mit `[Priority(2)]` annotiert sind.</span><span class="sxs-lookup"><span data-stu-id="cda2e-123">Runs tests that are annotated with `[Priority(2)]`.</span></span> |

<span data-ttu-id="cda2e-124">Beispiele für die Verwendung der bedingten Operatoren `|` und `&`:</span><span class="sxs-lookup"><span data-stu-id="cda2e-124">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="cda2e-125">Zum Ausführen von Tests, bei denen `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> enthalten **oder** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> `"CategoryA"` ist.</span><span class="sxs-lookup"><span data-stu-id="cda2e-125">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> is `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

<span data-ttu-id="cda2e-126">Zum Ausführen von Tests, bei denen `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> enthalten **und** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> `"CategoryA"` ist.</span><span class="sxs-lookup"><span data-stu-id="cda2e-126">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

<span data-ttu-id="cda2e-127">Zum Ausführen von Tests, bei denen entweder <xref:System.Reflection.Module.FullyQualifiedName> `UnitTest1` enthält **und** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> `"CategoryA"` ist **oder** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute> die Priorität `1` hat.</span><span class="sxs-lookup"><span data-stu-id="cda2e-127">To run tests that have either <xref:System.Reflection.Module.FullyQualifiedName> containing `UnitTest1` **and** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> of `"CategoryA"` **or** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute> with a priority of `1`.</span></span>

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

| <span data-ttu-id="cda2e-128">expression</span><span class="sxs-lookup"><span data-stu-id="cda2e-128">Expression</span></span> | <span data-ttu-id="cda2e-129">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cda2e-129">Result</span></span> |
|--|--|
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="cda2e-130">Führt einen Test, `XUnitNamespace.TestClass1.Test1`, aus.</span><span class="sxs-lookup"><span data-stu-id="cda2e-130">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="cda2e-131">Führt alle Tests außer `XUnitNamespace.TestClass1.Test1` aus.</span><span class="sxs-lookup"><span data-stu-id="cda2e-131">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="cda2e-132">Führt Tests aus, dessen Anzeigename `TestClass1` enthält.</span><span class="sxs-lookup"><span data-stu-id="cda2e-132">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="cda2e-133">Im Codebeispiel können die definierten Merkmale mit den Schlüsseln `"Category"` und `"Priority"` zum Filtern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cda2e-133">In the code example, the defined traits with keys `"Category"` and `"Priority"` can be used for filtering.</span></span>

| <span data-ttu-id="cda2e-134">expression</span><span class="sxs-lookup"><span data-stu-id="cda2e-134">Expression</span></span> | <span data-ttu-id="cda2e-135">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cda2e-135">Result</span></span> |
|--|--|
| `dotnet test --filter XUnit` | <span data-ttu-id="cda2e-136">Führt Tests aus, dessen <xref:System.Reflection.Module.FullyQualifiedName>`XUnit` enthält.</span><span class="sxs-lookup"><span data-stu-id="cda2e-136">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `XUnit`.</span></span>  <span data-ttu-id="cda2e-137">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="cda2e-137">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="cda2e-138">Führt Tests aus, die `[Trait("Category", "CategoryA")]` enthalten.</span><span class="sxs-lookup"><span data-stu-id="cda2e-138">Runs tests that have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="cda2e-139">Beispiele für die Verwendung der bedingten Operatoren `|` und `&`:</span><span class="sxs-lookup"><span data-stu-id="cda2e-139">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="cda2e-140">Zum Ausführen von Tests, bei denen `TestClass1` ihren <xref:System.Reflection.Module.FullyQualifiedName> enthält **oder** die über einen `Trait` mit dem Schlüssel `"Category"` und dem Wert `"CategoryA"` verfügen.</span><span class="sxs-lookup"><span data-stu-id="cda2e-140">To run tests that have `TestClass1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** have a `Trait` with a key of `"Category"` and value of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1|Category=CategoryA"
```

<span data-ttu-id="cda2e-141">Zum Ausführen von Tests, bei denen `TestClass1` ihren <xref:System.Reflection.Module.FullyQualifiedName> enthält **und** die über einen `Trait` mit dem Schlüssel `"Category"` und dem Wert `"CategoryA"` verfügen.</span><span class="sxs-lookup"><span data-stu-id="cda2e-141">To run tests that have `TestClass1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a `Trait` with a key of `"Category"` and value of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"
```

<span data-ttu-id="cda2e-142">Zum Ausführen von Tests, bei denen entweder <xref:System.Reflection.Module.FullyQualifiedName> `TestClass1` enthält **und** die über einen `Trait` mit dem Schlüssel `"Category"` und dem Wert `"CategoryA"` verfügen **oder** die über einen `Trait` mit dem Schlüssel `"Priority"` und dem Wert `1` verfügen.</span><span class="sxs-lookup"><span data-stu-id="cda2e-142">To run tests that have either <xref:System.Reflection.Module.FullyQualifiedName> containing `TestClass1` **and** have a `Trait` with a key of `"Category"` and value of `"CategoryA"` **or** have a `Trait` with a key of `"Priority"` and value of `1`.</span></span>

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

| <span data-ttu-id="cda2e-143">expression</span><span class="sxs-lookup"><span data-stu-id="cda2e-143">Expression</span></span> | <span data-ttu-id="cda2e-144">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="cda2e-144">Result</span></span> |
|--|--|
| `dotnet test --filter Method` | <span data-ttu-id="cda2e-145">Führt Tests aus, dessen <xref:System.Reflection.Module.FullyQualifiedName>`Method` enthält.</span><span class="sxs-lookup"><span data-stu-id="cda2e-145">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `Method`.</span></span> <span data-ttu-id="cda2e-146">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="cda2e-146">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="cda2e-147">Führt Tests aus, dessen Name `TestMethod1` enthält.</span><span class="sxs-lookup"><span data-stu-id="cda2e-147">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="cda2e-148">Führt Tests aus, die sich in der Klasse `NUnitNamespace.UnitTest1` befinden.</span><span class="sxs-lookup"><span data-stu-id="cda2e-148">Runs tests that are in class `NUnitNamespace.UnitTest1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="cda2e-149">Führt alle Tests außer `NUnitNamespace.UnitTest1.TestMethod1` aus.</span><span class="sxs-lookup"><span data-stu-id="cda2e-149">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="cda2e-150">Führt Tests aus, die mit `[Category("CategoryA")]` annotiert sind.</span><span class="sxs-lookup"><span data-stu-id="cda2e-150">Runs tests that are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="cda2e-151">Führt Tests aus, die mit `[Priority(2)]` annotiert sind.</span><span class="sxs-lookup"><span data-stu-id="cda2e-151">Runs tests that are annotated with `[Priority(2)]`.</span></span> |

<span data-ttu-id="cda2e-152">Beispiele für die Verwendung der bedingten Operatoren `|` und `&`:</span><span class="sxs-lookup"><span data-stu-id="cda2e-152">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="cda2e-153">Zum Ausführen von Tests, bei denen `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> enthalten **oder** `Category` `"CategoryA"` ist.</span><span class="sxs-lookup"><span data-stu-id="cda2e-153">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** have a `Category` of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

<span data-ttu-id="cda2e-154">Zum Ausführen von Tests, bei denen `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> enthalten **und** `Category` `"CategoryA"` ist.</span><span class="sxs-lookup"><span data-stu-id="cda2e-154">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a `Category` of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

<span data-ttu-id="cda2e-155">Zum Ausführen von Tests, bei denen entweder <xref:System.Reflection.Module.FullyQualifiedName> `UnitTest1` enthält **und** `Category` `"CategoryA"` ist **oder** `Property` die `"Priority"` `1`hat.</span><span class="sxs-lookup"><span data-stu-id="cda2e-155">To run tests that have either a <xref:System.Reflection.Module.FullyQualifiedName> containing `UnitTest1` **and** have a `Category` of `"CategoryA"` **or** have a `Property` with a `"Priority"` of `1`.</span></span>

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

<span data-ttu-id="cda2e-156">Weitere Informationen finden Sie unter [TestCase-Filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="cda2e-156">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

:::zone-end

## <a name="see-also"></a><span data-ttu-id="cda2e-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cda2e-157">See also</span></span>

- [<span data-ttu-id="cda2e-158">dotnet test</span><span class="sxs-lookup"><span data-stu-id="cda2e-158">dotnet test</span></span>](../tools/dotnet-test.md)
- [<span data-ttu-id="cda2e-159">dotnet test --filter</span><span class="sxs-lookup"><span data-stu-id="cda2e-159">dotnet test --filter</span></span>](../tools/dotnet-test.md#filter-option-details)

## <a name="next-steps"></a><span data-ttu-id="cda2e-160">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cda2e-160">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cda2e-161">Festlegen einer Reihenfolge von Komponententests</span><span class="sxs-lookup"><span data-stu-id="cda2e-161">Order unit tests</span></span>](order-unit-tests.md)
