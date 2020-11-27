---
title: Testen einer .NET-Klassenbibliothek mit Visual Studio Code
description: In diesem Artikel erfahren Sie, wie Sie Visual Studio Code und die .NET-CLI zum Erstellen und Ausführen eines Komponententestprojekts für eine .NET-Klassenbibliothek verwenden.
ms.date: 11/17/2020
ms.openlocfilehash: 4528bd203ae03988a1d1d80a7e904e94e68c1d04
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915855"
---
# <a name="tutorial-test-a-net-class-library-using-visual-studio-code"></a><span data-ttu-id="3e0af-103">Tutorial: Testen einer .NET-Klassenbibliothek mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3e0af-103">Tutorial: Test a .NET class library using Visual Studio Code</span></span>

<span data-ttu-id="3e0af-104">In diesem Tutorial wird gezeigt, wie Sie Komponententests automatisieren, indem Sie einer Projektmappe ein Testprojekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-104">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3e0af-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3e0af-105">Prerequisites</span></span>

- <span data-ttu-id="3e0af-106">In diesem Tutorial wird die Projektmappe verwendet, die Sie in [Tutorial: Erstellen einer .NET-Standard-Bibliothek in Visual Studio Code](library-with-visual-studio-code.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-106">This tutorial works with the solution that you create in [Create a .NET class library using Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="3e0af-107">Ein Komponententestprojekt erstellen</span><span class="sxs-lookup"><span data-stu-id="3e0af-107">Create a unit test project</span></span>

<span data-ttu-id="3e0af-108">Komponententests bieten automatisierte Softwaretests während der Entwicklung und Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="3e0af-108">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="3e0af-109">Das in diesem Tutorial verwendete Testframework ist MSTest.</span><span class="sxs-lookup"><span data-stu-id="3e0af-109">The testing framework that you use in this tutorial is MSTest.</span></span> <span data-ttu-id="3e0af-110">[MSTest](https://github.com/Microsoft/testfx-docs) ist eines von drei Testframeworks, aus denen Sie wählen können.</span><span class="sxs-lookup"><span data-stu-id="3e0af-110">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="3e0af-111">Die beiden anderen sind [xUnit](https://xunit.net/) und [nUnit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="3e0af-111">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="3e0af-112">Starten Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="3e0af-112">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="3e0af-113">Öffnen Sie die `ClassLibraryProjects`-Projektmappe, die Sie in [Tutorial: Erstellen einer .NET-Standard-Bibliothek in Visual Studio Code](library-with-visual-studio-code.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3e0af-113">Open the `ClassLibraryProjects` solution you created in [Create a .NET class library using Visual Studio Code](library-with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="3e0af-114">Erstellen Sie ein Komponententestprojekt namens „StringLibraryTest“.</span><span class="sxs-lookup"><span data-stu-id="3e0af-114">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="3e0af-115">Die Projektvorlage erstellt die Datei „UnitTest1.cs“, die den folgenden Code enthält:</span><span class="sxs-lookup"><span data-stu-id="3e0af-115">The project template creates a UnitTest1.cs file with the following code:</span></span>

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

   namespace StringLibraryTest
   {
       [TestClass]
       public class UnitTest1
       {
           [TestMethod]
           public void TestMethod1()
           {
           }
       }
   }
   ```

   <span data-ttu-id="3e0af-116">Der von der Vorlage für Komponententests erstellte Quellcode führt Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="3e0af-116">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="3e0af-117">Er importiert den Namespace <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, der für Komponententests verwendeten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="3e0af-117">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="3e0af-118">Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> auf die Klasse `UnitTest1` an.</span><span class="sxs-lookup"><span data-stu-id="3e0af-118">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="3e0af-119">Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> an, um `TestMethod1` zu definieren.</span><span class="sxs-lookup"><span data-stu-id="3e0af-119">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="3e0af-120">Jede mit [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) gekennzeichnete Methode in einer mit [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) gekennzeichneten Testklasse wird automatisch ausgeführt, wenn der Komponententest ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3e0af-120">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="3e0af-121">Fügen Sie das Testprojekt zur Projektmappe hinzu.</span><span class="sxs-lookup"><span data-stu-id="3e0af-121">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

## <a name="add-a-project-reference"></a><span data-ttu-id="3e0af-122">Hinzufügen eines Projektverweises</span><span class="sxs-lookup"><span data-stu-id="3e0af-122">Add a project reference</span></span>

<span data-ttu-id="3e0af-123">Damit das Testprojekt mit der `StringLibrary`-Klasse funktioniert, fügen Sie im Projekt `StringLibraryTest` einen Verweis auf das Projekt `StringLibrary` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3e0af-123">For the test project to work with the `StringLibrary` class, add a reference in the `StringLibraryTest` project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="3e0af-124">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="3e0af-124">Run the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="3e0af-125">Hinzufügen und Ausführen von Komponententestmethoden</span><span class="sxs-lookup"><span data-stu-id="3e0af-125">Add and run unit test methods</span></span>

<span data-ttu-id="3e0af-126">Wenn Visual Studio einen Komponententest ausführt, erfolgt die Ausführung jeder Methode, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> gekennzeichnet ist, in einer Klasse, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="3e0af-126">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="3e0af-127">Eine Testmethode endet, wenn der erste Fehler gefunden wird, oder wenn alle in der Methode enthaltenen Tests erfolgreich ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="3e0af-127">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="3e0af-128">In den am häufigsten verwendeten Tests werden Member der Klasse <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-128">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="3e0af-129">Viele Assert-Methoden enthalten mindestens zwei Parameter, von denen einer das erwartete und der andere das tatsächliche Testergebnis ist.</span><span class="sxs-lookup"><span data-stu-id="3e0af-129">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="3e0af-130">Die am häufigsten aufgerufenen Methoden der `Assert`-Klasse werden in der nachfolgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="3e0af-130">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="3e0af-131">Assert-Methoden</span><span class="sxs-lookup"><span data-stu-id="3e0af-131">Assert methods</span></span>     | <span data-ttu-id="3e0af-132">Funktion</span><span class="sxs-lookup"><span data-stu-id="3e0af-132">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="3e0af-133">Überprüft, ob zwei Werte oder Objekte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="3e0af-133">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="3e0af-134">Der Assert ist nicht erfolgreich, wenn die Werte oder Objekte nicht gleich sind.</span><span class="sxs-lookup"><span data-stu-id="3e0af-134">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="3e0af-135">Überprüft, ob zwei Objektvariablen auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-135">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="3e0af-136">Die Bestätigung ist nicht erfolgreich, wenn die Variablen auf verschiedene Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-136">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="3e0af-137">Überprüft, ob eine Bedingung `false` ist.</span><span class="sxs-lookup"><span data-stu-id="3e0af-137">Verifies that a condition is `false`.</span></span> <span data-ttu-id="3e0af-138">Die Bestätigung ist nicht erfolgreich, wenn die Bedingung `true` ist.</span><span class="sxs-lookup"><span data-stu-id="3e0af-138">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="3e0af-139">Überprüft, ob ein Objekt nicht `null` ist.</span><span class="sxs-lookup"><span data-stu-id="3e0af-139">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="3e0af-140">Die Bestätigung ist nicht erfolgreich, wenn das Objekt `null` ist.</span><span class="sxs-lookup"><span data-stu-id="3e0af-140">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="3e0af-141">Sie können auch die <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType>-Methode in einer Testmethode verwenden, um den Typ der Ausnahme anzugeben, die ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="3e0af-141">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="3e0af-142">Der Test ist nicht erfolgreich, wenn die angegebene Ausnahme nicht ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="3e0af-142">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="3e0af-143">Beim Testen der `StringLibrary.StartsWithUpper`-Methode möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-143">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="3e0af-144">Sie erwarten, dass die Methode in diesen Fällen `true` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-144">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3e0af-145">Außerdem möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die nicht mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-145">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="3e0af-146">Sie erwarten, dass die Methode in diesen Fällen `false` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-146">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="3e0af-147">Da Ihre Bibliotheksmethode Zeichenfolgen verarbeitet, sollten Sie sicherstellen, dass sie eine [leere Zeichenfolge (`String.Empty`)](xref:System.String.Empty) und eine `null`-Zeichenfolge erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="3e0af-147">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="3e0af-148">Eine leere Zeichenfolge enthält keine Zeichen, und ihre <xref:System.String.Length>-Eigenschaft weist den Wert „0“ auf.</span><span class="sxs-lookup"><span data-stu-id="3e0af-148">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="3e0af-149">Eine `null`-Zeichenfolge ist eine Zeichenfolge, die nicht initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3e0af-149">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="3e0af-150">Sie können `StartsWithUpper` als statische Methode direkt aufrufen und ein einzelnes <xref:System.String>-Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="3e0af-150">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="3e0af-151">Alternativ können Sie `StartsWithUpper` als Erweiterungsmethode für eine `string`-Variable aufrufen, die `null` zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="3e0af-151">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="3e0af-152">Sie definieren drei Methoden, von denen jede eine zugehörige <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>-Methode für jedes Element in einem Zeichenfolgenarray aufruft.</span><span class="sxs-lookup"><span data-stu-id="3e0af-152">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="3e0af-153">Sie rufen eine Methodenüberladung auf, mit der Sie eine Fehlermeldung angeben können, die bei einem Testfehler angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3e0af-153">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="3e0af-154">Die Meldung enthält die Zeichenfolge, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="3e0af-154">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="3e0af-155">So erstellen Sie die Testmethoden:</span><span class="sxs-lookup"><span data-stu-id="3e0af-155">To create the test methods:</span></span>

1. <span data-ttu-id="3e0af-156">Öffnen Sie die Datei *StringLibraryTest/UnitTest1.cs*, und ersetzen Sie den gesamten Code durch den folgenden:</span><span class="sxs-lookup"><span data-stu-id="3e0af-156">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="3e0af-157">Der Test für Großbuchstaben in der `TestStartsWithUpper`-Methode enthält den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+041C).</span><span class="sxs-lookup"><span data-stu-id="3e0af-157">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="3e0af-158">Der Test für Kleinbuchstaben in der `TestDoesNotStartWithUpper`-Methode enthält den griechischen Kleinbuchstaben alpha (U+03B1) und den kyrillischen Kleinbuchstaben ghe (U+0433).</span><span class="sxs-lookup"><span data-stu-id="3e0af-158">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="3e0af-159">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-159">Save your changes.</span></span>

1. <span data-ttu-id="3e0af-160">Führen Sie die Tests aus:</span><span class="sxs-lookup"><span data-stu-id="3e0af-160">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="3e0af-161">Die Terminalausgabe gibt an, dass alle Tests bestanden wurden.</span><span class="sxs-lookup"><span data-stu-id="3e0af-161">The terminal output shows that all tests passed.</span></span>

   ```output
   Starting test execution, please wait...
   A total of 1 test files matched the specified pattern.

   Passed!  - Failed:     0, Passed:     3, Skipped:     0, Total:     3, Duration: 3 ms - StringLibraryTest.dll (net5.0)
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="3e0af-162">Behandeln von Testfehlern</span><span class="sxs-lookup"><span data-stu-id="3e0af-162">Handle test failures</span></span>

<span data-ttu-id="3e0af-163">Bei der testgesteuerten Entwicklung (Test-Driven Development, TDD) schreiben Sie zunächst Tests, bei deren ersten Ausführung Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="3e0af-163">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="3e0af-164">Anschließend fügen Sie der App Code hinzu, mit dem der Test erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3e0af-164">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="3e0af-165">Für dieses Tutorial haben Sie den Test, der den Code überprüft, nach Schreiben des App-Codes erstellt, sodass beim Test kein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3e0af-165">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="3e0af-166">Fügen Sie einen ungültigen Wert zur Testeingabe hinzu, um zu überprüfen, ob beim Test auch wirklich erwartungsgemäß ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="3e0af-166">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="3e0af-167">Verändern Sie das `words`-Array in der `TestDoesNotStartWithUpper`-Methode, um die Zeichenfolge "Error" einzufügen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-167">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="3e0af-168">Führen Sie die Tests aus:</span><span class="sxs-lookup"><span data-stu-id="3e0af-168">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="3e0af-169">Die Terminalausgabe zeigt, dass bei einem Test ein Fehler auftritt, und gibt eine Fehlermeldung für diesen Test an: „Fehler bei Assert.IsFalse.</span><span class="sxs-lookup"><span data-stu-id="3e0af-169">The terminal output shows that one test fails, and it provides an error message for the failed test: "Assert.IsFalse failed.</span></span> <span data-ttu-id="3e0af-170">Für 'Error' erwartet: False; tatsächlich: True“.</span><span class="sxs-lookup"><span data-stu-id="3e0af-170">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="3e0af-171">Wegen des Fehlers wurden keine auf „Error“ folgenden Zeichenfolgen im Array getestet.</span><span class="sxs-lookup"><span data-stu-id="3e0af-171">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   ```output
   Starting test execution, please wait...
   A total of 1 test files matched the specified pattern.
     Failed TestDoesNotStartWithUpper [28 ms]
     Error Message:
      Assert.IsFalse failed. Expected for 'Error': false; Actual: True
     Stack Trace:
        at StringLibraryTest.UnitTest1.TestDoesNotStartWithUpper() in C:\ClassLibraryProjects\StringLibraryTest\UnitTest1.cs:line 33

   Failed!  - Failed:     1, Passed:     2, Skipped:     0, Total:     3, Duration: 31 ms - StringLibraryTest.dll (net5.0)
   ```

1. <span data-ttu-id="3e0af-172">Entfernen Sie die Zeichenfolge „Error“, die Sie in Schritt 1 hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="3e0af-172">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="3e0af-173">Führen Sie den Test erneut aus. Nun ist er erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="3e0af-173">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="3e0af-174">Testen der Releaseversion der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="3e0af-174">Test the Release version of the library</span></span>

<span data-ttu-id="3e0af-175">Nachdem die Tests beim Ausführen des Debugbuilds der Bibliothek nun alle erfolgreich waren, führen Sie die Tests auch für den Releasebuild der Bibliothek aus.</span><span class="sxs-lookup"><span data-stu-id="3e0af-175">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="3e0af-176">Eine Reihe von Faktoren einschließlich der Compileroptimierungen kann manchmal zu einem unterschiedlichen Verhalten von Debug- und endgültiger Produktversion führen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-176">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="3e0af-177">Führen Sie die Tests mit der Releasebuildkonfiguration aus:</span><span class="sxs-lookup"><span data-stu-id="3e0af-177">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="3e0af-178">Die Tests sind erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="3e0af-178">The tests pass.</span></span>

## <a name="debug-tests"></a><span data-ttu-id="3e0af-179">Debuggen von Tests</span><span class="sxs-lookup"><span data-stu-id="3e0af-179">Debug tests</span></span>

<span data-ttu-id="3e0af-180">Wenn Sie Visual Studio Code als IDE verwenden, können Sie den gleichen Prozess wie unter [Tutorial: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio Code](debugging-with-visual-studio-code.md) beschrieben verwenden, um Code mit Ihrem Komponententestprojekt zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-180">If you're using Visual Studio Code as your IDE, you can use the same process shown in [Debug a .NET console application using Visual Studio Code](debugging-with-visual-studio-code.md) to debug code using your unit test project.</span></span> <span data-ttu-id="3e0af-181">Anstatt das App-Projekt *ShowCase* zu starten, öffnen Sie *StringLibraryTest/UnitTest1.cs*, und wählen Sie **Alle Tests ausführen** zwischen den Zeilen 7 und 8 aus.</span><span class="sxs-lookup"><span data-stu-id="3e0af-181">Instead of starting the *ShowCase* app project, open *StringLibraryTest/UnitTest1.cs*, and select **Run All Tests** between lines 7 and 8.</span></span> <span data-ttu-id="3e0af-182">Wenn Sie den Test nicht finden können, drücken Sie <kbd>STRG</kbd>+<kbd>UMSCHALT</kbd>+<kbd>P</kbd>, um die Befehlspalette zu öffnen, und geben Sie **Fenster erneut Laden** ein.</span><span class="sxs-lookup"><span data-stu-id="3e0af-182">If you're unable to find it, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> to open the command palette and enter **Reload Window**.</span></span>

<span data-ttu-id="3e0af-183">Visual Studio Code startet das Testprojekt mit angefügtem Debugger.</span><span class="sxs-lookup"><span data-stu-id="3e0af-183">Visual Studio Code starts the test project with the debugger attached.</span></span> <span data-ttu-id="3e0af-184">Die Ausführung wird an jedem Haltepunkt angehalten, den Sie dem Testprojekt oder zugrunde liegenden Bibliothekscode hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="3e0af-184">Execution will stop at any breakpoint you've added to the test project or the underlying library code.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e0af-185">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="3e0af-185">Additional resources</span></span>

* [<span data-ttu-id="3e0af-186">Komponententests in .NET</span><span class="sxs-lookup"><span data-stu-id="3e0af-186">Unit testing in .NET</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="3e0af-187">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3e0af-187">Next steps</span></span>

<span data-ttu-id="3e0af-188">In diesem Tutorial haben Sie Komponententests für eine Klassenbibliothek ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3e0af-188">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="3e0af-189">Sie können die Bibliothek anderen Benutzern zur Verfügung stellen, indem Sie sie als Paket auf [NuGet](https://nuget.org) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="3e0af-189">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="3e0af-190">Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:</span><span class="sxs-lookup"><span data-stu-id="3e0af-190">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3e0af-191">Erstellen und Veröffentlichen eines Pakets mithilfe der dotnet-CLI</span><span class="sxs-lookup"><span data-stu-id="3e0af-191">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="3e0af-192">Wenn Sie eine Bibliothek als NuGet-Paket veröffentlichen, können andere Benutzer diese installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="3e0af-192">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="3e0af-193">Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:</span><span class="sxs-lookup"><span data-stu-id="3e0af-193">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3e0af-194">Installieren und Verwenden eines Pakets mithilfe der dotnet-CLI</span><span class="sxs-lookup"><span data-stu-id="3e0af-194">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="3e0af-195">Eine Bibliothek muss nicht als Paket verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="3e0af-195">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="3e0af-196">Sie kann mit einer Konsolen-App gebündelt werden, die sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="3e0af-196">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="3e0af-197">Informationen zum Veröffentlichen einer Konsolen-App finden Sie in einem früheren Tutorial dieser Reihe:</span><span class="sxs-lookup"><span data-stu-id="3e0af-197">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3e0af-198">Tutorial: Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3e0af-198">Publish a .NET console application using Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
