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
ms.openlocfilehash: af832d04d2cba530a93710a90701ab119a66deef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="3981c-104">Ausführen von selektiven Komponententests</span><span class="sxs-lookup"><span data-stu-id="3981c-104">Running selective unit tests</span></span>

<span data-ttu-id="3981c-105">Die folgenden Beispiele verwenden `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="3981c-105">The following examples use `dotnet test`.</span></span> <span data-ttu-id="3981c-106">Wenn Sie `vstest.console.exe` verwenden, ersetzen Sie `--filter ` mit `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="3981c-106">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="3981c-107">MSTest</span><span class="sxs-lookup"><span data-stu-id="3981c-107">MSTest</span></span>

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

| <span data-ttu-id="3981c-108">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="3981c-108">Expression</span></span> | <span data-ttu-id="3981c-109">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="3981c-109">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="3981c-110">Führt Tests aus, dessen `FullyQualifiedName` `Method` enthält.</span><span class="sxs-lookup"><span data-stu-id="3981c-110">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="3981c-111">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="3981c-111">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="3981c-112">Führt Tests aus, dessen Name `TestMethod1` enthält.</span><span class="sxs-lookup"><span data-stu-id="3981c-112">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="3981c-113">Führt Tests aus, die sich in der Klasse `MSTestNamespace.UnitTestClass1` befinden.</span><span class="sxs-lookup"><span data-stu-id="3981c-113">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="3981c-114">**Hinweis:** Der Wert `ClassName` muss einen Namespace besitzen, damit `ClassName=UnitTestClass1` nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3981c-114">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="3981c-115">Führt alle Tests außer `MSTestNamespace.UnitTestClass1.TestMethod1` aus.</span><span class="sxs-lookup"><span data-stu-id="3981c-115">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="3981c-116">Führt Tests aus, die mit `[TestCategory("CategoryA")]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="3981c-116">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="3981c-117">Führt Tests aus, die mit `[Priority(3)]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="3981c-117">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="3981c-118">**Hinweis:** `Priority~3` ist ein ungültiger Wert, da er keine Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="3981c-118">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="3981c-119">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="3981c-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="3981c-120">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="3981c-120">Expression</span></span> | <span data-ttu-id="3981c-121">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="3981c-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="3981c-122">Führt Tests aus, die `UnitTestClass1` in `FullyQualifiedName` besitzen, **oder** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="3981c-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="3981c-123">Führt Tests aus, die `UnitTestClass1` in `FullyQualifiedName` besitzen, **und** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="3981c-123">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="3981c-124">Führt Tests aus, in denen `FullyQualifiedName` entweder `UnitTestClass1` enthalten ist, **und** `TestCategory` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="3981c-124">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="3981c-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="3981c-125">xUnit</span></span>

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

| <span data-ttu-id="3981c-126">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="3981c-126">Expression</span></span> | <span data-ttu-id="3981c-127">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="3981c-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="3981c-128">Führt einen Test, `XUnitNamespace.TestClass1.Test1`, aus.</span><span class="sxs-lookup"><span data-stu-id="3981c-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="3981c-129">Führt alle Tests außer `XUnitNamespace.TestClass1.Test1` aus.</span><span class="sxs-lookup"><span data-stu-id="3981c-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="3981c-130">Führt Tests aus, dessen Anzeigename `TestClass1` enthält.</span><span class="sxs-lookup"><span data-stu-id="3981c-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="3981c-131">Im Codebeispiel können die definierten Merkmale mit den Schlüsseln `Category` und `Priority` zum Filtern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3981c-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="3981c-132">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="3981c-132">Expression</span></span> | <span data-ttu-id="3981c-133">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="3981c-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="3981c-134">Führt Tests aus, dessen `FullyQualifiedName` `XUnit` enthält.</span><span class="sxs-lookup"><span data-stu-id="3981c-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="3981c-135">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="3981c-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="3981c-136">Führt Tests aus, die `[Trait("Category", "bvt")]` besitzen.</span><span class="sxs-lookup"><span data-stu-id="3981c-136">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="3981c-137">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="3981c-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="3981c-138">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="3981c-138">Expression</span></span> | <span data-ttu-id="3981c-139">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="3981c-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="3981c-140">Führt Tests aus, die `TestClass1` in `FullyQualifiedName` besitzen, **oder** `Category` ist `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="3981c-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="3981c-141">Führt Tests aus, die `TestClass1` in `FullyQualifiedName` besitzen, **und** `Category` ist `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="3981c-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="3981c-142">Führt Tests aus, in denen `FullyQualifiedName` entweder `TestClass1` enthalten ist, **und** `Category` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="3981c-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |
