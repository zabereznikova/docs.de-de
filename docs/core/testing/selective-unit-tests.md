---
title: Ausführen von selektiven Komponententests
description: Es wird erläutert, wie Sie einen Filterausdruck zum Ausführen selektiver Komponententests mit dem dotnet-Testbefehl in .NET Core verwenden.
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: 57428dad2de6c2507ca2cdc42e3df9e83a1edd69
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715460"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="2c619-103">Ausführen von selektiven Komponententests</span><span class="sxs-lookup"><span data-stu-id="2c619-103">Running selective unit tests</span></span>

<span data-ttu-id="2c619-104">Mit dem Befehl `dotnet test` in .NET Core können Sie einen Filterausdruck zum Ausführen selektiver Tests verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c619-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="2c619-105">In diesem Artikel wird gezeigt, wie Sie die auszuführenden Tests filtern.</span><span class="sxs-lookup"><span data-stu-id="2c619-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="2c619-106">Die folgenden Beispiele verwenden `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="2c619-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="2c619-107">Wenn Sie `vstest.console.exe` verwenden, ersetzen Sie `--filter` mit `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="2c619-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="2c619-108">MSTest</span><span class="sxs-lookup"><span data-stu-id="2c619-108">MSTest</span></span>

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

| <span data-ttu-id="2c619-109">expression</span><span class="sxs-lookup"><span data-stu-id="2c619-109">Expression</span></span> | <span data-ttu-id="2c619-110">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="2c619-110">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="2c619-111">Führt Tests aus, dessen `FullyQualifiedName``Method` enthält.</span><span class="sxs-lookup"><span data-stu-id="2c619-111">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="2c619-112">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="2c619-112">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="2c619-113">Führt Tests aus, dessen Name `TestMethod1` enthält.</span><span class="sxs-lookup"><span data-stu-id="2c619-113">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="2c619-114">Führt Tests aus, die sich in der Klasse `MSTestNamespace.UnitTest1` befinden.</span><span class="sxs-lookup"><span data-stu-id="2c619-114">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="2c619-115">**Hinweis**: Der Wert `ClassName` muss einen Namespace besitzen, damit `ClassName=UnitTest1` nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2c619-115">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="2c619-116">Führt alle Tests außer `MSTestNamespace.UnitTest1.TestMethod1` aus.</span><span class="sxs-lookup"><span data-stu-id="2c619-116">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="2c619-117">Führt Tests aus, die mit `[TestCategory("CategoryA")]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="2c619-117">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="2c619-118">Führt Tests aus, die mit `[Priority(2)]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="2c619-118">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="2c619-119">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="2c619-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="2c619-120">expression</span><span class="sxs-lookup"><span data-stu-id="2c619-120">Expression</span></span> | <span data-ttu-id="2c619-121">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="2c619-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="2c619-122">Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` aufweisen, **oder** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="2c619-122">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="2c619-123">Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` aufweisen, **und** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="2c619-123">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="2c619-124">Führt Tests aus, in denen `FullyQualifiedName` entweder `UnitTest1` enthält, **und** `TestCategory` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="2c619-124">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="2c619-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="2c619-125">xUnit</span></span>

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

| <span data-ttu-id="2c619-126">expression</span><span class="sxs-lookup"><span data-stu-id="2c619-126">Expression</span></span> | <span data-ttu-id="2c619-127">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="2c619-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="2c619-128">Führt einen Test, `XUnitNamespace.TestClass1.Test1`, aus.</span><span class="sxs-lookup"><span data-stu-id="2c619-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="2c619-129">Führt alle Tests außer `XUnitNamespace.TestClass1.Test1` aus.</span><span class="sxs-lookup"><span data-stu-id="2c619-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="2c619-130">Führt Tests aus, dessen Anzeigename `TestClass1` enthält.</span><span class="sxs-lookup"><span data-stu-id="2c619-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="2c619-131">Im Codebeispiel können die definierten Merkmale mit den Schlüsseln `Category` und `Priority` zum Filtern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c619-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="2c619-132">expression</span><span class="sxs-lookup"><span data-stu-id="2c619-132">Expression</span></span> | <span data-ttu-id="2c619-133">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="2c619-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="2c619-134">Führt Tests aus, dessen `FullyQualifiedName``XUnit` enthält.</span><span class="sxs-lookup"><span data-stu-id="2c619-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="2c619-135">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="2c619-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="2c619-136">Führt Tests aus, die `[Trait("Category", "CategoryA")]` besitzen.</span><span class="sxs-lookup"><span data-stu-id="2c619-136">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="2c619-137">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="2c619-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="2c619-138">expression</span><span class="sxs-lookup"><span data-stu-id="2c619-138">Expression</span></span> | <span data-ttu-id="2c619-139">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="2c619-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="2c619-140">Führt Tests aus, die `TestClass1` in `FullyQualifiedName` aufweisen, **oder** `Category` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="2c619-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="2c619-141">Führt Tests aus, die `TestClass1` in `FullyQualifiedName` aufweisen, **und** `Category` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="2c619-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="2c619-142">Führt Tests aus, in denen `FullyQualifiedName` entweder `TestClass1` aufweist, **und** `Category` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="2c619-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="2c619-143">NUnit</span><span class="sxs-lookup"><span data-stu-id="2c619-143">NUnit</span></span>

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

| <span data-ttu-id="2c619-144">expression</span><span class="sxs-lookup"><span data-stu-id="2c619-144">Expression</span></span> | <span data-ttu-id="2c619-145">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="2c619-145">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="2c619-146">Führt Tests aus, dessen `FullyQualifiedName``Method` enthält.</span><span class="sxs-lookup"><span data-stu-id="2c619-146">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="2c619-147">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="2c619-147">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="2c619-148">Führt Tests aus, dessen Name `TestMethod1` enthält.</span><span class="sxs-lookup"><span data-stu-id="2c619-148">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="2c619-149">Führt Tests aus, die sich in der Klasse `NUnitNamespace.UnitTest1` befinden.</span><span class="sxs-lookup"><span data-stu-id="2c619-149">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="2c619-150">Führt alle Tests außer `NUnitNamespace.UnitTest1.TestMethod1` aus.</span><span class="sxs-lookup"><span data-stu-id="2c619-150">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="2c619-151">Führt Tests aus, die mit `[Category("CategoryA")]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="2c619-151">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="2c619-152">Führt Tests aus, die mit `[Priority(2)]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="2c619-152">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="2c619-153">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="2c619-153">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="2c619-154">expression</span><span class="sxs-lookup"><span data-stu-id="2c619-154">Expression</span></span> | <span data-ttu-id="2c619-155">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="2c619-155">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="2c619-156">Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` aufweisen, **oder** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="2c619-156">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="2c619-157">Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` aufweisen, **und** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="2c619-157">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="2c619-158">Führt Tests aus, in denen `FullyQualifiedName` entweder `UnitTest1` enthält, **und** `TestCategory` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="2c619-158">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
