---
title: Festlegen einer Reihenfolge von Komponententests
description: Erfahren Sie, wie Sie mit .NET Core eine Reihenfolge von Komponententests festlegen.
author: IEvangelist
ms.author: dapine
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: eb426b790e0623b0cf233a763e93d2bd501b8034
ms.sourcegitcommit: 4ad2f8920251f3744240c3b42a443ffbe0a46577
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "86100820"
---
# <a name="order-unit-tests"></a><span data-ttu-id="0d216-103">Festlegen einer Reihenfolge von Komponententests</span><span class="sxs-lookup"><span data-stu-id="0d216-103">Order unit tests</span></span>

<span data-ttu-id="0d216-104">Gelegentlich kann es erforderlich sein, dass Komponententests in einer bestimmten Reihenfolge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0d216-104">Occasionally, you may want to have unit tests run in a specific order.</span></span> <span data-ttu-id="0d216-105">Im Idealfall sollte die Reihenfolge, in der Komponententests ausgeführt werden, _keine_ Rolle spielen, und es ist ein [bewährte Methode](unit-testing-best-practices.md), das Festlegen einer Reihenfolge von Komponententests zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="0d216-105">Ideally, the order in which unit tests run should _not_ matter, and it is [best practice](unit-testing-best-practices.md) to avoid ordering unit tests.</span></span> <span data-ttu-id="0d216-106">Nichtsdestoweniger kann es im Einzelfall erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="0d216-106">Regardless, there may be a need to do so.</span></span> <span data-ttu-id="0d216-107">In diesem Artikel erfahren Sie, wie Sie die Reihenfolge von Komponententests festlegen.</span><span class="sxs-lookup"><span data-stu-id="0d216-107">In that case, this article demonstrates how to order test runs.</span></span>

<span data-ttu-id="0d216-108">Wenn Sie lieber den Quellcode durchsuchen möchten, finden Sie weitere Informationen im Beispielrepository [Festlegen der Reihenfolge von .NET Core-Komponententests](/samples/dotnet/samples/order-unit-tests-cs).</span><span class="sxs-lookup"><span data-stu-id="0d216-108">If you prefer to browse the source code, see the [order .NET Core unit tests](/samples/dotnet/samples/order-unit-tests-cs) sample repository.</span></span>

> [!TIP]
> <span data-ttu-id="0d216-109">Zusätzlich zu den in diesem Artikel beschriebenen Funktionen zum Festlegen der Reihenfolge sollten Sie das [Erstellen benutzerdefinierter Wiedergabelisten mit Visual Studio](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists) als Alternative berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="0d216-109">In addition to the ordering capabilities outlined in this article, consider [creating custom playlists with Visual Studio](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists) as an alternative.</span></span>

:::zone pivot="mstest"

## <a name="order-alphabetically"></a><span data-ttu-id="0d216-110">Alphabetisches Sortieren</span><span class="sxs-lookup"><span data-stu-id="0d216-110">Order alphabetically</span></span>

<span data-ttu-id="0d216-111">Mit MSTest werden Tests automatisch nach ihrem Testnamen geordnet.</span><span class="sxs-lookup"><span data-stu-id="0d216-111">With MSTest, tests are automatically ordered by their test name.</span></span>

> [!NOTE]
> <span data-ttu-id="0d216-112">Ein Test mit dem Namen `Test14` wird vor `Test2` ausgeführt, obwohl die Zahl `2` kleiner als `14` ist.</span><span class="sxs-lookup"><span data-stu-id="0d216-112">A test named `Test14` will run before `Test2` even though the number  `2` is less than `14`.</span></span> <span data-ttu-id="0d216-113">Dies liegt daran, dass beim Festlegen der Reihenfolge der Textname des Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0d216-113">This is because, test name ordering uses the text name of the test.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/MSTest.Project/ByAlphabeticalOrder.cs":::

:::zone-end
:::zone pivot="xunit"

<span data-ttu-id="0d216-114">Das xUnit-Testframework ermöglicht eine höhere Genauigkeit und Steuerung der Testreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="0d216-114">The xUnit test framework allows for more granularity and control of test run order.</span></span> <span data-ttu-id="0d216-115">Sie implementieren die Schnittstellen `ITestCaseOrderer` und `ITestCollectionOrderer`, um die Reihenfolge von Testfällen für eine Klasse oder Testsammlungen zu steuern.</span><span class="sxs-lookup"><span data-stu-id="0d216-115">You implement the `ITestCaseOrderer` and `ITestCollectionOrderer` interfaces to control the order of test cases for a class, or test collections.</span></span>

## <a name="order-by-test-case-alphabetically"></a><span data-ttu-id="0d216-116">Alphabetisches Sortieren nach Testfall</span><span class="sxs-lookup"><span data-stu-id="0d216-116">Order by test case alphabetically</span></span>

