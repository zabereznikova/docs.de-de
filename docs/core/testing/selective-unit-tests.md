---
title: Ausführen von selektiven Komponententests – .NET Core
description: Es wird erläutert, wie Sie einen Filterausdruck zum Ausführen selektiver Komponententests mit dem dotnet-Testbefehl in .NET Core verwenden.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.custom: seodec18
ms.openlocfilehash: 3c24fb8cc5024399ae523801373b0fd8eff85f45
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151745"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="8473f-103">Ausführen von selektiven Komponententests</span><span class="sxs-lookup"><span data-stu-id="8473f-103">Running selective unit tests</span></span>

<span data-ttu-id="8473f-104">Die folgenden Beispiele verwenden `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="8473f-104">The following examples use `dotnet test`.</span></span> <span data-ttu-id="8473f-105">Wenn Sie `vstest.console.exe` verwenden, ersetzen Sie `--filter ` mit `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="8473f-105">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="8473f-106">MSTest</span><span class="sxs-lookup"><span data-stu-id="8473f-106">MSTest</span></span>

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

| <span data-ttu-id="8473f-107">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="8473f-107">Expression</span></span> | <span data-ttu-id="8473f-108">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="8473f-108">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="8473f-109">Führt Tests aus, dessen `FullyQualifiedName` `Method` enthält.</span><span class="sxs-lookup"><span data-stu-id="8473f-109">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="8473f-110">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="8473f-110">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="8473f-111">Führt Tests aus, dessen Name `TestMethod1` enthält.</span><span class="sxs-lookup"><span data-stu-id="8473f-111">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="8473f-112">Führt Tests aus, die sich in der Klasse `MSTestNamespace.UnitTest1` befinden.</span><span class="sxs-lookup"><span data-stu-id="8473f-112">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="8473f-113">**Hinweis:** Der Wert `ClassName` muss einen Namespace besitzen, damit `ClassName=UnitTest1` nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="8473f-113">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="8473f-114">Führt alle Tests außer `MSTestNamespace.UnitTest1.TestMethod1` aus.</span><span class="sxs-lookup"><span data-stu-id="8473f-114">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="8473f-115">Führt Tests aus, die mit `[TestCategory("CategoryA")]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="8473f-115">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="8473f-116">Führt Tests aus, die mit `[Priority(2)]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="8473f-116">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="8473f-117">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="8473f-117">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="8473f-118">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="8473f-118">Expression</span></span> | <span data-ttu-id="8473f-119">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="8473f-119">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="8473f-120">Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` besitzen, **oder** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="8473f-120">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="8473f-121">Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` besitzen, **und** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="8473f-121">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="8473f-122">Führt Tests aus, in denen `FullyQualifiedName` entweder `UnitTest1` enthalten ist, **und** `TestCategory` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="8473f-122">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="8473f-123">xUnit</span><span class="sxs-lookup"><span data-stu-id="8473f-123">xUnit</span></span>

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

| <span data-ttu-id="8473f-124">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="8473f-124">Expression</span></span> | <span data-ttu-id="8473f-125">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="8473f-125">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="8473f-126">Führt einen Test, `XUnitNamespace.TestClass1.Test1`, aus.</span><span class="sxs-lookup"><span data-stu-id="8473f-126">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="8473f-127">Führt alle Tests außer `XUnitNamespace.TestClass1.Test1` aus.</span><span class="sxs-lookup"><span data-stu-id="8473f-127">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="8473f-128">Führt Tests aus, dessen Anzeigename `TestClass1` enthält.</span><span class="sxs-lookup"><span data-stu-id="8473f-128">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="8473f-129">Im Codebeispiel können die definierten Merkmale mit den Schlüsseln `Category` und `Priority` zum Filtern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8473f-129">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="8473f-130">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="8473f-130">Expression</span></span> | <span data-ttu-id="8473f-131">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="8473f-131">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="8473f-132">Führt Tests aus, dessen `FullyQualifiedName` `XUnit` enthält.</span><span class="sxs-lookup"><span data-stu-id="8473f-132">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="8473f-133">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="8473f-133">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="8473f-134">Führt Tests aus, die `[Trait("Category", "CategoryA")]` besitzen.</span><span class="sxs-lookup"><span data-stu-id="8473f-134">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="8473f-135">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="8473f-135">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="8473f-136">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="8473f-136">Expression</span></span> | <span data-ttu-id="8473f-137">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="8473f-137">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="8473f-138">Führt Tests aus, die `TestClass1` in `FullyQualifiedName` besitzen, **oder** `Category` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="8473f-138">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="8473f-139">Führt Tests aus, die `TestClass1` in `FullyQualifiedName` besitzen, **und** `Category` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="8473f-139">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="8473f-140">Führt Tests aus, in denen `FullyQualifiedName` entweder `TestClass1` enthalten ist, **und** `Category` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="8473f-140">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="8473f-141">NUnit</span><span class="sxs-lookup"><span data-stu-id="8473f-141">NUnit</span></span>

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

| <span data-ttu-id="8473f-142">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="8473f-142">Expression</span></span> | <span data-ttu-id="8473f-143">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="8473f-143">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="8473f-144">Führt Tests aus, dessen `FullyQualifiedName` `Method` enthält.</span><span class="sxs-lookup"><span data-stu-id="8473f-144">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="8473f-145">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="8473f-145">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="8473f-146">Führt Tests aus, dessen Name `TestMethod1` enthält.</span><span class="sxs-lookup"><span data-stu-id="8473f-146">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="8473f-147">Führt Tests aus, die sich in der Klasse `NUnitNamespace.UnitTest1` befinden.</span><span class="sxs-lookup"><span data-stu-id="8473f-147">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="8473f-148">Führt alle Tests außer `NUnitNamespace.UnitTest1.TestMethod1` aus.</span><span class="sxs-lookup"><span data-stu-id="8473f-148">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="8473f-149">Führt Tests aus, die mit `[Category("CategoryA")]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="8473f-149">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="8473f-150">Führt Tests aus, die mit `[Priority(2)]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="8473f-150">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="8473f-151">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="8473f-151">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="8473f-152">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="8473f-152">Expression</span></span> | <span data-ttu-id="8473f-153">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="8473f-153">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="8473f-154">Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` besitzen, **oder** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="8473f-154">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="8473f-155">Führt Tests aus, die `UnitTest1` in `FullyQualifiedName` besitzen, **und** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="8473f-155">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="8473f-156">Führt Tests aus, in denen `FullyQualifiedName` entweder `UnitTest1` enthalten ist, **und** `TestCategory` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="8473f-156">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
