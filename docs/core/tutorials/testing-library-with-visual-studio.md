---
title: Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio
description: Erstellen Sie ein Komponententestprojekt für Ihre .NET Core-Klassenbibliothek. Stellen Sie sicher, dass Ihre .NET Core-Klassenbibliothek mit Komponententests funktioniert.
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 79b680022484bb9222b66c3df76bdd5a06de8117
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005010"
---
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio"></a><span data-ttu-id="c7984-104">Tutorial: Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7984-104">Tutorial: Test a .NET Standard library with .NET Core in Visual Studio</span></span>

<span data-ttu-id="c7984-105">In diesem Tutorial wird gezeigt, wie Sie Komponententests automatisieren, indem Sie einer Projektmappe ein Testprojekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c7984-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c7984-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c7984-106">Prerequisites</span></span>

- <span data-ttu-id="c7984-107">In diesem Tutorial wird die Projektmappe verwendet, die Sie in [Erstellen einer .NET Standard-Bibliothek in Visual Studio](library-with-visual-studio.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="c7984-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="c7984-108">Ein Komponententestprojekt erstellen</span><span class="sxs-lookup"><span data-stu-id="c7984-108">Create a unit test project</span></span>

1. <span data-ttu-id="c7984-109">Öffnen Sie die `ClassLibraryProjects`-Projektmappe, die Sie in [Erstellen einer .NET Standard-Bibliothek in Visual Studio](library-with-visual-studio.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="c7984-109">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="c7984-110">Fügen Sie der Projektmappe ein neues Komponententestprojekt mit dem Namen „StringLibraryTest“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="c7984-110">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="c7984-111">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="c7984-111">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="c7984-112">Geben Sie auf der Seite **Neues Projekt hinzufügen** **mstest** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="c7984-112">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="c7984-113">Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus.</span><span class="sxs-lookup"><span data-stu-id="c7984-113">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="c7984-114">Klicken Sie auf die Vorlage **MSTest-Testprojekt (.NET Core)** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c7984-114">Choose the **MSTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="c7984-115">Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **StringLibraryTest** ein.</span><span class="sxs-lookup"><span data-stu-id="c7984-115">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="c7984-116">Wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="c7984-116">Then choose **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c7984-117">MSTest ist eines von drei Testframeworks, unter denen Sie wählen können.</span><span class="sxs-lookup"><span data-stu-id="c7984-117">MSTest is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="c7984-118">Die beiden anderen sind xUnit und nUnit.</span><span class="sxs-lookup"><span data-stu-id="c7984-118">The others are xUnit and nUnit.</span></span>

1. <span data-ttu-id="c7984-119">Visual Studio erstellt das Projekt und öffnet die Klassendatei mit dem folgenden Code im Codefenster.</span><span class="sxs-lookup"><span data-stu-id="c7984-119">Visual Studio creates the project and opens the class file in the code window with the following code.</span></span> <span data-ttu-id="c7984-120">Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.</span><span class="sxs-lookup"><span data-stu-id="c7984-120">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   <span data-ttu-id="c7984-121">Der von der Vorlage für Komponententests erstellte Quellcode führt Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="c7984-121">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="c7984-122">Er importiert den Namespace <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, der für Komponententests verwendeten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="c7984-122">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="c7984-123">Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> auf die Klasse `UnitTest1` an.</span><span class="sxs-lookup"><span data-stu-id="c7984-123">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="c7984-124">Er wendet das <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>-Attribut an, um `TestMethod1` in C# oder `TestSub` in Visual Basic zu definieren.</span><span class="sxs-lookup"><span data-stu-id="c7984-124">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic.</span></span>

   <span data-ttu-id="c7984-125">Jede mit [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) gekennzeichnete Methode in einer mit [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) gekennzeichneten Testklasse wird automatisch ausgeführt, wenn der Komponententest ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c7984-125">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="c7984-126">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für den Knoten **Abhängigkeiten** des **StringLibraryTest**-Projekts, und wählen Sie **Projektverweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="c7984-126">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Project Reference** from the context menu.</span></span>

1. <span data-ttu-id="c7984-127">Erweitern Sie im Dialogfeld **Verweis-Manager** den Knoten **Projekte**, und aktivieren Sie das Kontrollkästchen neben **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="c7984-127">In the **Reference Manager** dialog, expand the **Projects** node, and select the box next to **StringLibrary**.</span></span> <span data-ttu-id="c7984-128">Das Hinzufügen eines Verweises auf die `StringLibrary`-Assembly ermöglicht dem Compiler, **StringLibrary**-Methoden zu finden, wenn das **StringLibraryTest**-Projekt kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="c7984-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods while compiling the **StringLibraryTest** project.</span></span>

1. <span data-ttu-id="c7984-129">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7984-129">Select **OK**.</span></span>

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="c7984-130">Hinzufügen und Ausführen von Komponententestmethoden</span><span class="sxs-lookup"><span data-stu-id="c7984-130">Add and run unit test methods</span></span>

<span data-ttu-id="c7984-131">Wenn Visual Studio einen Komponententest ausführt, erfolgt die Ausführung jeder Methode, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> gekennzeichnet ist, in einer Klasse, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="c7984-131">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="c7984-132">Eine Testmethode endet, wenn der erste Fehler gefunden wird, oder wenn alle in der Methode enthaltenen Tests erfolgreich ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="c7984-132">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="c7984-133">In den am häufigsten verwendeten Tests werden Member der Klasse <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c7984-133">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="c7984-134">Viele Assert-Methoden enthalten mindestens zwei Parameter, von denen einer das erwartete und der andere das tatsächliche Testergebnis ist.</span><span class="sxs-lookup"><span data-stu-id="c7984-134">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="c7984-135">Die am häufigsten aufgerufenen Methoden der `Assert`-Klasse werden in der nachfolgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c7984-135">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="c7984-136">Assert-Methoden</span><span class="sxs-lookup"><span data-stu-id="c7984-136">Assert methods</span></span>     | <span data-ttu-id="c7984-137">Funktion</span><span class="sxs-lookup"><span data-stu-id="c7984-137">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="c7984-138">Überprüft, ob zwei Werte oder Objekte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="c7984-138">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="c7984-139">Der Assert ist nicht erfolgreich, wenn die Werte oder Objekte nicht gleich sind.</span><span class="sxs-lookup"><span data-stu-id="c7984-139">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="c7984-140">Überprüft, ob zwei Objektvariablen auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="c7984-140">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="c7984-141">Die Bestätigung ist nicht erfolgreich, wenn die Variablen auf verschiedene Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="c7984-141">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="c7984-142">Überprüft, ob eine Bedingung `false` ist.</span><span class="sxs-lookup"><span data-stu-id="c7984-142">Verifies that a condition is `false`.</span></span> <span data-ttu-id="c7984-143">Die Bestätigung ist nicht erfolgreich, wenn die Bedingung `true` ist.</span><span class="sxs-lookup"><span data-stu-id="c7984-143">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="c7984-144">Überprüft, ob ein Objekt nicht `null` ist.</span><span class="sxs-lookup"><span data-stu-id="c7984-144">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="c7984-145">Die Bestätigung ist nicht erfolgreich, wenn das Objekt `null` ist.</span><span class="sxs-lookup"><span data-stu-id="c7984-145">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="c7984-146">Sie können auch die <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType>-Methode in einer Testmethode verwenden, um den Typ der Ausnahme anzugeben, die ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7984-146">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="c7984-147">Der Test ist nicht erfolgreich, wenn die angegebene Ausnahme nicht ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c7984-147">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="c7984-148">Beim Testen der `StringLibrary.StartsWithUpper`-Methode möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="c7984-148">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="c7984-149">Sie erwarten, dass die Methode in diesen Fällen `true` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c7984-149">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c7984-150">Außerdem möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die nicht mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="c7984-150">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="c7984-151">Sie erwarten, dass die Methode in diesen Fällen `false` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c7984-151">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="c7984-152">Da Ihre Bibliotheksmethode Zeichenfolgen verarbeitet, möchten Sie auch sicherstellen, dass sie eine [leere Zeichenfolge (`String.Empty`)](xref:System.String.Empty), eine gültige Zeichenfolge, die keine Zeichen enthält und deren <xref:System.String.Length> 0 ist, und eine `null`-Zeichenfolge, die nicht initialisiert wurde, erfolgreich verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c7984-152">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="c7984-153">Wenn `StartsWithUpper` als eine Erweiterungsmethode für eine <xref:System.String>-Instanz aufgerufen wird, kann ihr keine `null`-Zeichenfolge übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c7984-153">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it can't be passed a `null` string.</span></span> <span data-ttu-id="c7984-154">Allerdings kann sie auch direkt als statische Methode aufgerufen und ihr ein einzelnes <xref:System.String>-Argument übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c7984-154">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="c7984-155">Sie definieren drei Methoden, von denen jede eine zugehörige Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> wiederholt für jedes Element in einem Zeichenfolgenarray aufruft.</span><span class="sxs-lookup"><span data-stu-id="c7984-155">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="c7984-156">Da die Testmethode nicht fortgesetzt wird, sobald sie den ersten Fehler findet, rufen Sie eine Methodenüberladung auf, mit der Sie eine Zeichenfolge übergeben können, die den Zeichenfolgenwert angibt, der im Methodenaufruf verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7984-156">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="c7984-157">So erstellen Sie die Testmethoden:</span><span class="sxs-lookup"><span data-stu-id="c7984-157">To create the test methods:</span></span>

1. <span data-ttu-id="c7984-158">Ersetzen Sie den Code im Codefenster *UnitTest1.cs* oder *UnitTest1.vb* durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="c7984-158">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]
   [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   <span data-ttu-id="c7984-159">Der Test für Großbuchstaben in der `TestStartsWithUpper`-Methode enthält den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+041C).</span><span class="sxs-lookup"><span data-stu-id="c7984-159">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="c7984-160">Der Test für Kleinbuchstaben in der `TestDoesNotStartWithUpper`-Methode enthält den griechischen Kleinbuchstaben alpha (U+03B1) und den kyrillischen Kleinbuchstaben ghe (U+0433).</span><span class="sxs-lookup"><span data-stu-id="c7984-160">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="c7984-161">Wählen Sie in der Menüleiste **Datei** > **UnitTest1.cs speichern unter** oder **Datei** > **UnitTest1.vb speichern unter** aus.</span><span class="sxs-lookup"><span data-stu-id="c7984-161">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="c7984-162">Wählen Sie im Dialogfeld **Datei speichern unter** den Pfeil neben der Schaltfläche **Speichern**, und wählen Sie dann **Mit Codierung speichern...** aus.</span><span class="sxs-lookup"><span data-stu-id="c7984-162">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7984-163">![Visual Studio-Dialogfeld „Datei speichern unter“](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="c7984-163">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="c7984-164">Wählen Sie im Dialogfeld **Speichern unter bestätigen** die Schaltfläche **Ja**, um die Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c7984-164">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="c7984-165">Wählen Sie im Dialogfeld **Erweiterte Speicheroptionen** **Unicode (UTF-8 mit Signatur) – Codepage 65001** aus der Dropdownliste **Codierung** aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7984-165">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7984-166">![Visual Studio-Dialogfeld „Erweiterte Speicheroptionen“](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="c7984-166">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="c7984-167">Wenn Sie den Quellcode nicht in einer UTF8-codierten Datei speichern, kann Visual Studio ihn als ASCII-Datei speichern.</span><span class="sxs-lookup"><span data-stu-id="c7984-167">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="c7984-168">Wenn dies geschieht, decodiert die Laufzeit die UTF8-Zeichen außerhalb des ASCII-Bereichs nicht ordnungsgemäß, und die Testergebnisse sind nicht richtig.</span><span class="sxs-lookup"><span data-stu-id="c7984-168">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="c7984-169">Wählen Sie auf der Menüleiste **Testen** > **Alle Tests ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="c7984-169">On the menu bar, select **Test** > **Run All Tests**.</span></span> <span data-ttu-id="c7984-170">Wenn das Fenster **Test-Explorer** nicht geöffnet ist, öffnen Sie es, indem Sie **Testen** > **Test-Explorer** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c7984-170">If the **Test Explorer** window doesn't open, open it by choosing **Test** > **Test Explorer**.</span></span> <span data-ttu-id="c7984-171">Die drei Tests sind im Abschnitt **Bestandene Tests** aufgelistet, und im Abschnitt **Zusammenfassung** wird das Ergebnis des Testlaufs berichtet.</span><span class="sxs-lookup"><span data-stu-id="c7984-171">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7984-172">![Test Explorer-Fenster mit erfolgreichen Tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="c7984-172">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="c7984-173">Behandeln von Testfehlern</span><span class="sxs-lookup"><span data-stu-id="c7984-173">Handle test failures</span></span>

<span data-ttu-id="c7984-174">In Ihrem Testlauf sind keine Fehler aufgetreten, darum verändern Sie ihn leicht , sodass eine der Testmethoden nicht fortgesetzt wird:</span><span class="sxs-lookup"><span data-stu-id="c7984-174">Your test run had no failures, but change it slightly so that one of the test methods fails:</span></span>

1. <span data-ttu-id="c7984-175">Verändern Sie das `words`-Array in der `TestDoesNotStartWithUpper`-Methode, um die Zeichenfolge "Error" einzufügen.</span><span class="sxs-lookup"><span data-stu-id="c7984-175">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="c7984-176">Sie müssen die Datei nicht speichern, das Visual Studio offene Dateien automatisch speichert, wenn eine Projektmappe zum Ausführen von Tests erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c7984-176">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="c7984-177">Führen Sie den Test aus, indem Sie auf der Menüleiste **Testen** > **Alle Tests ausführen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c7984-177">Run the test by selecting **Test** > **Run All Tests** from the menu bar.</span></span> <span data-ttu-id="c7984-178">Das Fenster **Test-Explorer** zeigt, dass zwei Tests erfolgreich ausgeführt wurden und einer nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="c7984-178">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7984-179">![Test Explorer-Fenster mit fehlschlagenden Tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="c7984-179">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="c7984-180">Wählen Sie den fehlgeschlagenen Test (`TestDoesNotStartWith`) aus.</span><span class="sxs-lookup"><span data-stu-id="c7984-180">Select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="c7984-181">Im Fenster **Test-Explorer** wird die Assert-Meldung angezeigt: „Fehler bei Assert.IsFalse.</span><span class="sxs-lookup"><span data-stu-id="c7984-181">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="c7984-182">Für 'Error' erwartet: False; tatsächlich: True“.</span><span class="sxs-lookup"><span data-stu-id="c7984-182">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="c7984-183">Wegen des Fehlers wurden alle auf „Error“ folgenden Zeichenfolgen im Array nicht getestet.</span><span class="sxs-lookup"><span data-stu-id="c7984-183">Because of the failure, all strings in the array after "Error" weren't tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7984-184">![Fenster „Test-Explorer“, das den Assertionsfehler isFalse zeigt](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="c7984-184">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="c7984-185">Machen Sie die Änderung rückgängig, die Sie in Schritt 1 vorgenommen haben, und entfernen Sie die Zeichenfolge „Error“ (Fehler).</span><span class="sxs-lookup"><span data-stu-id="c7984-185">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="c7984-186">Führen Sie den Test erneut aus. Nun ist er erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="c7984-186">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="c7984-187">Testen der Releaseversion der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="c7984-187">Test the Release version of the library</span></span>

<span data-ttu-id="c7984-188">Nachdem die Tests beim Ausführen der Debugversion der Bibliothek nun alle erfolgreich waren, führen Sie die Tests auch für den Releasebuild der Bibliothek aus.</span><span class="sxs-lookup"><span data-stu-id="c7984-188">Now that the tests have all passed when running the Debug version of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="c7984-189">Eine Reihe von Faktoren einschließlich der Compileroptimierungen kann manchmal zu einem unterschiedlichen Verhalten von Debug- und endgültiger Produktversion führen.</span><span class="sxs-lookup"><span data-stu-id="c7984-189">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="c7984-190">So testen Sie die endgültige Produktversion:</span><span class="sxs-lookup"><span data-stu-id="c7984-190">To test the Release build:</span></span>

1. <span data-ttu-id="c7984-191">Ändern Sie in der Symbolleiste von Visual Studio die Buildkonfiguration von **Debuggen** zu **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="c7984-191">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7984-192">![Visual Studio-Symbolleiste mit hervorgehobenem Releasebuild](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="c7984-192">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="c7984-193">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **StringLibrary**-Projekt, und wählen Sie aus dem Kontextmenü **Erstellen** aus, um die Bibliothek erneut zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="c7984-193">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7984-194">![StringLibrary-Kontextmenü mit Befehl „Erstellen“](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="c7984-194">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="c7984-195">Führen Sie den Komponententest aus, indem Sie auf der Menüleiste **Testen** > **Alle Tests** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c7984-195">Run the unit tests by choosing **Test Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="c7984-196">Die Tests sind erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="c7984-196">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c7984-197">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c7984-197">Additional resources</span></span>

- [<span data-ttu-id="c7984-198">Grundlagen zu Komponententests: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7984-198">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)

## <a name="next-steps"></a><span data-ttu-id="c7984-199">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c7984-199">Next steps</span></span>

<span data-ttu-id="c7984-200">In diesem Tutorial haben Sie Komponententests für eine Klassenbibliothek ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c7984-200">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="c7984-201">Sie können die Bibliothek anderen Benutzern zur Verfügung stellen, indem Sie sie als Paket auf [NuGet](https://nuget.org) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="c7984-201">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="c7984-202">Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:</span><span class="sxs-lookup"><span data-stu-id="c7984-202">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c7984-203">Erstellen und Veröffentlichen eines NuGet-Pakets mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7984-203">Create and publish a NuGet package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

<span data-ttu-id="c7984-204">Wenn Sie eine Bibliothek als NuGet-Paket veröffentlichen, können andere Benutzer diese installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7984-204">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="c7984-205">Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:</span><span class="sxs-lookup"><span data-stu-id="c7984-205">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c7984-206">Installieren und Verwenden eines Pakets in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7984-206">Install and use a package in Visual Studio</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

<span data-ttu-id="c7984-207">Eine Bibliothek muss nicht als Paket verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="c7984-207">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="c7984-208">Sie kann mit einer Konsolen-App gebündelt werden, die sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7984-208">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="c7984-209">Informationen zum Veröffentlichen einer Konsolen-App finden Sie in einem früheren Tutorial dieser Reihe:</span><span class="sxs-lookup"><span data-stu-id="c7984-209">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c7984-210">Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7984-210">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
