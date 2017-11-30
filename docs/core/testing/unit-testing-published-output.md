---
title: "Testen von veröffentlichten Dotnet in der Vstest-Ausgabe"
description: "Informationen Sie zum Ausführen von Tests in der veröffentlichten Ausgabe mit dem Dotnet in der Vstest-Befehl."
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3965e4ca-75b8-4969-b3af-ca993c397a15
ms.openlocfilehash: 217787d41a9da6000941ded6caaa4f44d124644b
ms.sourcegitcommit: 8a4f8e6a7f1341764abcd188a332cc28d1e2d8ec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="14c9e-103">Testen von veröffentlichten Dotnet in der Vstest-Ausgabe</span><span class="sxs-lookup"><span data-stu-id="14c9e-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="14c9e-104">Sie können bei der Ausgabe bereits veröffentlichten Tests ausführen, mit der `dotnet vstest` Befehl.</span><span class="sxs-lookup"><span data-stu-id="14c9e-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="14c9e-105">Diese Methode kann auf xUnit, MSTest und NUnit Tests verwendet.</span><span class="sxs-lookup"><span data-stu-id="14c9e-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="14c9e-106">Einfach suchen Sie die DLL-Datei, die Teil der veröffentlichten Ausgabe war, und führen Sie:</span><span class="sxs-lookup"><span data-stu-id="14c9e-106">Simply locate the DLL file that was part of your published output and run:</span></span>
```
dotnet vstest <MyPublishedTests>.dll
```
<span data-ttu-id="14c9e-107">wobei `<MyPublishedTests>` ist der Name des veröffentlichten Testprojekts.</span><span class="sxs-lookup"><span data-stu-id="14c9e-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

### <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="14c9e-108">Beispiel für das Ausführen von Tests auf einer veröffentlichten DLL</span><span class="sxs-lookup"><span data-stu-id="14c9e-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE] <span data-ttu-id="14c9e-109">Hinweis: Wenn Ihre app anders als ein Framework abzielt `netcoreapp` können Sie weiterhin Ausführen der `dotnet vstest` Befehl durch das Zielframework durch ein Framework-Flag übergeben.</span><span class="sxs-lookup"><span data-stu-id="14c9e-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="14c9e-110">Beispielsweise `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="14c9e-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="14c9e-111">In Visual Studio 2017 Update 5 wird das gewünschte Framework automatisch erkannt.</span><span class="sxs-lookup"><span data-stu-id="14c9e-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

### <a name="related-topics"></a><span data-ttu-id="14c9e-112">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="14c9e-112">Related topics</span></span>
- [<span data-ttu-id="14c9e-113">UnitTests mit Test Dotnet und xUnit</span><span class="sxs-lookup"><span data-stu-id="14c9e-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="14c9e-114">UnitTests mit Test Dotnet und MSTest</span><span class="sxs-lookup"><span data-stu-id="14c9e-114">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
