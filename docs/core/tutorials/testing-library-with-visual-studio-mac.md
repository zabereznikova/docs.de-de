---
title: Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio für Mac
description: Erstellen Sie ein Komponententestprojekt für eine .NET Core-Klassenbibliothek. Sie überprüfen mithilfe von Komponententests, ob die .NET Core-Klassenbibliothek ordnungsgemäß funktioniert.
ms.date: 06/08/2020
ms.openlocfilehash: a183049623df44cbb8c4abd47ce6e78d91adae12
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713304"
---
# <a name="test-a-net-standard-class-library-with-net-core-using-visual-studio"></a><span data-ttu-id="d82bf-104">Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d82bf-104">Test a .NET Standard class library with .NET Core using Visual Studio</span></span>

<span data-ttu-id="d82bf-105">In diesem Tutorial wird gezeigt, wie Sie Komponententests automatisieren, indem Sie einer Projektmappe ein Testprojekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d82bf-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d82bf-106">Prerequisites</span></span>

- <span data-ttu-id="d82bf-107">In diesem Tutorial wird die Projektmappe verwendet, die Sie in [Erstellen einer .NET Standard-Bibliothek in Visual Studio für Mac](library-with-visual-studio-mac.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio for Mac](library-with-visual-studio-mac.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="d82bf-108">Ein Komponententestprojekt erstellen</span><span class="sxs-lookup"><span data-stu-id="d82bf-108">Create a unit test project</span></span>

<span data-ttu-id="d82bf-109">Komponententests bieten automatisierte Softwaretests während der Entwicklung und Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="d82bf-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="d82bf-110">[MSTest](https://github.com/Microsoft/testfx-docs) ist eines von drei Testframeworks, aus denen Sie wählen können.</span><span class="sxs-lookup"><span data-stu-id="d82bf-110">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="d82bf-111">Die beiden anderen sind [xUnit](https://xunit.net/) und [nUnit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="d82bf-111">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="d82bf-112">Starten Sie Visual Studio für Mac.</span><span class="sxs-lookup"><span data-stu-id="d82bf-112">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="d82bf-113">Öffnen Sie die `ClassLibraryProjects`-Projektmappe, die Sie in [Erstellen einer .NET Standard-Bibliothek in Visual Studio für Mac](library-with-visual-studio-mac.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d82bf-113">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio for Mac](library-with-visual-studio-mac.md).</span></span>

1. <span data-ttu-id="d82bf-114">Klicken Sie im Pad **Projektmappe** bei gedrückter <kbd>CTRL-TASTE</kbd> auf die Projektmappe `ClassLibraryProjects`, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-114">In the **Solution** pad, <kbd>ctrl</kbd>-click the `ClassLibraryProjects` solution and select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="d82bf-115">Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **Web und Konsole** die Option **Tests** aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-115">In the **New Project** dialog, select **Tests** from the **Web and Console** node.</span></span> <span data-ttu-id="d82bf-116">Wählen Sie das Projekt**MSTest-Projekt** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-116">Select the **MSTest Project** followed by **Next**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-project.png" alt-text="Visual Studio für Mac, Dialogfeld „Neues Projekt“, Erstellen des Testprojekts":::

1. <span data-ttu-id="d82bf-118">Wählen Sie die **.NET Core 3.1** aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-118">Select **.NET Core 3.1**.</span></span> <span data-ttu-id="d82bf-119">Nennen Sie das neue Projekt „StringLibraryTest“, und wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-119">Name the new project "StringLibraryTest" and select **Create**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-new-project-name.png" alt-text="Visual Studio für Mac, Dialogfeld „Neues Projekt“, Angeben des Projektnamens":::

   <span data-ttu-id="d82bf-121">Visual Studio erstellt eine Klassendatei mit folgendem Code:</span><span class="sxs-lookup"><span data-stu-id="d82bf-121">Visual Studio creates a class file with the following code:</span></span>

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

   <span data-ttu-id="d82bf-122">Der von der Vorlage für Komponententests erstellte Quellcode führt Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="d82bf-122">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="d82bf-123">Er importiert den Namespace <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, der für Komponententests verwendeten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="d82bf-123">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="d82bf-124">Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> auf die Klasse `UnitTest1` an.</span><span class="sxs-lookup"><span data-stu-id="d82bf-124">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="d82bf-125">Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> auf `TestMethod1` an.</span><span class="sxs-lookup"><span data-stu-id="d82bf-125">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to `TestMethod1`.</span></span>

   <span data-ttu-id="d82bf-126">Jede mit [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) gekennzeichnete Methode in einer mit [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) gekennzeichneten Testklasse wird automatisch ausgeführt, wenn der Komponententest ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d82bf-126">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="d82bf-127">Hinzufügen eines Projektverweises</span><span class="sxs-lookup"><span data-stu-id="d82bf-127">Add a project reference</span></span>

