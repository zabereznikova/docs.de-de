---
title: Test einer veröffentlichten Ausgabe mit „dotnet vtest“
description: Erfahren Sie, wie Sie mit dem Befehl „dotnet vstest“ Tests für veröffentlichte Ausgaben ausführen.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 2f750a8bb0907069691c4a4491beeb4b1733df29
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="d586b-103">Test einer veröffentlichten Ausgabe mit „dotnet vtest“</span><span class="sxs-lookup"><span data-stu-id="d586b-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="d586b-104">Mit dem Befehl `dotnet vstest` können Sie Tests für bereits veröffentlichte Ausgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="d586b-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="d586b-105">Dieser kann für xUnit-, MSTest- und NUnit-Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d586b-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="d586b-106">Suchen Sie einfach die DLL-Datei, die Teil Ihrer veröffentlichten Ausgabe war, und führen Sie sie aus:</span><span class="sxs-lookup"><span data-stu-id="d586b-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="d586b-107">`<MyPublishedTests>` ist dabei der Name des veröffentlichten Testprojekts.</span><span class="sxs-lookup"><span data-stu-id="d586b-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="d586b-108">Beispiel für das Ausführen von Tests für eine veröffentlichte DLL</span><span class="sxs-lookup"><span data-stu-id="d586b-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="d586b-109">Hinweis: Wenn Ihre App Zielversionen für ein anderes Framework als `netcoreapp` festlegt, können Sie den Befehl `dotnet vstest` trotzdem ausführen, indem Sie das Zielframework mit einem Frameworkflag übergeben.</span><span class="sxs-lookup"><span data-stu-id="d586b-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="d586b-110">Beispielsweise `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="d586b-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="d586b-111">In Visual Studio 2017 Update 5 wird das gewünschte Framework automatisch erkannt.</span><span class="sxs-lookup"><span data-stu-id="d586b-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="d586b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d586b-112">See also</span></span>
 [<span data-ttu-id="d586b-113">Komponententests mit „dotnet-test“ und xUnit</span><span class="sxs-lookup"><span data-stu-id="d586b-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)  
 [<span data-ttu-id="d586b-114">Komponententests mit „dotnet-test“ und MSTest</span><span class="sxs-lookup"><span data-stu-id="d586b-114">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)  
