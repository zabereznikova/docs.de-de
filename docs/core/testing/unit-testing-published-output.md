---
title: Test einer veröffentlichten Ausgabe mit „dotnet vtest“
description: Erfahren Sie, wie Sie mit dem Befehl „dotnet vstest“ Tests für veröffentlichte Bibliotheken statt für den Quellcode ausführen.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: 7618d37782de3a16f1963380bbb56945fb73e8eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714265"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="6b2cb-103">Test einer veröffentlichten Ausgabe mit „dotnet vtest“</span><span class="sxs-lookup"><span data-stu-id="6b2cb-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="6b2cb-104">Mit dem Befehl `dotnet vstest` können Sie Tests für bereits veröffentlichte Ausgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="6b2cb-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="6b2cb-105">Dieser kann für xUnit-, MSTest- und NUnit-Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6b2cb-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="6b2cb-106">Suchen Sie einfach die DLL-Datei, die Teil Ihrer veröffentlichten Ausgabe war, und führen Sie sie aus:</span><span class="sxs-lookup"><span data-stu-id="6b2cb-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```dotnetcli
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="6b2cb-107">`<MyPublishedTests>` ist dabei der Name des veröffentlichten Testprojekts.</span><span class="sxs-lookup"><span data-stu-id="6b2cb-107">Where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example"></a><span data-ttu-id="6b2cb-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b2cb-108">Example</span></span>

<span data-ttu-id="6b2cb-109">Mit den folgenden Befehlen wird das Ausführen von Tests für eine veröffentlichte DLL demonstriert.</span><span class="sxs-lookup"><span data-stu-id="6b2cb-109">The commands below demonstrate running tests on a published DLL.</span></span>

```dotnetcli
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="6b2cb-110">Hinweis: Wenn Ihre App für ein anderes Framework als `netcoreapp` vorgesehen ist, können Sie den Befehl `dotnet vstest` trotzdem ausführen, indem Sie das Zielframework mit einem Frameworkflag übergeben.</span><span class="sxs-lookup"><span data-stu-id="6b2cb-110">Note: If your app targets a framework other than `netcoreapp`, you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="6b2cb-111">Beispielsweise `dotnet vstest <MyPublishedTests>.dll --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="6b2cb-111">For example, `dotnet vstest <MyPublishedTests>.dll --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="6b2cb-112">In Visual Studio 2017 Update 5 oder höher wird das gewünschte Framework automatisch erkannt.</span><span class="sxs-lookup"><span data-stu-id="6b2cb-112">In Visual Studio 2017 Update 5 and later, the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b2cb-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b2cb-113">See also</span></span>

- [<span data-ttu-id="6b2cb-114">Komponententests mit „dotnet-test“ und xUnit</span><span class="sxs-lookup"><span data-stu-id="6b2cb-114">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="6b2cb-115">Komponententests mit „dotnet-test“ und NUnit</span><span class="sxs-lookup"><span data-stu-id="6b2cb-115">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="6b2cb-116">Komponententests mit „dotnet-test“ und MSTest</span><span class="sxs-lookup"><span data-stu-id="6b2cb-116">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