<span data-ttu-id="d82bf-128">Damit das Testprojekt mit der `StringLibrary`-Klasse funktioniert, fügen Sie einen Verweis auf das Projekt `StringLibrary` hinzu.</span><span class="sxs-lookup"><span data-stu-id="d82bf-128">For the test project to work with the `StringLibrary` class, add a reference to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="d82bf-129">Klicken Sie im Pad **Projektmappe** bei gedrückter <kbd>CTRL-TASTE</kbd> unter **StringLibraryTest** auf **Abhängigkeiten**.</span><span class="sxs-lookup"><span data-stu-id="d82bf-129">In the **Solution** pad, <kbd>ctrl</kbd>-click **Dependencies** under **StringLibraryTest**.</span></span> <span data-ttu-id="d82bf-130">Wählen Sie im Kontextmenü **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-130">Select **Add Reference** from the context menu.</span></span>

1. <span data-ttu-id="d82bf-131">Wählen Sie im Dialogfeld **Verweise** das Projekt **StringLibrary** aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-131">In the **References** dialog, select the **StringLibrary** project.</span></span> <span data-ttu-id="d82bf-132">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d82bf-132">Select **OK**.</span></span>

      :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-edit-references.png" alt-text="Visual Studio für Mac, Dialogfeld „Verweise bearbeiten“":::

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="d82bf-134">Hinzufügen und Ausführen von Komponententestmethoden</span><span class="sxs-lookup"><span data-stu-id="d82bf-134">Add and run unit test methods</span></span>

<span data-ttu-id="d82bf-135">Wenn Visual Studio einen Komponententest ausführt, erfolgt die Ausführung jeder Methode, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> gekennzeichnet ist, in einer Klasse, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="d82bf-135">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="d82bf-136">Eine Testmethode endet, wenn der erste Fehler gefunden wird, oder wenn alle in der Methode enthaltenen Tests erfolgreich ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="d82bf-136">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="d82bf-137">In den am häufigsten verwendeten Tests werden Member der Klasse <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-137">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="d82bf-138">Viele Assert-Methoden enthalten mindestens zwei Parameter, von denen einer das erwartete und der andere das tatsächliche Testergebnis ist.</span><span class="sxs-lookup"><span data-stu-id="d82bf-138">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="d82bf-139">Die am häufigsten aufgerufenen Methoden der `Assert`-Klasse werden in der nachfolgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="d82bf-139">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="d82bf-140">Assert-Methoden</span><span class="sxs-lookup"><span data-stu-id="d82bf-140">Assert methods</span></span>     | <span data-ttu-id="d82bf-141">Funktion</span><span class="sxs-lookup"><span data-stu-id="d82bf-141">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="d82bf-142">Überprüft, ob zwei Werte oder Objekte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="d82bf-142">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="d82bf-143">Der Assert ist nicht erfolgreich, wenn die Werte oder Objekte nicht gleich sind.</span><span class="sxs-lookup"><span data-stu-id="d82bf-143">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="d82bf-144">Überprüft, ob zwei Objektvariablen auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-144">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="d82bf-145">Die Bestätigung ist nicht erfolgreich, wenn die Variablen auf verschiedene Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-145">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="d82bf-146">Überprüft, ob eine Bedingung `false` ist.</span><span class="sxs-lookup"><span data-stu-id="d82bf-146">Verifies that a condition is `false`.</span></span> <span data-ttu-id="d82bf-147">Die Bestätigung ist nicht erfolgreich, wenn die Bedingung `true` ist.</span><span class="sxs-lookup"><span data-stu-id="d82bf-147">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="d82bf-148">Überprüft, ob ein Objekt nicht `null` ist.</span><span class="sxs-lookup"><span data-stu-id="d82bf-148">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="d82bf-149">Die Bestätigung ist nicht erfolgreich, wenn das Objekt `null` ist.</span><span class="sxs-lookup"><span data-stu-id="d82bf-149">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="d82bf-150">Sie können auch die <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType>-Methode in einer Testmethode verwenden, um den Typ der Ausnahme anzugeben, die ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="d82bf-150">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="d82bf-151">Der Test ist nicht erfolgreich, wenn die angegebene Ausnahme nicht ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="d82bf-151">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="d82bf-152">Beim Testen der `StringLibrary.StartsWithUpper`-Methode möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-152">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="d82bf-153">Sie erwarten, dass die Methode in diesen Fällen `true` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-153">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d82bf-154">Außerdem möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die nicht mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-154">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="d82bf-155">Sie erwarten, dass die Methode in diesen Fällen `false` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-155">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="d82bf-156">Da Ihre Bibliotheksmethode Zeichenfolgen verarbeitet, möchten Sie auch sicherstellen, dass sie eine [leere Zeichenfolge (`String.Empty`)](xref:System.String.Empty), eine gültige Zeichenfolge, die keine Zeichen enthält und deren <xref:System.String.Length> 0 ist, und eine `null`-Zeichenfolge, die nicht initialisiert wurde, erfolgreich verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d82bf-156">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="d82bf-157">Sie können `StartsWithUpper` als statische Methode direkt aufrufen und ein einzelnes <xref:System.String>-Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="d82bf-157">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="d82bf-158">Alternativ können Sie `StartsWithUpper` als Erweiterungsmethode für eine `string`-Variable aufrufen, die `null` zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="d82bf-158">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="d82bf-159">Sie definieren drei Methoden, von denen jede eine zugehörige <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>-Methode für jedes Element in einem Zeichenfolgenarray aufruft.</span><span class="sxs-lookup"><span data-stu-id="d82bf-159">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="d82bf-160">Sie rufen eine Methodenüberladung auf, mit der Sie eine Fehlermeldung angeben können, die bei einem Testfehler angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d82bf-160">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="d82bf-161">Die Meldung enthält die Zeichenfolge, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="d82bf-161">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="d82bf-162">So erstellen Sie die Testmethoden:</span><span class="sxs-lookup"><span data-stu-id="d82bf-162">To create the test methods:</span></span>