<span data-ttu-id="0d216-117">Um Testfälle nach dem Methodennamen zu sortieren, implementieren Sie den `ITestCaseOrderer` und stellen einen Sortiermechanismus bereit.</span><span class="sxs-lookup"><span data-stu-id="0d216-117">To order test cases by their method name, you implement the `ITestCaseOrderer` and provide an ordering mechanism.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/AlphabeticalOrderer.cs":::

<span data-ttu-id="0d216-118">In einer Testklasse legen Sie dann die Testfallreihenfolge mit dem `TestCaseOrdererAttribute` fest.</span><span class="sxs-lookup"><span data-stu-id="0d216-118">Then in a test class you set the test case order with the `TestCaseOrdererAttribute`.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByAlphabeticalOrder.cs":::

## <a name="order-by-collection-alphabetically"></a><span data-ttu-id="0d216-119">Alphabetisches Sortieren nach Sammlung</span><span class="sxs-lookup"><span data-stu-id="0d216-119">Order by collection alphabetically</span></span>

<span data-ttu-id="0d216-120">Um Testsammlungen nach dem Anzeigenamen zu sortieren, implementieren Sie den `ITestCollectionOrderer` und stellen einen Sortiermechanismus bereit.</span><span class="sxs-lookup"><span data-stu-id="0d216-120">To order test collections by their display name, you implement the `ITestCollectionOrderer` and provide an ordering mechanism.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/DisplayNameOrderer.cs":::

<span data-ttu-id="0d216-121">Da Testsammlungen möglicherweise parallel ausgeführt werden, müssen Sie die Testparallelisierung der Sammlungen mit dem `CollectionBehaviorAttribute` explizit deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0d216-121">Since test collections potentially run in parallel, you must explicitly disable test parallelization of the collections with the `CollectionBehaviorAttribute`.</span></span> <span data-ttu-id="0d216-122">Geben Sie dann die Implementierung des `TestCollectionOrdererAttribute` an.</span><span class="sxs-lookup"><span data-stu-id="0d216-122">Then specify the implementation to the `TestCollectionOrdererAttribute`.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByDisplayName.cs":::

## <a name="order-by-custom-attribute"></a><span data-ttu-id="0d216-123">Sortieren nach benutzerdefiniertem Attribut</span><span class="sxs-lookup"><span data-stu-id="0d216-123">Order by custom attribute</span></span>

<span data-ttu-id="0d216-124">Um xUnit-Tests mit benutzerdefinierten Attributen zu sortieren, benötigen Sie zuerst ein Attribut, auf das Sie sich verlassen können.</span><span class="sxs-lookup"><span data-stu-id="0d216-124">To order xUnit tests with custom attributes, you first need an attribute to rely on.</span></span> <span data-ttu-id="0d216-125">Definieren Sie wie folgt ein `TestPriorityAttribute`:</span><span class="sxs-lookup"><span data-stu-id="0d216-125">Define a `TestPriorityAttribute` as follows:</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Attributes/TestPriorityAttribute.cs":::

<span data-ttu-id="0d216-126">Erwägen Sie als Nächstes die folgende `PriorityOrderer`-Implementierung der `ITestCaseOrderer`-Schnittstelle:</span><span class="sxs-lookup"><span data-stu-id="0d216-126">Next, consider the following `PriorityOrderer` implementation of the `ITestCaseOrderer` interface.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/PriorityOrderer.cs":::

<span data-ttu-id="0d216-127">In einer Testklasse legen Sie dann die Testfallreihenfolge mit dem `TestCaseOrdererAttribute` auf `PriorityOrderer` fest.</span><span class="sxs-lookup"><span data-stu-id="0d216-127">Then in a test class you set the test case order with the `TestCaseOrdererAttribute` to the `PriorityOrderer`.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByPriorityOrder.cs":::

:::zone-end
:::zone pivot="nunit"

## <a name="order-by-priority"></a><span data-ttu-id="0d216-128">Sortieren nach Priorität</span><span class="sxs-lookup"><span data-stu-id="0d216-128">Order by priority</span></span>

<span data-ttu-id="0d216-129">Zum expliziten Sortieren von Tests stellt NUnit ein [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute) bereit.</span><span class="sxs-lookup"><span data-stu-id="0d216-129">To order tests explicitly, NUnit provides an [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute).</span></span> <span data-ttu-id="0d216-130">Tests mit diesem Attribut werden vor Tests ohne gestartet.</span><span class="sxs-lookup"><span data-stu-id="0d216-130">Tests with this attribute are started before tests without.</span></span> <span data-ttu-id="0d216-131">Der Wert für die Reihenfolge wird verwendet, um die Reihenfolge zum Ausführen der Komponententests zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="0d216-131">The order value is used to determined the order to run the unit tests.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/NUnit.TestProject/ByOrder.cs":::

:::zone-end

## <a name="next-steps"></a><span data-ttu-id="0d216-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0d216-132">Next Steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0d216-133">Code Coverage für Komponententests</span><span class="sxs-lookup"><span data-stu-id="0d216-133">Unit test code coverage</span></span>](unit-testing-code-coverage.md)
