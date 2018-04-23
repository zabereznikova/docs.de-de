---
title: Organisieren und Testen von Projekten mit der .NET Core-Befehlszeile
description: In diesem Tutorial wird das Organisieren und Testen von .NET Core-Projekten von der Befehlszeile aus erläutert.
keywords: .NET, .NET Core, Komponententests, .NET Core-CLI, xUnit
author: cartermp
ms.author: mairaw
ms.date: 05/16/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 52ff1be3-d92e-4477-9c84-8c1771e87ab5
ms.workload:
- dotnetcore
ms.openlocfilehash: c68b7cb7dac069093e2e849543c5b5c21b4ffe3a
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2018
---
# <a name="organizing-and-testing-projects-with-the-net-core-command-line"></a><span data-ttu-id="8143e-104">Organisieren und Testen von Projekten mit der .NET Core-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="8143e-104">Organizing and testing projects with the .NET Core command line</span></span>

<span data-ttu-id="8143e-105">Dieses Tutorial folgt auf [Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile](using-with-xplat-cli.md), was Sie über die Erstellung einer einfachen Konsolen-App hinaus führt, damit Sie erweiterte und gut organisierte Anwendungen entwickeln können.</span><span class="sxs-lookup"><span data-stu-id="8143e-105">This tutorial follows [Getting started with .NET Core on Windows/Linux/macOS using the command line](using-with-xplat-cli.md), taking you beyond the creation of a simple console app to develop advanced and well-organized applications.</span></span> <span data-ttu-id="8143e-106">Nachdem Sie gesehen haben, wie Sie Ordner zum Organisieren Ihres Codes verwenden können, zeigt Ihnen dieses Tutorial, wie Sie eine Konsolenanwendung mit dem [xUnit](https://xunit.github.io/)-Testframework erweitern können.</span><span class="sxs-lookup"><span data-stu-id="8143e-106">After showing you how to use folders to organize your code, this tutorial shows you how to extend a console application with the [xUnit](https://xunit.github.io/) testing framework.</span></span>

## <a name="using-folders-to-organize-code"></a><span data-ttu-id="8143e-107">Verwenden von Ordnern zum Strukturieren von Code</span><span class="sxs-lookup"><span data-stu-id="8143e-107">Using folders to organize code</span></span>

<span data-ttu-id="8143e-108">Wenn Sie neue Typen in eine Konsolen-App einführen möchten, können Sie dies durch Hinzufügen von Dateien tun, die die Typen dieser App enthalten.</span><span class="sxs-lookup"><span data-stu-id="8143e-108">If you want to introduce new types into a console app, you can do so by adding files containing the types to the app.</span></span> <span data-ttu-id="8143e-109">Wenn Sie Ihrem Projekt beispielsweise Dateien hinzufügen, die die Typen `AccountInformation` und `MonthlyReportRecords` enthalten, ist die Dateistruktur des Projekts flach und einfach zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="8143e-109">For example if you add files containing `AccountInformation` and `MonthlyReportRecords` types to your project, the project file structure is flat and easy to navigate:</span></span>

```
/MyProject
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="8143e-110">Dies funktioniert jedoch nur einwandfrei, wenn Ihr Projekt relativ klein ist.</span><span class="sxs-lookup"><span data-stu-id="8143e-110">However, this only works well when the size of your project is relatively small.</span></span> <span data-ttu-id="8143e-111">Können Sie sich vorstellen, was passieren wird, wenn Sie 20 Typen zum Projekt hinzufügen?</span><span class="sxs-lookup"><span data-stu-id="8143e-111">Can you imagine what will happen if you add 20 types to the project?</span></span> <span data-ttu-id="8143e-112">Das Projekt wäre auf jeden Fall schwierig zu navigieren und zu warten, außerdem würden viele Dateien das Stammverzeichnis des Projekts unübersichtlich machen.</span><span class="sxs-lookup"><span data-stu-id="8143e-112">The project definitely wouldn't be easy to navigate and maintain with that many files littering the project's root directory.</span></span>

<span data-ttu-id="8143e-113">Um das Projekt zu organisieren, erstellen Sie einen neuen Ordner und nennen Ihn *Modelle*, der die Typdateien enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="8143e-113">To organize the project, create a new folder and name it *Models* to hold the type files.</span></span> <span data-ttu-id="8143e-114">Platzieren Sie die Typdateien in den Ordner *Modelle*.</span><span class="sxs-lookup"><span data-stu-id="8143e-114">Place the type files into the *Models* folder:</span></span>

```
/MyProject
|__/Models
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="8143e-115">Projekte, die Dateien logisch in Ordner gruppieren, sind einfach zu navigieren und zu warten.</span><span class="sxs-lookup"><span data-stu-id="8143e-115">Projects that logically group files into folders are easy to navigate and maintain.</span></span> <span data-ttu-id="8143e-116">Im nächsten Abschnitt erstellen Sie ein komplexeres Beispiel mit Ordnern und Komponententests.</span><span class="sxs-lookup"><span data-stu-id="8143e-116">In the next section, you create a more complex sample with folders and unit testing.</span></span>

## <a name="organizing-and-testing-using-the-newtypes-pets-sample"></a><span data-ttu-id="8143e-117">Organisieren und Testen mithilfe des NewTypes Pets-Beispiels</span><span class="sxs-lookup"><span data-stu-id="8143e-117">Organizing and testing using the NewTypes Pets Sample</span></span>

### <a name="building-the-sample"></a><span data-ttu-id="8143e-118">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="8143e-118">Building the sample</span></span>

<span data-ttu-id="8143e-119">Sie können für die folgenden Schritte entweder mithilfe des [NewTypes Pets-Beispiels](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) durchführen oder Ihre eigenen Dateien und Ordner erstellen.</span><span class="sxs-lookup"><span data-stu-id="8143e-119">For the following steps, you can either follow along using the [NewTypes Pets Sample](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) or create your own files and folders.</span></span> <span data-ttu-id="8143e-120">Die Typen werden logisch in einer Ordnerstruktur organisiert, die das spätere Hinzufügen zusätzlicher Typen erlaubt. Tests werden ebenso logisch in Ordnern platziert, wobei später weitere Tests durchgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="8143e-120">The types are logically organized into a folder structure that permits the addition of more types later, and tests are also logically placed in folders permitting the addition of more tests later.</span></span>

<span data-ttu-id="8143e-121">In diesem Beispiel sind zwei Typen enthalten, `Dog` und `Cat`, mit deren Hilfe die allgemeine Schnittstelle `IPet` implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="8143e-121">The sample contains two types, `Dog` and `Cat`, and has them implement a common interface, `IPet`.</span></span> <span data-ttu-id="8143e-122">Ihr Ziel für das `NewTypes`-Projekt ist es, die auf Haustiere (pets) bezogenen Typen in einem *Pets*-Ordner zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="8143e-122">For the `NewTypes` project, your goal is to organize the pet-related types into a *Pets* folder.</span></span> <span data-ttu-id="8143e-123">Wenn andere Typen später hinzugefügt werden, z.B. *WildAnimals*, werden sie im *NewTypes*-Ordner neben dem *Pets*-Ordner platziert.</span><span class="sxs-lookup"><span data-stu-id="8143e-123">If another set of types is added later, *WildAnimals* for example, they're placed in the *NewTypes* folder alongside the *Pets* folder.</span></span> <span data-ttu-id="8143e-124">Der *WildAnimals*-Ordner kann womöglich Tierarten enthalten, die keine Haustiere sind, z.B. die Typen `Squirrel` und `Rabbit`.</span><span class="sxs-lookup"><span data-stu-id="8143e-124">The *WildAnimals* folder may contain types for animals that aren't pets, such as `Squirrel` and `Rabbit` types.</span></span> <span data-ttu-id="8143e-125">Dadurch, dass Typen hinzugefügt werden, bleibt das Projekt organisiert.</span><span class="sxs-lookup"><span data-stu-id="8143e-125">In this way as types are added, the project remains well organized.</span></span> 

<span data-ttu-id="8143e-126">Erstellen Sie die folgende Ordnerstruktur mit angegebenem Dateiinhalt:</span><span class="sxs-lookup"><span data-stu-id="8143e-126">Create the following folder structure with file content indicated:</span></span>

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
```

<span data-ttu-id="8143e-127">*IPet.cs*:</span><span class="sxs-lookup"><span data-stu-id="8143e-127">*IPet.cs*:</span></span>

[!code-csharp[IPet interface](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/IPet.cs)]

<span data-ttu-id="8143e-128">*Dog.cs*:</span><span class="sxs-lookup"><span data-stu-id="8143e-128">*Dog.cs*:</span></span>

[!code-csharp[Dog class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Dog.cs)]

<span data-ttu-id="8143e-129">*Cat.cs*:</span><span class="sxs-lookup"><span data-stu-id="8143e-129">*Cat.cs*:</span></span>

[!code-csharp[Cat class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Cat.cs)]

<span data-ttu-id="8143e-130">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="8143e-130">*Program.cs*:</span></span>

[!code-csharp[Main](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Program.cs)]

<span data-ttu-id="8143e-131">*NewTypes.csproj*:</span><span class="sxs-lookup"><span data-stu-id="8143e-131">*NewTypes.csproj*:</span></span>

[!code-xml[NewTypes csproj](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/NewTypes.csproj)]

<span data-ttu-id="8143e-132">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8143e-132">Execute the following commands:</span></span>

```console
dotnet run
```

<span data-ttu-id="8143e-133">Achten Sie auf die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8143e-133">Obtain the following output:</span></span>

```console
Woof!
Meow!
```

<span data-ttu-id="8143e-134">Optionale Übung: Sie können einen neuen Tiertyp hinzufügen, z.B. `Bird`, indem Sie dieses Projekt erweitern.</span><span class="sxs-lookup"><span data-stu-id="8143e-134">Optional exercise: You can add a new pet type, such as a `Bird`, by extending this project.</span></span> <span data-ttu-id="8143e-135">Die `TalkToOwner`-Methode des Vogels soll einen `Tweet!` an den Besitzer geben.</span><span class="sxs-lookup"><span data-stu-id="8143e-135">Make the bird's `TalkToOwner` method give a `Tweet!` to the owner.</span></span> <span data-ttu-id="8143e-136">Führen Sie die App erneut aus.</span><span class="sxs-lookup"><span data-stu-id="8143e-136">Run the app again.</span></span> <span data-ttu-id="8143e-137">Die Ausgabe wird `Tweet!` enthalten.</span><span class="sxs-lookup"><span data-stu-id="8143e-137">The output will include `Tweet!`</span></span>

### <a name="testing-the-sample"></a><span data-ttu-id="8143e-138">Testen der Beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="8143e-138">Testing the sample</span></span>

<span data-ttu-id="8143e-139">Das `NewTypes`-Projekt ist platziert, und Sie haben es organisiert, indem Sie die auf Haustiere bezogenen Typen in einem Ordner gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="8143e-139">The `NewTypes` project is in place, and you've organized it by keeping the pets-related types in a folder.</span></span> <span data-ttu-id="8143e-140">Erstellen Sie als Nächstes Ihr Testprojekt und beginnen Sie, Tests mit dem [xUnit](https://xunit.github.io/)-Testframework zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="8143e-140">Next, create your test project and start writing tests with the [xUnit](https://xunit.github.io/) test framework.</span></span> <span data-ttu-id="8143e-141">Komponententests erlauben Ihnen, automatisch das Verhalten Ihrer Haustiertypen zu testen, um zu überprüfen, ob sie ordnungsgemäß arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8143e-141">Unit testing allows you to automatically check the bevahior of your pet types to confirm that they're operating properly.</span></span>

<span data-ttu-id="8143e-142">Erstellen Sie einen *test*-Ordner, der den *NewTypesTests*-Ordner innehat.</span><span class="sxs-lookup"><span data-stu-id="8143e-142">Create a *test* folder with a *NewTypesTests* folder within it.</span></span> <span data-ttu-id="8143e-143">Führen Sie in einer Eingabeaufforderung vom *NewTypesTests*-Ordner `dotnet new xunit` aus.</span><span class="sxs-lookup"><span data-stu-id="8143e-143">At a command prompt from the *NewTypesTests* folder, execute `dotnet new xunit`.</span></span> <span data-ttu-id="8143e-144">Dadurch werden zwei Dateien erstellt: *NewTypesTests.csproj* und *UnitTest1.cs*.</span><span class="sxs-lookup"><span data-stu-id="8143e-144">This produces two files: *NewTypesTests.csproj* and *UnitTest1.cs*.</span></span>

<span data-ttu-id="8143e-145">Das Testprojekt kann derzeit nicht die Typen in `NewTypes` testen und benötigt einen Projektverweis auf das `NewTypes`-Projekt.</span><span class="sxs-lookup"><span data-stu-id="8143e-145">The test project cannot currently test the types in `NewTypes` and requires a project reference to the `NewTypes` project.</span></span> <span data-ttu-id="8143e-146">Um einen Projektverweis hinzuzufügen, verwenden Sie den [`dotnet add reference`](../tools/dotnet-add-reference.md)-Befehl:</span><span class="sxs-lookup"><span data-stu-id="8143e-146">To add a project reference, use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

<span data-ttu-id="8143e-147">Sie haben auch die Möglichkeit, den Projektverweis manuell hinzuzufügen, indem Sie der *NewTypesTests.csproj*-Datei einen `<ItemGroup>`-Knoten hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="8143e-147">You also have the option of manually adding the project reference by adding an `<ItemGroup>` node to the *NewTypesTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="../../src/NewTypes/NewTypes.csproj" />
</ItemGroup>
```

<span data-ttu-id="8143e-148">*NewTypesTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="8143e-148">*NewTypesTests.csproj*:</span></span>

[!code-xml[NewTypesTests csproj](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/NewTypesTests.csproj)]

<span data-ttu-id="8143e-149">Die *NewTypesTests.csproj*-Datei enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8143e-149">The *NewTypesTests.csproj* file contains the following:</span></span>

* <span data-ttu-id="8143e-150">Paketverweis auf `Microsoft.NET.Test.Sdk`, die .NET-Testinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="8143e-150">Package reference to `Microsoft.NET.Test.Sdk`, the .NET testing infrastructure</span></span>
* <span data-ttu-id="8143e-151">Paketverweis auf `xunit`, das xUnit-Testframework</span><span class="sxs-lookup"><span data-stu-id="8143e-151">Package reference to `xunit`, the xUnit testing framework</span></span>
* <span data-ttu-id="8143e-152">Paketverweis auf `xunit.runner.visualstudio`, der Test Runner</span><span class="sxs-lookup"><span data-stu-id="8143e-152">Package reference to `xunit.runner.visualstudio`, the test runner</span></span>
* <span data-ttu-id="8143e-153">Projektverweis auf `NewTypes`, der zu testende Code</span><span class="sxs-lookup"><span data-stu-id="8143e-153">Project reference to `NewTypes`, the code to test</span></span>

<span data-ttu-id="8143e-154">Ändern Sie den Namen von *UnitTest1.cs* zu *PetTests.cs*, und ersetzen Sie den Code in der Datei mit Folgendem:</span><span class="sxs-lookup"><span data-stu-id="8143e-154">Change the name of *UnitTest1.cs* to *PetTests.cs* and replace the code in the file with the following:</span></span>

```csharp
using System;
using Xunit;
using Pets;

public class PetTests
{
    [Fact]
    public void DogTalkToOwnerReturnsWoof()
    {
        string expected = "Woof!";
        string actual = new Dog().TalkToOwner();
        
        Assert.NotEqual(expected, actual);
    }
    
    [Fact]
    public void CatTalkToOwnerReturnsMeow()
    {
        string expected = "Meow!";
        string actual = new Cat().TalkToOwner();
        
        Assert.NotEqual(expected, actual);
    }
}
```

<span data-ttu-id="8143e-155">Optionale Übung: Wenn Sie zuvor einen `Bird`-Typ hinzugefügt haben, der `Tweet!` dem Besitzer zurückgibt, fügen Sie der *PetTests.cs*-Datei eine Testmethode hinzu, `BirdTalkToOwnerReturnsTweet`, um zu überprüfen, dass die `TalkToOwner`-Methode ordnungsgemäß für den `Bird`-Typ funktioniert.</span><span class="sxs-lookup"><span data-stu-id="8143e-155">Optional exercise: If you added a `Bird` type earlier that yields a `Tweet!` to the owner, add a test method to the *PetTests.cs* file, `BirdTalkToOwnerReturnsTweet`, to check that the `TalkToOwner` method works correctly for the `Bird` type.</span></span>

> [!NOTE]
> <span data-ttu-id="8143e-156">Obwohl Sie erwarten, dass die Werte `expected` und `actual` gleich sind, geben die anfänglichen Assertionen mit den `Assert.NotEqual`-Überprüfungen an, dass sie *nicht gleich* sind.</span><span class="sxs-lookup"><span data-stu-id="8143e-156">Although you expect that the `expected` and `actual` values are equal, the initial assertions with the `Assert.NotEqual` checks specify that they are *not equal*.</span></span> <span data-ttu-id="8143e-157">Erstellen Sie Ihre Tests zuerst immer, damit sie einmal fehlschlagen können, um die Logik der Tests zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8143e-157">Always initially create your tests to fail once in order to check the logic of the tests.</span></span> <span data-ttu-id="8143e-158">Dies ist ein wichtiger Schritt in der TDD-Methodik (test-driven design, testgesteuerter Entwurf).</span><span class="sxs-lookup"><span data-stu-id="8143e-158">This is an important step in test-driven design (TDD) methodology.</span></span> <span data-ttu-id="8143e-159">Nachdem Sie bestätigt haben, dass die Tests fehlschlagen, passen Sie die Assertion an, damit sie erfolgreich ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="8143e-159">After you confirm the tests fail, you adjust the assertions to allow them to pass.</span></span>

<span data-ttu-id="8143e-160">Nachstehend ist die vollständige Projektstruktur dargestellt:</span><span class="sxs-lookup"><span data-stu-id="8143e-160">The following shows the complete project structure:</span></span>

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__NewTypesTests.csproj
```

<span data-ttu-id="8143e-161">Beginnen Sie im *test/NewTypesTests*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8143e-161">Start in the *test/NewTypesTests* directory.</span></span> <span data-ttu-id="8143e-162">Stellen Sie das Testprojekt mit dem [`dotnet restore`](../tools/dotnet-restore.md)-Befehl wieder her.</span><span class="sxs-lookup"><span data-stu-id="8143e-162">Restore the test project with the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="8143e-163">Führen Sie die Tests mit dem [`dotnet test`](../tools/dotnet-test.md)-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="8143e-163">Run the tests with the [`dotnet test`](../tools/dotnet-test.md) command.</span></span> <span data-ttu-id="8143e-164">Dieser Befehl startet den in der Projektdatei angegebenen Test Runner.</span><span class="sxs-lookup"><span data-stu-id="8143e-164">This command starts the test runner specified in the project file.</span></span>

 [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

 
<span data-ttu-id="8143e-165">Der Test schlägt wie erwartet fehl, und die Konsole zeigt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8143e-165">As expected, testing fails, and the console displays the following output:</span></span>
 
```
Test run for C:\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp1.1\NewTypesTests.dll(.NETCoreApp,Version=v1.1)
Microsoft (R) Test Execution Command Line Tool Version 15.0.0.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.7271827]   Discovering: NewTypesTests
[xUnit.net 00:00:00.8258687]   Discovered:  NewTypesTests
[xUnit.net 00:00:00.8663545]   Starting:    NewTypesTests
[xUnit.net 00:00:01.0109236]     PetTests.CatTalkToOwnerReturnsMeow [FAIL]
[xUnit.net 00:00:01.0119107]       Assert.NotEqual() Failure
[xUnit.net 00:00:01.0120278]       Expected: Not "Meow!"
[xUnit.net 00:00:01.0120968]       Actual:   "Meow!"
[xUnit.net 00:00:01.0130500]       Stack Trace:
[xUnit.net 00:00:01.0141240]         C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs(22,0): at PetTests.CatTalkToOwnerReturnsMeow()
[xUnit.net 00:00:01.0272364]     PetTests.DogTalkToOwnerReturnsWoof [FAIL]
[xUnit.net 00:00:01.0273649]       Assert.NotEqual() Failure
[xUnit.net 00:00:01.0274166]       Expected: Not "Woof!"
[xUnit.net 00:00:01.0274690]       Actual:   "Woof!"
[xUnit.net 00:00:01.0275264]       Stack Trace:
[xUnit.net 00:00:01.0275960]         C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs(13,0): at PetTests.DogTalkToOwnerReturnsWoof()
[xUnit.net 00:00:01.0294509]   Finished:    NewTypesTests
Failed   PetTests.CatTalkToOwnerReturnsMeow
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Meow!"
Actual:   "Meow!"
Stack Trace:
   at PetTests.CatTalkToOwnerReturnsMeow() in C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 22