1. <span data-ttu-id="d82bf-163">Öffnen Sie die Datei *UnitTest1.cs*, und ersetzen Sie den Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="d82bf-163">Open the *UnitTest1.cs* file and replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="d82bf-164">Der Test für Großbuchstaben in der `TestStartsWithUpper`-Methode enthält den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+041C).</span><span class="sxs-lookup"><span data-stu-id="d82bf-164">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="d82bf-165">Der Test für Kleinbuchstaben in der `TestDoesNotStartWithUpper`-Methode enthält den griechischen Kleinbuchstaben alpha (U+03B1) und den kyrillischen Kleinbuchstaben ghe (U+0433).</span><span class="sxs-lookup"><span data-stu-id="d82bf-165">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="d82bf-166">Wählen Sie auf der Menüleiste **Datei** > **Speichern unter** aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-166">On the menu bar, select **File** > **Save As**.</span></span> <span data-ttu-id="d82bf-167">Stellen Sie im Dialogfeld sicher, dass **Codierung** auf **Unicode (UTF-8)** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d82bf-167">In the dialog, make sure that **Encoding** is set to **Unicode (UTF-8)**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/save-file-as-dialog.png" alt-text="Visual Studio-Dialogfeld „Datei speichern unter“":::

1. <span data-ttu-id="d82bf-169">Wenn Sie gefragt werden, ob Sie die vorhandene Datei ersetzen möchten, wählen Sie **Ersetzen** aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-169">When you're asked if you want to replace the existing file, select **Replace**.</span></span>

   <span data-ttu-id="d82bf-170">Wenn Sie den Quellcode nicht in einer UTF8-codierten Datei speichern, kann Visual Studio ihn als ASCII-Datei speichern.</span><span class="sxs-lookup"><span data-stu-id="d82bf-170">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="d82bf-171">Wenn dies geschieht, decodiert die Laufzeit die UTF8-Zeichen außerhalb des ASCII-Bereichs nicht ordnungsgemäß, und die Testergebnisse sind nicht richtig.</span><span class="sxs-lookup"><span data-stu-id="d82bf-171">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="d82bf-172">Öffnen Sie das Panel **Komponententests** auf der rechten Seite des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="d82bf-172">Open the **Unit Tests** panel on the right side of the screen.</span></span> <span data-ttu-id="d82bf-173">Wählen Sie **Ansicht** > **Tests** aus dem Menü aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-173">Select **View** > **Tests** from the menu.</span></span>

1. <span data-ttu-id="d82bf-174">Klicken Sie auf das **Andocksymbol**, um das Panel geöffnet zu lassen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-174">Click the **Dock** icon to keep the panel open.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-dock-icon.png" alt-text="Visual Studio für Mac, Andocksymbol im Bereich „Komponententests“":::

