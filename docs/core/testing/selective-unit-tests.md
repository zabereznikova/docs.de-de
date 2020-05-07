---
title: Ausführen von selektiven Komponententests
description: Es wird erläutert, wie Sie einen Filterausdruck zum Ausführen selektiver Komponententests mit dem dotnet-Testbefehl in .NET Core verwenden.
author: smadala
ms.date: 04/29/2020
ms.openlocfilehash: 50642126f3b470180ddd303ed4a2d2d90bfa5b8f
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728181"
---
# <a name="run-selective-unit-tests"></a><span data-ttu-id="bbf7b-103">Ausführen selektiver Komponententests</span><span class="sxs-lookup"><span data-stu-id="bbf7b-103">Run selective unit tests</span></span>

<span data-ttu-id="bbf7b-104">Mit dem Befehl `dotnet test` in .NET Core können Sie einen Filterausdruck zum Ausführen selektiver Tests verwenden.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="bbf7b-105">In diesem Artikel wird gezeigt, wie Sie die auszuführenden Tests filtern.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-105">This article demonstrates how to filter which tests are run.</span></span> <span data-ttu-id="bbf7b-106">Die folgenden Beispiele verwenden `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="bbf7b-107">Wenn Sie `vstest.console.exe` verwenden, ersetzen Sie `--filter` mit `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="bbf7b-108">Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="bbf7b-108">Character escaping</span></span>

<span data-ttu-id="bbf7b-109">Die Verwendung von Filtern, die in `*nix` ein Ausrufezeichen (!) enthalten, erfordert Escapezeichen, da `!` reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-109">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="bbf7b-110">Dieser Filter überspringt beispielsweise alle Tests, wenn der Namespace IntegrationTests enthält: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-110">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
<span data-ttu-id="bbf7b-111">Beachten Sie den umgekehrten Schrägstrich, der dem Ausrufezeichen vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-111">Note the backslash that precedes the exclamation mark.</span></span>

<span data-ttu-id="bbf7b-112">Für `FullyQualifiedName`-Werte, die ein Komma für generische Typparameter enthalten, versehen Sie das Komma mit dem Escapezeichen `%2C`.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="bbf7b-113">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bbf7b-113">For example:</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

## <a name="mstest"></a><span data-ttu-id="bbf7b-114">MSTest</span><span class="sxs-lookup"><span data-stu-id="bbf7b-114">MSTest</span></span>

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

| <span data-ttu-id="bbf7b-115">expression</span><span class="sxs-lookup"><span data-stu-id="bbf7b-115">Expression</span></span> | <span data-ttu-id="bbf7b-116">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="bbf7b-116">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="bbf7b-117">Führt Tests aus, dessen `FullyQualifiedName``Method` enthält.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-117">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="bbf7b-118">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-118">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="bbf7b-119">Führt Tests aus, dessen Name `TestMethod1` enthält.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-119">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="bbf7b-120">Führt Tests aus, die sich in der Klasse `MSTestNamespace.UnitTest1` befinden.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-120">Runs tests that are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="bbf7b-121">**Hinweis**: Der Wert `ClassName` muss einen Namespace besitzen, damit `ClassName=UnitTest1` nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-121">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="bbf7b-122">Führt alle Tests außer `MSTestNamespace.UnitTest1.TestMethod1` aus.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-122">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="bbf7b-123">Führt Tests aus, die mit `[TestCategory("CategoryA")]` annotiert sind.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-123">Runs tests that are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="bbf7b-124">Führt Tests aus, die mit `[Priority(2)]` annotiert sind.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-124">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="bbf7b-125">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="bbf7b-125">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="bbf7b-126">expression</span><span class="sxs-lookup"><span data-stu-id="bbf7b-126">Expression</span></span> | <span data-ttu-id="bbf7b-127">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="bbf7b-127">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="bbf7b-128">Führt Tests aus, bei denen `UnitTest1` sich in `FullyQualifiedName` befindet **oder** bei denen `TestCategory` `CategoryA` ist.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-128">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="bbf7b-129">Führt Tests aus, bei denen `UnitTest1` sich in `FullyQualifiedName` befindet **und** bei denen `TestCategory` `CategoryA` ist.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-129">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="bbf7b-130">Führt Tests aus, bei denen entweder `FullyQualifiedName` `UnitTest1` enthält **und** `TestCategory` `CategoryA` ist **oder** bei denen `Priority` 1 ist.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-130">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="bbf7b-131">xUnit</span><span class="sxs-lookup"><span data-stu-id="bbf7b-131">xUnit</span></span>

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

| <span data-ttu-id="bbf7b-132">expression</span><span class="sxs-lookup"><span data-stu-id="bbf7b-132">Expression</span></span> | <span data-ttu-id="bbf7b-133">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="bbf7b-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="bbf7b-134">Führt einen Test, `XUnitNamespace.TestClass1.Test1`, aus.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-134">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="bbf7b-135">Führt alle Tests außer `XUnitNamespace.TestClass1.Test1` aus.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-135">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="bbf7b-136">Führt Tests aus, dessen Anzeigename `TestClass1` enthält.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-136">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="bbf7b-137">Im Codebeispiel können die definierten Merkmale mit den Schlüsseln `Category` und `Priority` zum Filtern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-137">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="bbf7b-138">expression</span><span class="sxs-lookup"><span data-stu-id="bbf7b-138">Expression</span></span> | <span data-ttu-id="bbf7b-139">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="bbf7b-139">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="bbf7b-140">Führt Tests aus, dessen `FullyQualifiedName``XUnit` enthält.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-140">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="bbf7b-141">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-141">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="bbf7b-142">Führt Tests aus, die `[Trait("Category", "CategoryA")]` enthalten.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-142">Runs tests that have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="bbf7b-143">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="bbf7b-143">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="bbf7b-144">expression</span><span class="sxs-lookup"><span data-stu-id="bbf7b-144">Expression</span></span> | <span data-ttu-id="bbf7b-145">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="bbf7b-145">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="bbf7b-146">Führt Tests aus, bei denen `TestClass1` sich in `FullyQualifiedName` befindet **oder** bei denen `Category` `CategoryA` ist.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-146">Runs tests that have `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="bbf7b-147">Führt Tests aus, bei denen `TestClass1` sich in `FullyQualifiedName` befindet **und** bei denen `Category` `CategoryA` ist.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-147">Runs tests that have `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="bbf7b-148">Führt Tests aus, bei denen entweder `FullyQualifiedName` `TestClass1` enthält **und** `Category` `CategoryA` ist **oder** bei denen `Priority` 1 ist.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-148">Runs tests that have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="bbf7b-149">NUnit</span><span class="sxs-lookup"><span data-stu-id="bbf7b-149">NUnit</span></span>

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

| <span data-ttu-id="bbf7b-150">expression</span><span class="sxs-lookup"><span data-stu-id="bbf7b-150">Expression</span></span> | <span data-ttu-id="bbf7b-151">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="bbf7b-151">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="bbf7b-152">Führt Tests aus, dessen `FullyQualifiedName``Method` enthält.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-152">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="bbf7b-153">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-153">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="bbf7b-154">Führt Tests aus, dessen Name `TestMethod1` enthält.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-154">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="bbf7b-155">Führt Tests aus, die sich in der Klasse `NUnitNamespace.UnitTest1` befinden.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-155">Runs tests that are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="bbf7b-156">Führt alle Tests außer `NUnitNamespace.UnitTest1.TestMethod1` aus.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-156">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="bbf7b-157">Führt Tests aus, die mit `[Category("CategoryA")]` annotiert sind.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-157">Runs tests that are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="bbf7b-158">Führt Tests aus, die mit `[Priority(2)]` annotiert sind.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-158">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="bbf7b-159">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="bbf7b-159">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="bbf7b-160">expression</span><span class="sxs-lookup"><span data-stu-id="bbf7b-160">Expression</span></span> | <span data-ttu-id="bbf7b-161">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="bbf7b-161">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="bbf7b-162">Führt Tests aus, bei denen `UnitTest1` sich in `FullyQualifiedName` befindet **oder** bei denen `TestCategory` `CategoryA` ist.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-162">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="bbf7b-163">Führt Tests aus, bei denen `UnitTest1` sich in `FullyQualifiedName` befindet **und** bei denen `TestCategory` `CategoryA` ist.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-163">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="bbf7b-164">Führt Tests aus, bei denen entweder `FullyQualifiedName` `UnitTest1` enthält **und** `TestCategory` `CategoryA` ist **oder** bei denen `Priority` 1 ist.</span><span class="sxs-lookup"><span data-stu-id="bbf7b-164">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

<span data-ttu-id="bbf7b-165">Weitere Informationen finden Sie unter [TestCase-Filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="bbf7b-165">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>