Failed   PetTests.DogTalkToOwnerReturnsWoof
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Woof!"
Actual:   "Woof!"
Stack Trace:
   at PetTests.DogTalkToOwnerReturnsWoof() in C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 13

Total tests: 2. Passed: 0. Failed: 2. Skipped: 0.
Test Run Failed.
Test execution time: 2.1371 Seconds
```

<span data-ttu-id="8143e-166">Ändern Sie die Assertionen Ihrer Tests von `Assert.NotEqual` zu `Assert.Equal`:</span><span class="sxs-lookup"><span data-stu-id="8143e-166">Change the assertions of your tests from `Assert.NotEqual` to `Assert.Equal`:</span></span>

[!code-csharp[PetTests class](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/PetTests.cs)]

<span data-ttu-id="8143e-167">Führen Sie die Tests erneut mit dem `dotnet test`-Befehl aus, und achten Sie auf die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8143e-167">Re-run the tests with the `dotnet test` command and obtain the following output:</span></span>

```
Microsoft (R) Test Execution Command Line Tool Version 15.0.0.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:01.3882374]   Discovering: NewTypesTests
[xUnit.net 00:00:01.4767970]   Discovered:  NewTypesTests
[xUnit.net 00:00:01.5157667]   Starting:    NewTypesTests
[xUnit.net 00:00:01.6408870]   Finished:    NewTypesTests

Total tests: 2. Passed: 2. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.6634 Seconds
```

<span data-ttu-id="8143e-168">Die Tests werden erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8143e-168">Testing passes.</span></span> <span data-ttu-id="8143e-169">Die Haustiertyp-Methoden geben die korrekten Werte zurück, wenn sie mit dem Besitzer kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="8143e-169">The pet types' methods return the correct values when talking to the owner.</span></span>

<span data-ttu-id="8143e-170">Sie haben Techniken zum Organisieren und Testen von Projekten mithilfe von xUnit gelernt.</span><span class="sxs-lookup"><span data-stu-id="8143e-170">You've learned techniques for organizing and testing projects using xUnit.</span></span> <span data-ttu-id="8143e-171">Machen Sie mit diesen Techniken weiter, und wenden Sie sie in Ihren eigenen Projekten an.</span><span class="sxs-lookup"><span data-stu-id="8143e-171">Go forward with these techniques applying them in your own projects.</span></span> <span data-ttu-id="8143e-172">*Viel Spaß beim Programmieren!*</span><span class="sxs-lookup"><span data-stu-id="8143e-172">*Happy coding!*</span></span>