1. <span data-ttu-id="d82bf-176">Klicken Sie auf die Schaltfläche **Alle ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d82bf-176">Click the **Run All** button.</span></span>

   <span data-ttu-id="d82bf-177">Alle Tests erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d82bf-177">All tests pass.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-pass.png" alt-text="Visual Studio für Mac, erwarteter erfolgreicher Test":::

## <a name="handle-test-failures"></a><span data-ttu-id="d82bf-179">Behandeln von Testfehlern</span><span class="sxs-lookup"><span data-stu-id="d82bf-179">Handle test failures</span></span>

<span data-ttu-id="d82bf-180">Bei der testgesteuerten Entwicklung (Test-Driven Development, TDD) schreiben Sie zunächst Tests, bei deren ersten Ausführung Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="d82bf-180">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="d82bf-181">Anschließend fügen Sie der App Code hinzu, mit dem der Test erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d82bf-181">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="d82bf-182">Für dieses Tutorial haben Sie den Test, der den Code überprüft, nach Schreiben des App-Codes erstellt, sodass beim Test kein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d82bf-182">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="d82bf-183">Fügen Sie einen ungültigen Wert zur Testeingabe hinzu, um zu überprüfen, ob beim Test auch wirklich erwartungsgemäß ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="d82bf-183">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="d82bf-184">Verändern Sie das `words`-Array in der `TestDoesNotStartWithUpper`-Methode, um die Zeichenfolge "Error" einzufügen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-184">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="d82bf-185">Sie müssen die Datei nicht speichern, das Visual Studio offene Dateien automatisch speichert, wenn eine Projektmappe zum Ausführen von Tests erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d82bf-185">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="d82bf-186">Führen Sie die Tests erneut aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-186">Run the tests again.</span></span>

   <span data-ttu-id="d82bf-187">Das Fenster **Test-Explorer** zeigt nun an, dass zwei Tests erfolgreich waren und einer nicht.</span><span class="sxs-lookup"><span data-stu-id="d82bf-187">This time, the **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/failed-test-window.png" alt-text="Test Explorer-Fenster mit fehlschlagenden Tests":::

1. <span data-ttu-id="d82bf-189">Klicken Sie bei gedrückter <kbd>CTRL-TASTE</kbd> auf den fehlgeschlagenen Test, `TestDoesNotStartWithUpper`. Wählen Sie im Kontextmenü **Ergebnisbereich anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-189"><kbd>ctrl</kbd>-click the failed test, `TestDoesNotStartWithUpper`, and select **Show Results Pad** from the context menu.</span></span>

   <span data-ttu-id="d82bf-190">Im Pad **Ergebnisse** wird die Meldung angezeigt, die von Assert generiert wurde: „Fehler bei Assert.IsFalse.</span><span class="sxs-lookup"><span data-stu-id="d82bf-190">The **Results** pad displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="d82bf-191">Für 'Error' erwartet: False; tatsächlich: True“.</span><span class="sxs-lookup"><span data-stu-id="d82bf-191">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="d82bf-192">Wegen des Fehlers wurden keine auf „Error“ folgenden Zeichenfolgen im Array getestet.</span><span class="sxs-lookup"><span data-stu-id="d82bf-192">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-failure.png" alt-text="Fenster „Test-Explorer“, das den Assertionsfehler isFalse zeigt":::

1. <span data-ttu-id="d82bf-194">Entfernen Sie die Zeichenfolge „Error“, die Sie in Schritt 1 hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="d82bf-194">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="d82bf-195">Führen Sie den Test erneut aus. Nun ist er erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d82bf-195">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="d82bf-196">Testen der Releaseversion der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="d82bf-196">Test the Release version of the library</span></span>

<span data-ttu-id="d82bf-197">Nachdem die Tests beim Ausführen des Debugbuilds der Bibliothek nun alle erfolgreich waren, führen Sie die Tests auch für den Releasebuild der Bibliothek aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-197">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="d82bf-198">Eine Reihe von Faktoren einschließlich der Compileroptimierungen kann manchmal zu einem unterschiedlichen Verhalten von Debug- und endgültiger Produktversion führen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-198">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="d82bf-199">So testen Sie die endgültige Produktversion:</span><span class="sxs-lookup"><span data-stu-id="d82bf-199">To test the Release build:</span></span>

1. <span data-ttu-id="d82bf-200">Ändern Sie in der Symbolleiste von Visual Studio die Buildkonfiguration von **Debuggen** zu **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="d82bf-200">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Visual Studio-Symbolleiste mit hervorgehobenem Releasebuild":::

