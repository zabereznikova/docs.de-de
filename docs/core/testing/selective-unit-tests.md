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
# <a name="running-selective-unit-tests"></a><span data-ttu-id="21a85-103">Ausführen von selektiven Komponententests</span><span class="sxs-lookup"><span data-stu-id="21a85-103">Running selective unit tests</span></span>

<span data-ttu-id="21a85-104">Mit dem Befehl `dotnet test` in .NET Core können Sie einen Filterausdruck zum Ausführen selektiver Tests verwenden.</span><span class="sxs-lookup"><span data-stu-id="21a85-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="21a85-105">In diesem Artikel wird gezeigt, wie Sie die auszuführenden Tests filtern.</span><span class="sxs-lookup"><span data-stu-id="21a85-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="21a85-106">Die folgenden Beispiele verwenden `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="21a85-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="21a85-107">Wenn Sie `vstest.console.exe` verwenden, ersetzen Sie `--filter` mit `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="21a85-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

> [!NOTE]
> <span data-ttu-id="21a85-108">Die Verwendung von Filtern, die in `*nix` ein Ausrufezeichen (!) enthalten, erfordert Escapezeichen, da `!` reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="21a85-108">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="21a85-109">Dieser Filter überspringt beispielsweise alle Tests, wenn der Namespace IntegrationTests enthält: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span><span class="sxs-lookup"><span data-stu-id="21a85-109">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
> <span data-ttu-id="21a85-110">Beachten Sie den umgekehrten Schrägstrich, der dem Ausrufezeichen vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="21a85-110">Note the backslash that precedes the exclamation mark.</span></span>

## <a name="mstest"></a><span data-ttu-id="21a85-111">MSTest</span><span class="sxs-lookup"><span data-stu-id="21a85-111">MSTest</span></span>

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

| <span data-ttu-id="21a85-112">expression</span><span class="sxs-lookup"><span data-stu-id="21a85-112">Expression</span></span> | <span data-ttu-id="21a85-113">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="21a85-113">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="21a85-114">Führt Tests aus, dessen `FullyQualifiedName``Method` enthält.</span><span class="sxs-lookup"><span data-stu-id="21a85-114">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="21a85-115">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="21a85-115">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="21a85-116">Führt Tests aus, dessen Name `TestMethod1` enthält.</span><span class="sxs-lookup"><span data-stu-id="21a85-116">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="21a85-117">Führt Tests aus, die sich in der Klasse `MSTestNamespace.UnitTest1` befinden.</span><span class="sxs-lookup"><span data-stu-id="21a85-117">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="21a85-118">**Hinweis:** Der Wert `ClassName` muss einen Namespace besitzen, damit `ClassName=UnitTest1` nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="21a85-118">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="21a85-119">Führt alle Tests außer `MSTestNamespace.UnitTest1.TestMethod1` aus.</span><span class="sxs-lookup"><span data-stu-id="21a85-119">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="21a85-120">Führt Tests aus, die mit `[TestCategory("CategoryA")]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="21a85-120">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="21a85-121">Führt Tests aus, die mit `[Priority(2)]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="21a85-121">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="21a85-122">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="21a85-122">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="21a85-123">expression</span><span class="sxs-lookup"><span data-stu-id="21a85-123">Expression</span></span> | <span data-ttu-id="21a85-124">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="21a85-124">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="21a85-125">Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` aufweisen, **oder** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="21a85-125">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="21a85-126">Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` aufweisen, **und** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="21a85-126">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="21a85-127">Führt Tests aus, in denen `FullyQualifiedName` entweder `UnitTest1` enthält, **und** `TestCategory` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="21a85-127">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="21a85-128">xUnit</span><span class="sxs-lookup"><span data-stu-id="21a85-128">xUnit</span></span>

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

| <span data-ttu-id="21a85-129">expression</span><span class="sxs-lookup"><span data-stu-id="21a85-129">Expression</span></span> | <span data-ttu-id="21a85-130">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="21a85-130">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="21a85-131">Führt einen Test, `XUnitNamespace.TestClass1.Test1`, aus.</span><span class="sxs-lookup"><span data-stu-id="21a85-131">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="21a85-132">Führt alle Tests außer `XUnitNamespace.TestClass1.Test1` aus.</span><span class="sxs-lookup"><span data-stu-id="21a85-132">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="21a85-133">Führt Tests aus, dessen Anzeigename `TestClass1` enthält.</span><span class="sxs-lookup"><span data-stu-id="21a85-133">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="21a85-134">Im Codebeispiel können die definierten Merkmale mit den Schlüsseln `Category` und `Priority` zum Filtern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21a85-134">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="21a85-135">expression</span><span class="sxs-lookup"><span data-stu-id="21a85-135">Expression</span></span> | <span data-ttu-id="21a85-136">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="21a85-136">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="21a85-137">Führt Tests aus, dessen `FullyQualifiedName``XUnit` enthält.</span><span class="sxs-lookup"><span data-stu-id="21a85-137">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="21a85-138">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="21a85-138">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="21a85-139">Führt Tests aus, die `[Trait("Category", "CategoryA")]` besitzen.</span><span class="sxs-lookup"><span data-stu-id="21a85-139">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="21a85-140">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="21a85-140">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="21a85-141">expression</span><span class="sxs-lookup"><span data-stu-id="21a85-141">Expression</span></span> | <span data-ttu-id="21a85-142">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="21a85-142">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="21a85-143">Führt Tests aus, die `TestClass1` in `FullyQualifiedName` aufweisen, **oder** `Category` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="21a85-143">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="21a85-144">Führt Tests aus, die `TestClass1` in `FullyQualifiedName` aufweisen, **und** `Category` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="21a85-144">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="21a85-145">Führt Tests aus, in denen `FullyQualifiedName` entweder `TestClass1` enthält, **und** `Category` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="21a85-145">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="21a85-146">NUnit</span><span class="sxs-lookup"><span data-stu-id="21a85-146">NUnit</span></span>

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

| <span data-ttu-id="21a85-147">expression</span><span class="sxs-lookup"><span data-stu-id="21a85-147">Expression</span></span> | <span data-ttu-id="21a85-148">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="21a85-148">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="21a85-149">Führt Tests aus, dessen `FullyQualifiedName``Method` enthält.</span><span class="sxs-lookup"><span data-stu-id="21a85-149">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="21a85-150">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="21a85-150">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="21a85-151">Führt Tests aus, dessen Name `TestMethod1` enthält.</span><span class="sxs-lookup"><span data-stu-id="21a85-151">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="21a85-152">Führt Tests aus, die sich in der Klasse `NUnitNamespace.UnitTest1` befinden.</span><span class="sxs-lookup"><span data-stu-id="21a85-152">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="21a85-153">Führt alle Tests außer `NUnitNamespace.UnitTest1.TestMethod1` aus.</span><span class="sxs-lookup"><span data-stu-id="21a85-153">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="21a85-154">Führt Tests aus, die mit `[Category("CategoryA")]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="21a85-154">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="21a85-155">Führt Tests aus, die mit `[Priority(2)]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="21a85-155">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="21a85-156">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="21a85-156">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="21a85-157">expression</span><span class="sxs-lookup"><span data-stu-id="21a85-157">Expression</span></span> | <span data-ttu-id="21a85-158">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="21a85-158">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="21a85-159">Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` aufweisen, **oder** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="21a85-159">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="21a85-160">Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` aufweisen, **und** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="21a85-160">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="21a85-161">Führt Tests aus, in denen `FullyQualifiedName` entweder `UnitTest1` enthält, **und** `TestCategory` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="21a85-161">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
