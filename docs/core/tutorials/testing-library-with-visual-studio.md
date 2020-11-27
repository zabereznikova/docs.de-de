---
title: Testen einer .NET-Klassenbibliothek mit Visual Studio
description: In diesem Artikel erfahren Sie, wie Sie Visual Studio zum Erstellen und Ausführen eines Komponententestprojekts für eine .NET-Klassenbibliothek verwenden.
ms.date: 11/18/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 3d56627b937fa0ad5f8002f396ce617e09ce9d2c
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916125"
---
# <a name="tutorial-test-a-net-class-library-with-net-using-visual-studio"></a><span data-ttu-id="4429a-103">Tutorial: Testen einer .NET-Klassenbibliothek mit .NET mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4429a-103">Tutorial: Test a .NET class library with .NET using Visual Studio</span></span>

<span data-ttu-id="4429a-104">In diesem Tutorial wird gezeigt, wie Sie Komponententests automatisieren, indem Sie einer Projektmappe ein Testprojekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4429a-104">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4429a-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4429a-105">Prerequisites</span></span>

- <span data-ttu-id="4429a-106">In diesem Tutorial wird die Projektmappe verwendet, die Sie in [Tutorial: Erstellen einer .NET-Klassenbibliothek in Visual Studio Code](library-with-visual-studio.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="4429a-106">This tutorial works with the solution that you create in [Create a .NET class library using Visual Studio](library-with-visual-studio.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="4429a-107">Ein Komponententestprojekt erstellen</span><span class="sxs-lookup"><span data-stu-id="4429a-107">Create a unit test project</span></span>

<span data-ttu-id="4429a-108">Komponententests bieten automatisierte Softwaretests während der Entwicklung und Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="4429a-108">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="4429a-109">[MSTest](https://github.com/Microsoft/testfx-docs) ist eines von drei Testframeworks, aus denen Sie wählen können.</span><span class="sxs-lookup"><span data-stu-id="4429a-109">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="4429a-110">Die beiden anderen sind [xUnit](https://xunit.net/) und [nUnit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="4429a-110">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="4429a-111">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4429a-111">Start Visual Studio.</span></span>

1. <span data-ttu-id="4429a-112">Öffnen Sie die Projektmappe `ClassLibraryProjects`, die Sie in [Tutorial: Erstellen einer .NET-Klassenbibliothek in Visual Studio Code](library-with-visual-studio.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="4429a-112">Open the `ClassLibraryProjects` solution you created in [Create a .NET class library using Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="4429a-113">Fügen Sie der Projektmappe ein neues Komponententestprojekt mit dem Namen „StringLibraryTest“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="4429a-113">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="4429a-114">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="4429a-114">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="4429a-115">Geben Sie auf der Seite **Neues Projekt hinzufügen** **mstest** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="4429a-115">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="4429a-116">Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus.</span><span class="sxs-lookup"><span data-stu-id="4429a-116">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="4429a-117">Wählen Sie die Vorlage **Komponententestprojekt** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4429a-117">Choose the **Unit Test Project** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="4429a-118">Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **StringLibraryTest** ein.</span><span class="sxs-lookup"><span data-stu-id="4429a-118">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="4429a-119">Wählen Sie anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="4429a-119">Then choose **Next**.</span></span>

   1. <span data-ttu-id="4429a-120">Wählen Sie auf der Seite **Zusätzliche Informationen** im Feld **Zielframework** die Option **.NET 5.0 (aktuell)** aus.</span><span class="sxs-lookup"><span data-stu-id="4429a-120">On the **Additional information** page, select **.NET 5.0 (Current)** in the **Target Framework** box.</span></span> <span data-ttu-id="4429a-121">Wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="4429a-121">Then choose **Create**.</span></span>

1. <span data-ttu-id="4429a-122">Visual Studio erstellt das Projekt und öffnet die Klassendatei mit dem folgenden Code im Codefenster.</span><span class="sxs-lookup"><span data-stu-id="4429a-122">Visual Studio creates the project and opens the class file in the code window with the following code.</span></span> <span data-ttu-id="4429a-123">Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.</span><span class="sxs-lookup"><span data-stu-id="4429a-123">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   ```vb
   Imports Microsoft.VisualStudio.TestTools.UnitTesting

   Namespace StringLibraryTest
       <TestClass>
       Public Class UnitTest1
           <TestMethod>
           Sub TestSub()

           End Sub
       End Class
   End Namespace
   ```

   <span data-ttu-id="4429a-124">Der von der Vorlage für Komponententests erstellte Quellcode führt Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4429a-124">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="4429a-125">Er importiert den Namespace <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, der für Komponententests verwendeten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="4429a-125">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="4429a-126">Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> auf die Klasse `UnitTest1` an.</span><span class="sxs-lookup"><span data-stu-id="4429a-126">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="4429a-127">Er wendet das <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>-Attribut an, um `TestMethod1` in C# oder `TestSub` in Visual Basic zu definieren.</span><span class="sxs-lookup"><span data-stu-id="4429a-127">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic.</span></span>

   <span data-ttu-id="4429a-128">Jede mit [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) gekennzeichnete Methode in einer mit [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) gekennzeichneten Testklasse wird automatisch ausgeführt, wenn der Komponententest ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4429a-128">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="4429a-129">Hinzufügen eines Projektverweises</span><span class="sxs-lookup"><span data-stu-id="4429a-129">Add a project reference</span></span>

<span data-ttu-id="4429a-130">Damit das Testprojekt mit der `StringLibrary`-Klasse funktioniert, fügen Sie im Projekt **StringLibraryTest** einen Verweis auf das Projekt `StringLibrary` hinzu.</span><span class="sxs-lookup"><span data-stu-id="4429a-130">For the test project to work with the `StringLibrary` class, add a reference in the **StringLibraryTest** project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="4429a-131">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für den Knoten **Abhängigkeiten** des **StringLibraryTest**-Projekts, und wählen Sie **Projektverweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="4429a-131">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Project Reference** from the context menu.</span></span>

1. <span data-ttu-id="4429a-132">Erweitern Sie im Dialogfeld **Verweis-Manager** den Knoten **Projekte**, und aktivieren Sie das Kontrollkästchen neben **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="4429a-132">In the **Reference Manager** dialog, expand the **Projects** node, and select the box next to **StringLibrary**.</span></span> <span data-ttu-id="4429a-133">Das Hinzufügen eines Verweises auf die `StringLibrary`-Assembly ermöglicht dem Compiler, **StringLibrary**-Methoden zu finden, wenn das **StringLibraryTest**-Projekt kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="4429a-133">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods while compiling the **StringLibraryTest** project.</span></span>

1. <span data-ttu-id="4429a-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4429a-134">Select **OK**.</span></span>

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="4429a-135">Hinzufügen und Ausführen von Komponententestmethoden</span><span class="sxs-lookup"><span data-stu-id="4429a-135">Add and run unit test methods</span></span>

<span data-ttu-id="4429a-136">Wenn Visual Studio einen Komponententest ausführt, erfolgt die Ausführung jeder Methode, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> gekennzeichnet ist, in einer Klasse, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="4429a-136">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="4429a-137">Eine Testmethode endet, wenn der erste Fehler gefunden wird, oder wenn alle in der Methode enthaltenen Tests erfolgreich ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="4429a-137">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="4429a-138">In den am häufigsten verwendeten Tests werden Member der Klasse <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4429a-138">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="4429a-139">Viele Assert-Methoden enthalten mindestens zwei Parameter, von denen einer das erwartete und der andere das tatsächliche Testergebnis ist.</span><span class="sxs-lookup"><span data-stu-id="4429a-139">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="4429a-140">Die am häufigsten aufgerufenen Methoden der `Assert`-Klasse werden in der nachfolgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="4429a-140">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="4429a-141">Assert-Methoden</span><span class="sxs-lookup"><span data-stu-id="4429a-141">Assert methods</span></span>     | <span data-ttu-id="4429a-142">Funktion</span><span class="sxs-lookup"><span data-stu-id="4429a-142">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="4429a-143">Überprüft, ob zwei Werte oder Objekte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="4429a-143">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="4429a-144">Der Assert ist nicht erfolgreich, wenn die Werte oder Objekte nicht gleich sind.</span><span class="sxs-lookup"><span data-stu-id="4429a-144">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="4429a-145">Überprüft, ob zwei Objektvariablen auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="4429a-145">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="4429a-146">Die Bestätigung ist nicht erfolgreich, wenn die Variablen auf verschiedene Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="4429a-146">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="4429a-147">Überprüft, ob eine Bedingung `false` ist.</span><span class="sxs-lookup"><span data-stu-id="4429a-147">Verifies that a condition is `false`.</span></span> <span data-ttu-id="4429a-148">Die Bestätigung ist nicht erfolgreich, wenn die Bedingung `true` ist.</span><span class="sxs-lookup"><span data-stu-id="4429a-148">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="4429a-149">Überprüft, ob ein Objekt nicht `null` ist.</span><span class="sxs-lookup"><span data-stu-id="4429a-149">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="4429a-150">Die Bestätigung ist nicht erfolgreich, wenn das Objekt `null` ist.</span><span class="sxs-lookup"><span data-stu-id="4429a-150">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="4429a-151">Sie können auch die <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType>-Methode in einer Testmethode verwenden, um den Typ der Ausnahme anzugeben, die ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="4429a-151">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="4429a-152">Der Test ist nicht erfolgreich, wenn die angegebene Ausnahme nicht ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="4429a-152">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="4429a-153">Beim Testen der `StringLibrary.StartsWithUpper`-Methode möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="4429a-153">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="4429a-154">Sie erwarten, dass die Methode in diesen Fällen `true` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4429a-154">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4429a-155">Außerdem möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die nicht mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="4429a-155">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="4429a-156">Sie erwarten, dass die Methode in diesen Fällen `false` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4429a-156">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="4429a-157">Da Ihre Bibliotheksmethode Zeichenfolgen verarbeitet, möchten Sie auch sicherstellen, dass sie eine [leere Zeichenfolge (`String.Empty`)](xref:System.String.Empty), eine gültige Zeichenfolge, die keine Zeichen enthält und deren <xref:System.String.Length> 0 ist, und eine `null`-Zeichenfolge, die nicht initialisiert wurde, erfolgreich verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="4429a-157">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="4429a-158">Sie können `StartsWithUpper` als statische Methode direkt aufrufen und ein einzelnes <xref:System.String>-Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="4429a-158">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="4429a-159">Alternativ können Sie `StartsWithUpper` als Erweiterungsmethode für eine `string`-Variable aufrufen, die `null` zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="4429a-159">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="4429a-160">Sie definieren drei Methoden, von denen jede eine zugehörige <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>-Methode für jedes Element in einem Zeichenfolgenarray aufruft.</span><span class="sxs-lookup"><span data-stu-id="4429a-160">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="4429a-161">Sie rufen eine Methodenüberladung auf, mit der Sie eine Fehlermeldung angeben können, die bei einem Testfehler angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4429a-161">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="4429a-162">Die Meldung enthält die Zeichenfolge, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="4429a-162">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="4429a-163">So erstellen Sie die Testmethoden:</span><span class="sxs-lookup"><span data-stu-id="4429a-163">To create the test methods:</span></span>

1. <span data-ttu-id="4429a-164">Ersetzen Sie den Code im Codefenster *UnitTest1.cs* oder *UnitTest1.vb* durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="4429a-164">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   <span data-ttu-id="4429a-165">Der Test für Großbuchstaben in der `TestStartsWithUpper`-Methode enthält den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+041C).</span><span class="sxs-lookup"><span data-stu-id="4429a-165">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="4429a-166">Der Test für Kleinbuchstaben in der `TestDoesNotStartWithUpper`-Methode enthält den griechischen Kleinbuchstaben alpha (U+03B1) und den kyrillischen Kleinbuchstaben ghe (U+0433).</span><span class="sxs-lookup"><span data-stu-id="4429a-166">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="4429a-167">Wählen Sie in der Menüleiste **Datei** > **UnitTest1.cs speichern unter** oder **Datei** > **UnitTest1.vb speichern unter** aus.</span><span class="sxs-lookup"><span data-stu-id="4429a-167">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="4429a-168">Wählen Sie im Dialogfeld **Datei speichern unter** den Pfeil neben der Schaltfläche **Speichern**, und wählen Sie dann **Mit Codierung speichern...** aus.</span><span class="sxs-lookup"><span data-stu-id="4429a-168">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/save-file-as-dialog.png" alt-text="Visual Studio-Dialogfeld „Datei speichern unter“":::

1. <span data-ttu-id="4429a-170">Wählen Sie im Dialogfeld **Speichern unter bestätigen** die Schaltfläche **Ja**, um die Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4429a-170">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="4429a-171">Wählen Sie im Dialogfeld **Erweiterte Speicheroptionen** **Unicode (UTF-8 mit Signatur) – Codepage 65001** aus der Dropdownliste **Codierung** aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4429a-171">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/advanced-save-options.png" alt-text="Visual Studio-Dialogfeld „Erweiterte Speicheroptionen“":::

   <span data-ttu-id="4429a-173">Wenn Sie den Quellcode nicht in einer UTF8-codierten Datei speichern, kann Visual Studio ihn als ASCII-Datei speichern.</span><span class="sxs-lookup"><span data-stu-id="4429a-173">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="4429a-174">Wenn dies geschieht, decodiert die Laufzeit die UTF8-Zeichen außerhalb des ASCII-Bereichs nicht ordnungsgemäß, und die Testergebnisse sind nicht richtig.</span><span class="sxs-lookup"><span data-stu-id="4429a-174">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="4429a-175">Wählen Sie auf der Menüleiste **Testen** > **Alle Tests ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="4429a-175">On the menu bar, select **Test** > **Run All Tests**.</span></span> <span data-ttu-id="4429a-176">Wenn das Fenster **Test-Explorer** nicht geöffnet ist, öffnen Sie es, indem Sie **Testen** > **Test-Explorer** auswählen.</span><span class="sxs-lookup"><span data-stu-id="4429a-176">If the **Test Explorer** window doesn't open, open it by choosing **Test** > **Test Explorer**.</span></span> <span data-ttu-id="4429a-177">Die drei Tests sind im Abschnitt **Bestandene Tests** aufgelistet, und im Abschnitt **Zusammenfassung** wird das Ergebnis des Testlaufs berichtet.</span><span class="sxs-lookup"><span data-stu-id="4429a-177">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/test-explorer-window.png" alt-text="Test Explorer-Fenster mit erfolgreichen Tests":::

## <a name="handle-test-failures"></a><span data-ttu-id="4429a-179">Behandeln von Testfehlern</span><span class="sxs-lookup"><span data-stu-id="4429a-179">Handle test failures</span></span>

<span data-ttu-id="4429a-180">Bei der testgesteuerten Entwicklung (Test-Driven Development, TDD) schreiben Sie zunächst Tests, bei deren ersten Ausführung Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="4429a-180">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="4429a-181">Anschließend fügen Sie der App Code hinzu, mit dem der Test erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4429a-181">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="4429a-182">Für dieses Tutorial haben Sie den Test, der den Code überprüft, nach Schreiben des App-Codes erstellt, sodass beim Test kein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4429a-182">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="4429a-183">Fügen Sie einen ungültigen Wert zur Testeingabe hinzu, um zu überprüfen, ob beim Test auch wirklich erwartungsgemäß ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="4429a-183">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="4429a-184">Verändern Sie das `words`-Array in der `TestDoesNotStartWithUpper`-Methode, um die Zeichenfolge "Error" einzufügen.</span><span class="sxs-lookup"><span data-stu-id="4429a-184">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="4429a-185">Sie müssen die Datei nicht speichern, das Visual Studio offene Dateien automatisch speichert, wenn eine Projektmappe zum Ausführen von Tests erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4429a-185">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="4429a-186">Führen Sie den Test aus, indem Sie auf der Menüleiste **Testen** > **Alle Tests ausführen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="4429a-186">Run the test by selecting **Test** > **Run All Tests** from the menu bar.</span></span> <span data-ttu-id="4429a-187">Das Fenster **Test-Explorer** zeigt, dass zwei Tests erfolgreich ausgeführt wurden und einer nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="4429a-187">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/failed-test-window.png" alt-text="Test Explorer-Fenster mit fehlschlagenden Tests":::

1. <span data-ttu-id="4429a-189">Wählen Sie den fehlgeschlagenen Test (`TestDoesNotStartWith`) aus.</span><span class="sxs-lookup"><span data-stu-id="4429a-189">Select the failed test, `TestDoesNotStartWith`.</span></span>

   <span data-ttu-id="4429a-190">Im Fenster **Test-Explorer** wird die Assert-Meldung angezeigt: „Fehler bei Assert.IsFalse.</span><span class="sxs-lookup"><span data-stu-id="4429a-190">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="4429a-191">Für 'Error' erwartet: False; tatsächlich: True“.</span><span class="sxs-lookup"><span data-stu-id="4429a-191">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="4429a-192">Wegen des Fehlers wurden keine auf „Error“ folgenden Zeichenfolgen im Array getestet.</span><span class="sxs-lookup"><span data-stu-id="4429a-192">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/failed-test-detail.png" alt-text="Fenster „Test-Explorer“, das den Assertionsfehler isFalse zeigt":::

1. <span data-ttu-id="4429a-194">Entfernen Sie die Zeichenfolge „Error“, die Sie in Schritt 1 hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="4429a-194">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="4429a-195">Führen Sie den Test erneut aus. Nun ist er erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="4429a-195">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="4429a-196">Testen der Releaseversion der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="4429a-196">Test the Release version of the library</span></span>

<span data-ttu-id="4429a-197">Nachdem die Tests beim Ausführen des Debugbuilds der Bibliothek nun alle erfolgreich waren, führen Sie die Tests auch für den Releasebuild der Bibliothek aus.</span><span class="sxs-lookup"><span data-stu-id="4429a-197">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="4429a-198">Eine Reihe von Faktoren einschließlich der Compileroptimierungen kann manchmal zu einem unterschiedlichen Verhalten von Debug- und endgültiger Produktversion führen.</span><span class="sxs-lookup"><span data-stu-id="4429a-198">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="4429a-199">So testen Sie die endgültige Produktversion:</span><span class="sxs-lookup"><span data-stu-id="4429a-199">To test the Release build:</span></span>

1. <span data-ttu-id="4429a-200">Ändern Sie in der Symbolleiste von Visual Studio die Buildkonfiguration von **Debuggen** zu **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="4429a-200">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Visual Studio-Symbolleiste mit hervorgehobenem Releasebuild":::

1. <span data-ttu-id="4429a-202">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **StringLibrary**-Projekt, und wählen Sie aus dem Kontextmenü **Erstellen** aus, um die Bibliothek erneut zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="4429a-202">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="./media/testing-library-with-visual-studio/build-library-context-menu.png" alt-text="StringLibrary-Kontextmenü mit Befehl „Erstellen“":::

1. <span data-ttu-id="4429a-204">Führen Sie den Komponententest aus, indem Sie auf der Menüleiste **Testen** > **Alle Tests** auswählen.</span><span class="sxs-lookup"><span data-stu-id="4429a-204">Run the unit tests by choosing **Test Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="4429a-205">Die Tests sind erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="4429a-205">The tests pass.</span></span>

## <a name="debug-tests"></a><span data-ttu-id="4429a-206">Debuggen von Tests</span><span class="sxs-lookup"><span data-stu-id="4429a-206">Debug tests</span></span>

<span data-ttu-id="4429a-207">Wenn Sie Visual Studio als IDE verwenden, können Sie den gleichen Prozess wie im [Tutorial: Debuggen einer .NET-Konsolenanwendung mit Visual Studio Code](debugging-with-visual-studio.md) beschrieben zum Debuggen von Code mithilfe Ihres Komponententestprojekts verwenden.</span><span class="sxs-lookup"><span data-stu-id="4429a-207">If you're using Visual Studio as your IDE, you can use the same process shown in [Tutorial: Debug a .NET console application using Visual Studio](debugging-with-visual-studio.md) to debug code using your unit test project.</span></span> <span data-ttu-id="4429a-208">Anstatt das App-Projekt *ShowCase* zu starten, klicken Sie erst mit der rechten Maustaste auf das Projekt **StringLibraryTests** und anschließend mit der linken im Kontextmenü auf **Tests debuggen**.</span><span class="sxs-lookup"><span data-stu-id="4429a-208">Instead of starting the *ShowCase* app project, right-click the **StringLibraryTests** project, and select **Debug Tests** from the context menu.</span></span>

<span data-ttu-id="4429a-209">Visual Studio startet das Testprojekt mit angefügtem Debugger.</span><span class="sxs-lookup"><span data-stu-id="4429a-209">Visual Studio starts the test project with the debugger attached.</span></span> <span data-ttu-id="4429a-210">Die Ausführung wird an jedem Haltepunkt angehalten, den Sie dem Testprojekt oder zugrunde liegenden Bibliothekscode hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="4429a-210">Execution will stop at any breakpoint you've added to the test project or the underlying library code.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4429a-211">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="4429a-211">Additional resources</span></span>

* [<span data-ttu-id="4429a-212">Grundlagen zu Komponententests: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4429a-212">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)
* [<span data-ttu-id="4429a-213">Komponententests in .NET</span><span class="sxs-lookup"><span data-stu-id="4429a-213">Unit testing in .NET</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="4429a-214">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4429a-214">Next steps</span></span>

<span data-ttu-id="4429a-215">In diesem Tutorial haben Sie Komponententests für eine Klassenbibliothek ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4429a-215">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="4429a-216">Sie können die Bibliothek anderen Benutzern zur Verfügung stellen, indem Sie sie als Paket auf [NuGet](https://nuget.org) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4429a-216">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="4429a-217">Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:</span><span class="sxs-lookup"><span data-stu-id="4429a-217">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4429a-218">Erstellen und Veröffentlichen eines NuGet-Pakets mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4429a-218">Create and publish a NuGet package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

<span data-ttu-id="4429a-219">Wenn Sie eine Bibliothek als NuGet-Paket veröffentlichen, können andere Benutzer diese installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="4429a-219">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="4429a-220">Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:</span><span class="sxs-lookup"><span data-stu-id="4429a-220">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4429a-221">Installieren und Verwenden eines Pakets in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4429a-221">Install and use a package in Visual Studio</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

<span data-ttu-id="4429a-222">Eine Bibliothek muss nicht als Paket verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="4429a-222">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="4429a-223">Sie kann mit einer Konsolen-App gebündelt werden, die sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="4429a-223">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="4429a-224">Informationen zum Veröffentlichen einer Konsolen-App finden Sie in einem früheren Tutorial dieser Reihe:</span><span class="sxs-lookup"><span data-stu-id="4429a-224">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4429a-225">Veröffentlichen einer .NET-Konsolenanwendung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4429a-225">Publish a .NET console application using Visual Studio</span></span>](publishing-with-visual-studio.md)
