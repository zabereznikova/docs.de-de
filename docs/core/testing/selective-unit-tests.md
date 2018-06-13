---
title: Ausführen von selektiven Komponententests
description: Zeigt, wie Sie einen Filterausdruck zum Ausführen selektiver Komponententests mit dem dotnet-Testbefehl verwenden.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.openlocfilehash: caea91e9884dba6bc07a7ef6a99699e43d23399c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33210833"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="bd5ef-103">Ausführen von selektiven Komponententests</span><span class="sxs-lookup"><span data-stu-id="bd5ef-103">Running selective unit tests</span></span>

<span data-ttu-id="bd5ef-104">Die folgenden Beispiele verwenden `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-104">The following examples use `dotnet test`.</span></span> <span data-ttu-id="bd5ef-105">Wenn Sie `vstest.console.exe` verwenden, ersetzen Sie `--filter ` mit `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-105">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="bd5ef-106">MSTest</span><span class="sxs-lookup"><span data-stu-id="bd5ef-106">MSTest</span></span>

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

| <span data-ttu-id="bd5ef-107">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="bd5ef-107">Expression</span></span> | <span data-ttu-id="bd5ef-108">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="bd5ef-108">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="bd5ef-109">Führt Tests aus, dessen `FullyQualifiedName` `Method` enthält.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-109">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="bd5ef-110">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-110">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="bd5ef-111">Führt Tests aus, dessen Name `TestMethod1` enthält.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-111">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="bd5ef-112">Führt Tests aus, die sich in der Klasse `MSTestNamespace.UnitTestClass1` befinden.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-112">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="bd5ef-113">**Hinweis:** Der Wert `ClassName` muss einen Namespace besitzen, damit `ClassName=UnitTestClass1` nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-113">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="bd5ef-114">Führt alle Tests außer `MSTestNamespace.UnitTestClass1.TestMethod1` aus.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-114">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="bd5ef-115">Führt Tests aus, die mit `[TestCategory("CategoryA")]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-115">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="bd5ef-116">Führt Tests aus, die mit `[Priority(3)]` kommentiert sind.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-116">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="bd5ef-117">**Hinweis:** `Priority~3` ist ein ungültiger Wert, da er keine Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-117">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="bd5ef-118">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="bd5ef-118">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="bd5ef-119">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="bd5ef-119">Expression</span></span> | <span data-ttu-id="bd5ef-120">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="bd5ef-120">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="bd5ef-121">Führt Tests aus, die `UnitTestClass1` in `FullyQualifiedName` besitzen, **oder** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-121">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="bd5ef-122">Führt Tests aus, die `UnitTestClass1` in `FullyQualifiedName` besitzen, **und** `TestCategory` ist `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="bd5ef-123">Führt Tests aus, in denen `FullyQualifiedName` entweder `UnitTestClass1` enthalten ist, **und** `TestCategory` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-123">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="bd5ef-124">xUnit</span><span class="sxs-lookup"><span data-stu-id="bd5ef-124">xUnit</span></span>

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

| <span data-ttu-id="bd5ef-125">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="bd5ef-125">Expression</span></span> | <span data-ttu-id="bd5ef-126">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="bd5ef-126">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="bd5ef-127">Führt einen Test, `XUnitNamespace.TestClass1.Test1`, aus.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-127">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="bd5ef-128">Führt alle Tests außer `XUnitNamespace.TestClass1.Test1` aus.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-128">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="bd5ef-129">Führt Tests aus, dessen Anzeigename `TestClass1` enthält.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-129">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="bd5ef-130">Im Codebeispiel können die definierten Merkmale mit den Schlüsseln `Category` und `Priority` zum Filtern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-130">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="bd5ef-131">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="bd5ef-131">Expression</span></span> | <span data-ttu-id="bd5ef-132">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="bd5ef-132">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="bd5ef-133">Führt Tests aus, dessen `FullyQualifiedName` `XUnit` enthält.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-133">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="bd5ef-134">Verfügbar in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-134">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="bd5ef-135">Führt Tests aus, die `[Trait("Category", "bvt")]` besitzen.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-135">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="bd5ef-136">**Verwenden bedingter Operatoren | und&amp;**</span><span class="sxs-lookup"><span data-stu-id="bd5ef-136">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="bd5ef-137">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="bd5ef-137">Expression</span></span> | <span data-ttu-id="bd5ef-138">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="bd5ef-138">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="bd5ef-139">Führt Tests aus, die `TestClass1` in `FullyQualifiedName` besitzen, **oder** `Category` ist `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-139">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="bd5ef-140">Führt Tests aus, die `TestClass1` in `FullyQualifiedName` besitzen, **und** `Category` ist `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="bd5ef-141">Führt Tests aus, in denen `FullyQualifiedName` entweder `TestClass1` enthalten ist, **und** `Category` ist `CategoryA`, **oder** `Priority` ist 1.</span><span class="sxs-lookup"><span data-stu-id="bd5ef-141">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |
