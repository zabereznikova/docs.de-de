---
title: Test einer veröffentlichten Ausgabe mit „dotnet vtest“
description: Erfahren Sie, wie Sie mit dem Befehl „dotnet vstest“ Tests für veröffentlichte Ausgaben ausführen.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: e99000996f5dfa9f9d4f9b823e36ecbe325da835
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508132"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="0727f-103">Test einer veröffentlichten Ausgabe mit „dotnet vtest“</span><span class="sxs-lookup"><span data-stu-id="0727f-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="0727f-104">Mit dem Befehl `dotnet vstest` können Sie Tests für bereits veröffentlichte Ausgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="0727f-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="0727f-105">Dieser kann für xUnit-, MSTest- und NUnit-Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0727f-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="0727f-106">Suchen Sie einfach die DLL-Datei, die Teil Ihrer veröffentlichten Ausgabe war, und führen Sie sie aus:</span><span class="sxs-lookup"><span data-stu-id="0727f-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="0727f-107">`<MyPublishedTests>` ist dabei der Name des veröffentlichten Testprojekts.</span><span class="sxs-lookup"><span data-stu-id="0727f-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="0727f-108">Beispiel für das Ausführen von Tests für eine veröffentlichte DLL</span><span class="sxs-lookup"><span data-stu-id="0727f-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="0727f-109">Hinweis: Wenn Ihre App Zielversionen für ein anderes Framework als `netcoreapp` festlegt, können Sie den Befehl `dotnet vstest` trotzdem ausführen, indem Sie das Zielframework mit einem Frameworkflag übergeben.</span><span class="sxs-lookup"><span data-stu-id="0727f-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="0727f-110">Beispielsweise `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="0727f-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="0727f-111">In Visual Studio 2017 Update 5 wird das gewünschte Framework automatisch erkannt.</span><span class="sxs-lookup"><span data-stu-id="0727f-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="0727f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0727f-112">See also</span></span>
- [<span data-ttu-id="0727f-113">Komponententests mit „dotnet-test“ und xUnit</span><span class="sxs-lookup"><span data-stu-id="0727f-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="0727f-114">Komponententests mit „dotnet-test“ und NUnit</span><span class="sxs-lookup"><span data-stu-id="0727f-114">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="0727f-115">Komponententests mit „dotnet-test“ und MSTest</span><span class="sxs-lookup"><span data-stu-id="0727f-115">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
