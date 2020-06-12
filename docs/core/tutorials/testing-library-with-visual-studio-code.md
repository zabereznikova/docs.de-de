---
title: Testen einer .NET Standard-Klassenbibliothek mit .NET Core in Visual Studio Code
description: Erstellen Sie ein Komponententestprojekt für eine .NET Core-Klassenbibliothek. Sie überprüfen mithilfe von Komponententests, ob die .NET Core-Klassenbibliothek ordnungsgemäß funktioniert.
ms.date: 05/29/2020
ms.openlocfilehash: be227453bd441028cc6ce348c00fad944140238f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292162"
---
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio-code"></a><span data-ttu-id="093d9-104">Tutorial: Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="093d9-104">Tutorial: Test a .NET Standard library with .NET Core in Visual Studio Code</span></span>

<span data-ttu-id="093d9-105">In diesem Tutorial wird gezeigt, wie Sie Komponententests automatisieren, indem Sie einer Projektmappe ein Testprojekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="093d9-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="093d9-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="093d9-106">Prerequisites</span></span>

- <span data-ttu-id="093d9-107">In diesem Tutorial wird die Projektmappe verwendet, die Sie in [Erstellen einer .NET Standard-Bibliothek in Visual Studio Code](library-with-visual-studio-code.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="093d9-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="093d9-108">Ein Komponententestprojekt erstellen</span><span class="sxs-lookup"><span data-stu-id="093d9-108">Create a unit test project</span></span>

1. <span data-ttu-id="093d9-109">Öffnen Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="093d9-109">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="093d9-110">Öffnen Sie die `ClassLibraryProjects`-Projektmappe, die Sie in [Erstellen einer .NET Standard-Bibliothek in Visual Studio](library-with-visual-studio.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="093d9-110">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="093d9-111">Erstellen Sie ein Komponententestprojekt namens „StringLibraryTest“.</span><span class="sxs-lookup"><span data-stu-id="093d9-111">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="093d9-112">Die Projektvorlage erstellt die Datei „UnitTest1.cs“, die den folgenden Code enthält:</span><span class="sxs-lookup"><span data-stu-id="093d9-112">The project template creates a UnitTest1.cs file with the following code:</span></span>

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

   <span data-ttu-id="093d9-113">Der von der Vorlage für Komponententests erstellte Quellcode führt Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="093d9-113">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="093d9-114">Er importiert den Namespace <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, der für Komponententests verwendeten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="093d9-114">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="093d9-115">Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> auf die Klasse `UnitTest1` an.</span><span class="sxs-lookup"><span data-stu-id="093d9-115">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="093d9-116">Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> an, um `TestMethod1` zu definieren.</span><span class="sxs-lookup"><span data-stu-id="093d9-116">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="093d9-117">Jede mit [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) gekennzeichnete Methode in einer mit [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) gekennzeichneten Testklasse wird automatisch ausgeführt, wenn der Komponententest ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="093d9-117">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

   > [!NOTE]
   > <span data-ttu-id="093d9-118">MSTest ist eines von drei Testframeworks, unter denen Sie wählen können.</span><span class="sxs-lookup"><span data-stu-id="093d9-118">MSTest is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="093d9-119">Die beiden anderen sind xUnit und nUnit.</span><span class="sxs-lookup"><span data-stu-id="093d9-119">The others are xUnit and nUnit.</span></span>

1. <span data-ttu-id="093d9-120">Fügen Sie das Testprojekt zur Projektmappe hinzu.</span><span class="sxs-lookup"><span data-stu-id="093d9-120">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

1. <span data-ttu-id="093d9-121">Führen Sie den folgenden Befehl aus, um einen Projektverweis auf das Klassenbibliotheksprojekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="093d9-121">Create a project reference to the class library project by running the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="093d9-122">Hinzufügen und Ausführen von Komponententestmethoden</span><span class="sxs-lookup"><span data-stu-id="093d9-122">Add and run unit test methods</span></span>

<span data-ttu-id="093d9-123">Wenn Visual Studio einen Komponententest ausführt, erfolgt die Ausführung jeder Methode, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> gekennzeichnet ist, in einer Klasse, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="093d9-123">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="093d9-124">Eine Testmethode endet, wenn der erste Fehler gefunden wird, oder wenn alle in der Methode enthaltenen Tests erfolgreich ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="093d9-124">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="093d9-125">In den am häufigsten verwendeten Tests werden Member der Klasse <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="093d9-125">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="093d9-126">Viele Assert-Methoden enthalten mindestens zwei Parameter, von denen einer das erwartete und der andere das tatsächliche Testergebnis ist.</span><span class="sxs-lookup"><span data-stu-id="093d9-126">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="093d9-127">Die am häufigsten aufgerufenen Methoden der `Assert`-Klasse werden in der nachfolgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="093d9-127">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="093d9-128">Assert-Methoden</span><span class="sxs-lookup"><span data-stu-id="093d9-128">Assert methods</span></span>     | <span data-ttu-id="093d9-129">Funktion</span><span class="sxs-lookup"><span data-stu-id="093d9-129">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="093d9-130">Überprüft, ob zwei Werte oder Objekte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="093d9-130">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="093d9-131">Der Assert ist nicht erfolgreich, wenn die Werte oder Objekte nicht gleich sind.</span><span class="sxs-lookup"><span data-stu-id="093d9-131">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="093d9-132">Überprüft, ob zwei Objektvariablen auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="093d9-132">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="093d9-133">Die Bestätigung ist nicht erfolgreich, wenn die Variablen auf verschiedene Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="093d9-133">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="093d9-134">Überprüft, ob eine Bedingung `false` ist.</span><span class="sxs-lookup"><span data-stu-id="093d9-134">Verifies that a condition is `false`.</span></span> <span data-ttu-id="093d9-135">Die Bestätigung ist nicht erfolgreich, wenn die Bedingung `true` ist.</span><span class="sxs-lookup"><span data-stu-id="093d9-135">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="093d9-136">Überprüft, ob ein Objekt nicht `null` ist.</span><span class="sxs-lookup"><span data-stu-id="093d9-136">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="093d9-137">Die Bestätigung ist nicht erfolgreich, wenn das Objekt `null` ist.</span><span class="sxs-lookup"><span data-stu-id="093d9-137">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="093d9-138">Sie können auch die <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType>-Methode in einer Testmethode verwenden, um den Typ der Ausnahme anzugeben, die ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="093d9-138">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="093d9-139">Der Test ist nicht erfolgreich, wenn die angegebene Ausnahme nicht ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="093d9-139">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="093d9-140">Beim Testen der `StringLibrary.StartsWithUpper`-Methode möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="093d9-140">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="093d9-141">Sie erwarten, dass die Methode in diesen Fällen `true` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="093d9-141">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="093d9-142">Außerdem möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die nicht mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="093d9-142">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="093d9-143">Sie erwarten, dass die Methode in diesen Fällen `false` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="093d9-143">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="093d9-144">Da Ihre Bibliotheksmethode Zeichenfolgen verarbeitet, sollten Sie sicherstellen, dass sie eine [leere Zeichenfolge (`String.Empty`)](xref:System.String.Empty) und eine `null`-Zeichenfolge erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="093d9-144">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="093d9-145">Eine leere Zeichenfolge enthält keine Zeichen, und ihre <xref:System.String.Length>-Eigenschaft weist den Wert „0“ auf.</span><span class="sxs-lookup"><span data-stu-id="093d9-145">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="093d9-146">Eine `null`-Zeichenfolge ist eine Zeichenfolge, die nicht initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="093d9-146">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="093d9-147">Sie können `StartsWithUpper` als statische Methode direkt aufrufen und ein einzelnes <xref:System.String>-Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="093d9-147">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="093d9-148">Alternativ können Sie `StartsWithUpper` als Erweiterungsmethode für eine `string`-Variable aufrufen, die `null` zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="093d9-148">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="093d9-149">Sie definieren drei Methoden, von denen jede eine zugehörige Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> wiederholt für jedes Element in einem Zeichenfolgenarray aufruft.</span><span class="sxs-lookup"><span data-stu-id="093d9-149">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="093d9-150">Da die Testmethode nicht fortgesetzt wird, sobald sie den ersten Fehler findet, rufen Sie eine Methodenüberladung auf, mit der Sie eine Zeichenfolge übergeben können, die den Zeichenfolgenwert angibt, der im Methodenaufruf verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="093d9-150">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="093d9-151">So erstellen Sie die Testmethoden:</span><span class="sxs-lookup"><span data-stu-id="093d9-151">To create the test methods:</span></span>

1. <span data-ttu-id="093d9-152">Öffnen Sie die Datei *StringLibraryTest/UnitTest1.cs*, und ersetzen Sie den gesamten Code durch den folgenden:</span><span class="sxs-lookup"><span data-stu-id="093d9-152">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="093d9-153">Der Test für Großbuchstaben in der `TestStartsWithUpper`-Methode enthält den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+041C).</span><span class="sxs-lookup"><span data-stu-id="093d9-153">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="093d9-154">Der Test für Kleinbuchstaben in der `TestDoesNotStartWithUpper`-Methode enthält den griechischen Kleinbuchstaben alpha (U+03B1) und den kyrillischen Kleinbuchstaben ghe (U+0433).</span><span class="sxs-lookup"><span data-stu-id="093d9-154">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="093d9-155">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="093d9-155">Save your changes.</span></span>

1. <span data-ttu-id="093d9-156">Führen Sie die Tests aus:</span><span class="sxs-lookup"><span data-stu-id="093d9-156">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="093d9-157">Die Terminalausgabe gibt an, dass alle Tests bestanden wurden.</span><span class="sxs-lookup"><span data-stu-id="093d9-157">The terminal output shows that all tests passed.</span></span>

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
   Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="093d9-158">Behandeln von Testfehlern</span><span class="sxs-lookup"><span data-stu-id="093d9-158">Handle test failures</span></span>

<span data-ttu-id="093d9-159">Bei der testgesteuerten Entwicklung (Test-Driven Development, TDD) schreiben Sie zunächst Tests, bei deren ersten Ausführung Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="093d9-159">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="093d9-160">Anschließend fügen Sie der App Code hinzu, mit dem der Test erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="093d9-160">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="093d9-161">In diesem Fall haben Sie den Test, der den Code überprüft, nach Schreiben des App-Codes erstellt, sodass beim Test kein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="093d9-161">In this case, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="093d9-162">Fügen Sie einen ungültigen Wert zur Testeingabe hinzu, um zu überprüfen, ob beim Test auch wirklich erwartungsgemäß ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="093d9-162">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="093d9-163">Verändern Sie das `words`-Array in der `TestDoesNotStartWithUpper`-Methode, um die Zeichenfolge "Error" einzufügen.</span><span class="sxs-lookup"><span data-stu-id="093d9-163">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="093d9-164">Führen Sie die Tests aus:</span><span class="sxs-lookup"><span data-stu-id="093d9-164">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="093d9-165">Die Terminalausgabe zeigt, dass bei einem Test ein Fehler auftritt, und gibt eine Fehlermeldung für diesen Test an.</span><span class="sxs-lookup"><span data-stu-id="093d9-165">The terminal output shows that one test fails, and it provides an error message for the failed test.</span></span>

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.
     X TestDoesNotStartWithUpper [283ms]
     Error Message:
      Assert.IsFalse failed. Expected for 'Error': false; Actual: True
     Stack Trace:
     at StringLibraryTest.UnitTest1.TestDoesNotStartWithUpper()
       in C:\Projects\ClassLibraryProjects\StringLibraryTest\UnitTest1.cs:line 33

   Test Run Failed.
   Total tests: 3
        Passed: 2
        Failed: 1
   Total time: 1.7825 Seconds
   ```

1. <span data-ttu-id="093d9-166">Machen Sie die Änderung rückgängig, die Sie in Schritt 1 vorgenommen haben, und entfernen Sie die Zeichenfolge „Error“ (Fehler).</span><span class="sxs-lookup"><span data-stu-id="093d9-166">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="093d9-167">Führen Sie den Test erneut aus. Nun ist er erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="093d9-167">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="093d9-168">Testen der Releaseversion der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="093d9-168">Test the Release version of the library</span></span>

<span data-ttu-id="093d9-169">Nachdem die Tests beim Ausführen der Debugversion der Bibliothek nun alle erfolgreich waren, führen Sie die Tests auch für den Releasebuild der Bibliothek aus.</span><span class="sxs-lookup"><span data-stu-id="093d9-169">Now that the tests have all passed when running the Debug version of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="093d9-170">Eine Reihe von Faktoren einschließlich der Compileroptimierungen kann manchmal zu einem unterschiedlichen Verhalten von Debug- und endgültiger Produktversion führen.</span><span class="sxs-lookup"><span data-stu-id="093d9-170">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="093d9-171">Führen Sie die Tests mit der Releasebuildkonfiguration aus:</span><span class="sxs-lookup"><span data-stu-id="093d9-171">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="093d9-172">Die Tests sind erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="093d9-172">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="093d9-173">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="093d9-173">Additional resources</span></span>

- [<span data-ttu-id="093d9-174">Komponententests in .NET Core und .NET Standard</span><span class="sxs-lookup"><span data-stu-id="093d9-174">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="093d9-175">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="093d9-175">Next steps</span></span>

<span data-ttu-id="093d9-176">In diesem Tutorial haben Sie Komponententests für eine Klassenbibliothek ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="093d9-176">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="093d9-177">Sie können die Bibliothek anderen Benutzern zur Verfügung stellen, indem Sie sie als Paket auf [NuGet](https://nuget.org) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="093d9-177">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="093d9-178">Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:</span><span class="sxs-lookup"><span data-stu-id="093d9-178">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="093d9-179">Erstellen und Veröffentlichen eines Pakets mithilfe der dotnet-CLI</span><span class="sxs-lookup"><span data-stu-id="093d9-179">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="093d9-180">Wenn Sie eine Bibliothek als NuGet-Paket veröffentlichen, können andere Benutzer diese installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="093d9-180">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="093d9-181">Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:</span><span class="sxs-lookup"><span data-stu-id="093d9-181">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="093d9-182">Installieren und Verwenden eines Pakets mithilfe der dotnet-CLI</span><span class="sxs-lookup"><span data-stu-id="093d9-182">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="093d9-183">Eine Bibliothek muss nicht als Paket verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="093d9-183">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="093d9-184">Sie kann mit einer Konsolen-App gebündelt werden, die sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="093d9-184">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="093d9-185">Informationen zum Veröffentlichen einer Konsolen-App finden Sie in einem früheren Tutorial dieser Reihe:</span><span class="sxs-lookup"><span data-stu-id="093d9-185">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="093d9-186">Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="093d9-186">Publish a .NET Core console application with Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