1. <span data-ttu-id="d82bf-202">Klicken Sie im Pad **Projektmappe** bei gedrückter <kbd>CTRL-TASTE</kbd> auf das Projekt **StringLibrary**, und wählen Sie im Kontextmenü **Build** aus, um die Bibliothek erneut zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="d82bf-202">In the **Solution** pad, <kbd>ctrl</kbd>-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/build-library-context-menu.png" alt-text="StringLibrary-Kontextmenü mit Befehl „Erstellen“":::

1. <span data-ttu-id="d82bf-204">Führen Sie die Komponententests erneut aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-204">Run the unit tests again.</span></span>

   <span data-ttu-id="d82bf-205">Die Tests sind erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d82bf-205">The tests pass.</span></span>

## <a name="debug-tests"></a><span data-ttu-id="d82bf-206">Debuggen von Tests</span><span class="sxs-lookup"><span data-stu-id="d82bf-206">Debug tests</span></span>

<span data-ttu-id="d82bf-207">Sie können denselben im [Tutorial: Debuggen einer .NET Core-Konsolenanwendung in Visual Studio für Mac](debugging-with-visual-studio-mac.md) gezeigten Prozess befolgen, um Code mithilfe Ihres Komponententestprojekts zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-207">You can use the same process shown in [Tutorial: Debug a .NET Core console application using Visual Studio for Mac](debugging-with-visual-studio-mac.md) to debug code using your unit test project.</span></span> <span data-ttu-id="d82bf-208">Anstatt das App-Projekt ShowCase zu starten, klicken Sie bei gedrückter <kbd>CTRL-TASTE</kbd> auf das Projekt **StringLibraryTests**. Wählen Sie dann im Kontextmenü **Debuggen des Projekts starten** aus.</span><span class="sxs-lookup"><span data-stu-id="d82bf-208">Instead of starting the ShowCase app project, <kbd>ctrl</kbd>-click the **StringLibraryTests** project, and select **Start Debugging Project** from the context menu.</span></span> <span data-ttu-id="d82bf-209">Visual Studio startet das Testprojekt mit angefügtem Debugger.</span><span class="sxs-lookup"><span data-stu-id="d82bf-209">Visual Studio starts the test project with the debugger attached.</span></span> <span data-ttu-id="d82bf-210">Die Ausführung wird an jedem Haltepunkt angehalten, den Sie dem Testprojekt oder zugrunde liegenden Bibliothekscode hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="d82bf-210">Execution will stop at any breakpoint you've added to the test project or the underlying library code.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d82bf-211">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d82bf-211">Additional resources</span></span>

* [<span data-ttu-id="d82bf-212">Komponententests in .NET Core und .NET Standard</span><span class="sxs-lookup"><span data-stu-id="d82bf-212">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="d82bf-213">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d82bf-213">Next steps</span></span>

<span data-ttu-id="d82bf-214">In diesem Tutorial haben Sie Komponententests für eine Klassenbibliothek ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d82bf-214">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="d82bf-215">Sie können die Bibliothek anderen Benutzern zur Verfügung stellen, indem Sie sie als Paket auf [NuGet](https://nuget.org) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="d82bf-215">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="d82bf-216">Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:</span><span class="sxs-lookup"><span data-stu-id="d82bf-216">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d82bf-217">Erstellen und Veröffentlichen eines Pakets (dotnet CLI)</span><span class="sxs-lookup"><span data-stu-id="d82bf-217">Create and publish a package (dotnet CLI)</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="d82bf-218">Wenn Sie eine Bibliothek als NuGet-Paket veröffentlichen, können andere Benutzer diese installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="d82bf-218">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="d82bf-219">Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:</span><span class="sxs-lookup"><span data-stu-id="d82bf-219">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d82bf-220">Installieren und Verwenden eines Pakets in Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="d82bf-220">Install and use a package in Visual Studio for Mac</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio-mac)

<span data-ttu-id="d82bf-221">Eine Bibliothek muss nicht als Paket verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="d82bf-221">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="d82bf-222">Sie kann mit einer Konsolen-App gebündelt werden, die sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="d82bf-222">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="d82bf-223">Informationen zum Veröffentlichen einer Konsolen-App finden Sie in einem früheren Tutorial dieser Reihe:</span><span class="sxs-lookup"><span data-stu-id="d82bf-223">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d82bf-224">Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="d82bf-224">Publish a .NET Core console application with Visual Studio for Mac</span></span>](publishing-with-visual-studio-mac.md)
