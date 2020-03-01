---
title: Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio
description: Erstellen Sie ein Komponententestprojekt für Ihre .NET Core-Klassenbibliothek. Stellen Sie sicher, dass Ihre .NET Core-Klassenbibliothek mit Komponententests funktioniert.
ms.date: 12/24/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodoc18
ms.openlocfilehash: 307261088f5c7c69c0e69fbd6b99940c04842eec
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156620"
---
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio"></a><span data-ttu-id="42820-104">Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="42820-104">Test a .NET Standard library with .NET Core in Visual Studio</span></span>

<span data-ttu-id="42820-105">In [Erstellen einer .NET Standard-Bibliothek in Visual Studio](library-with-visual-studio.md) haben Sie eine einfache Klassenbibliothek erstellt, die der <xref:System.String>-Klasse eine Erweiterungsmethode hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="42820-105">In [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md), you created a simple class library that adds an extension method to the <xref:System.String> class.</span></span> <span data-ttu-id="42820-106">Jetzt erstellen Sie einen Komponententest, um sicherzustellen, dass es wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="42820-106">Now, you'll create a unit test to make sure that it works as expected.</span></span> <span data-ttu-id="42820-107">Sie fügen Ihr Komponententestprojekt der Projektmappe hinzu, die Sie im vorherigen Artikel erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="42820-107">You'll add your unit test project to the solution you created in the previous article.</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="42820-108">Ein Komponententestprojekt erstellen</span><span class="sxs-lookup"><span data-stu-id="42820-108">Create a unit test project</span></span>

<span data-ttu-id="42820-109">Um das Komponententestprojekt zu erstellen, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="42820-109">To create the unit test project, do the following:</span></span>

1. <span data-ttu-id="42820-110">Öffnen Sie die `ClassLibraryProjects`-Projektmappe, die Sie im Artikel [Erstellen einer .NET Standard-Bibliothek in Visual Studio](library-with-visual-studio.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="42820-110">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="42820-111">Fügen Sie der Projektmappe ein neues Komponententestprojekt mit dem Namen „StringLibraryTest“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="42820-111">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="42820-112">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="42820-112">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="42820-113">Geben Sie auf der Seite **Neues Projekt hinzufügen** **mstest** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="42820-113">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="42820-114">Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus.</span><span class="sxs-lookup"><span data-stu-id="42820-114">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="42820-115">Klicken Sie auf die Vorlage **MsTest-Testprojekt (.NET Core)** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="42820-115">Choose the **MsTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="42820-116">Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **StringLibraryTest** ein.</span><span class="sxs-lookup"><span data-stu-id="42820-116">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="42820-117">Wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="42820-117">Then choose **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="42820-118">Neben einem MSTest-Testprojekt können Sie auch xUnit- und nUnit-Testprojekte für .NET Core in Visual Studio erstellen.</span><span class="sxs-lookup"><span data-stu-id="42820-118">In addition to an MSTest, you can also create xUnit and nUnit test projects for .NET Core in Visual Studio.</span></span>

1. <span data-ttu-id="42820-119">Visual Studio erstellt das Projekt und öffnet die Klassendatei mit dem folgenden Code im Codefenster:</span><span class="sxs-lookup"><span data-stu-id="42820-119">Visual Studio creates the project and opens the class file in the code window with the following code:</span></span>

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

   <span data-ttu-id="42820-120">Der von der Vorlage für Komponententests erstellte Quellcode führt Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="42820-120">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="42820-121">Er importiert den Namespace <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, der für Komponententests verwendeten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="42820-121">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>

   - <span data-ttu-id="42820-122">Er wendet das [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute)-Attribut auf die `UnitTest1`-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="42820-122">It applies the [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="42820-123">Jede mit dem [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute)-Attribut markierte Testmethode in einer Testklasse wird automatisch ausgeführt, wenn der Komponententest ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="42820-123">Each test method in a test class tagged with the [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) attribute is executed automatically when the unit test is run.</span></span>

   - <span data-ttu-id="42820-124">Er wendet das Attribut [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) an, um `TestMethod1` in C# oder `TestSub` in Visual Basic als Testmethode für die automatische Ausführung beim Ausführen des Komponententests zu definieren.</span><span class="sxs-lookup"><span data-stu-id="42820-124">It applies the [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="42820-125">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für den Knoten **Abhängigkeiten** des **StringLibraryTest**-Projekts, und wählen Sie **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="42820-125">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42820-126">![Kontextmenü der StringLibraryTest-Abhängigkeiten](./media/testing-library-with-visual-studio/add-reference-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="42820-126">![Context menu of StringLibraryTest dependencies](./media/testing-library-with-visual-studio/add-reference-context-menu.png)</span></span>

1. <span data-ttu-id="42820-127">Erweitern Sie im Dialogfeld **Reference Manager** den Knoten **Projekte** und aktivieren Sie das Feld neben **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="42820-127">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="42820-128">Das Hinzufügen eines Verweises auf die `StringLibrary`-Assembly ermöglicht dem Compiler, **StringLibrary**-Methoden zu finden.</span><span class="sxs-lookup"><span data-stu-id="42820-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="42820-129">Klicken Sie auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="42820-129">Select the **OK** button.</span></span> <span data-ttu-id="42820-130">Ein Verweis auf Ihr Klassenbibliotheksprojekt (`StringLibrary`) wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="42820-130">A reference is added to your class library project, `StringLibrary`.</span></span>

   ![Dialogfeld „Verweis-Manager“ in Visual Studio](./media/testing-library-with-visual-studio/project-reference-manager.png)

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="42820-132">Hinzufügen und Ausführen von Komponententestmethoden</span><span class="sxs-lookup"><span data-stu-id="42820-132">Add and run unit test methods</span></span>

<span data-ttu-id="42820-133">Wenn Visual Studio einen Komponententest ausführt, wird jede Methode ausgeführt, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> in einer Komponententestklasse markiert ist: der Klasse, auf die das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="42820-133">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a unit test class, the class to which the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute is applied.</span></span> <span data-ttu-id="42820-134">Eine Testmethode endet, wenn der erste Fehler gefunden wird, oder wenn alle in der Methode enthaltenen Tests erfolgreich ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="42820-134">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="42820-135">In den am häufigsten verwendeten Tests werden Member der Klasse <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="42820-135">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="42820-136">Viele Assert-Methoden enthalten mindestens zwei Parameter, von denen einer das erwartete und der andere das tatsächliche Testergebnis ist.</span><span class="sxs-lookup"><span data-stu-id="42820-136">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="42820-137">Die am häufigsten aufgerufenen Methoden der `Assert`-Klasse werden in der nachfolgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="42820-137">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="42820-138">Assert-Methoden</span><span class="sxs-lookup"><span data-stu-id="42820-138">Assert methods</span></span>     | <span data-ttu-id="42820-139">Funktion</span><span class="sxs-lookup"><span data-stu-id="42820-139">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="42820-140">Überprüft, ob zwei Werte oder Objekte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="42820-140">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="42820-141">Der Assert ist nicht erfolgreich, wenn die Werte oder Objekte nicht gleich sind.</span><span class="sxs-lookup"><span data-stu-id="42820-141">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="42820-142">Überprüft, ob zwei Objektvariablen auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="42820-142">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="42820-143">Die Bestätigung ist nicht erfolgreich, wenn die Variablen auf verschiedene Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="42820-143">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="42820-144">Überprüft, ob eine Bedingung `false` ist.</span><span class="sxs-lookup"><span data-stu-id="42820-144">Verifies that a condition is `false`.</span></span> <span data-ttu-id="42820-145">Die Bestätigung ist nicht erfolgreich, wenn die Bedingung `true` ist.</span><span class="sxs-lookup"><span data-stu-id="42820-145">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="42820-146">Überprüft, ob ein Objekt nicht `null` ist.</span><span class="sxs-lookup"><span data-stu-id="42820-146">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="42820-147">Die Bestätigung ist nicht erfolgreich, wenn das Objekt `null` ist.</span><span class="sxs-lookup"><span data-stu-id="42820-147">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="42820-148">Sie können auch die <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A>-Methode in einer Testmethode verwenden, um den Typ der Ausnahme anzugeben, die ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="42820-148">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="42820-149">Der Test ist nicht erfolgreich, wenn die angegebene Ausnahme nicht ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="42820-149">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="42820-150">Beim Testen der `StringLibrary.StartsWithUpper`-Methode möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="42820-150">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="42820-151">Sie erwarten, dass die Methode in diesen Fällen `true` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="42820-151">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> method.</span></span> <span data-ttu-id="42820-152">Außerdem möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die nicht mit einem Großbuchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="42820-152">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="42820-153">Sie erwarten, dass die Methode in diesen Fällen `false` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="42820-153">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> method.</span></span>

<span data-ttu-id="42820-154">Da Ihre Bibliotheksmethode Zeichenfolgen verarbeitet, möchten Sie auch sicherstellen, dass sie eine [leere Zeichenfolge (`String.Empty`)](xref:System.String.Empty), eine gültige Zeichenfolge, die keine Zeichen enthält und deren <xref:System.String.Length> 0 ist, und eine `null`-Zeichenfolge, die nicht initialisiert wurde, erfolgreich verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="42820-154">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="42820-155">Wenn `StartsWithUpper` als eine Erweiterungsmethode für eine <xref:System.String>-Instanz aufgerufen wird, kann ihr keine `null`-Zeichenfolge übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="42820-155">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it can't be passed a `null` string.</span></span> <span data-ttu-id="42820-156">Allerdings kann sie auch direkt als statische Methode aufgerufen und ihr ein einzelnes <xref:System.String>-Argument übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="42820-156">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="42820-157">Sie definieren drei Methoden, von denen jede eine zugehörige Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> wiederholt für jedes Element in einem Zeichenfolgenarray aufruft.</span><span class="sxs-lookup"><span data-stu-id="42820-157">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="42820-158">Da die Testmethode nicht fortgesetzt wird, sobald sie den ersten Fehler findet, rufen Sie eine Methodenüberladung auf, mit der Sie eine Zeichenfolge übergeben können, die den Zeichenfolgenwert angibt, der im Methodenaufruf verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="42820-158">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="42820-159">So erstellen Sie die Testmethoden:</span><span class="sxs-lookup"><span data-stu-id="42820-159">To create the test methods:</span></span>

1. <span data-ttu-id="42820-160">Ersetzen Sie den Code im Codefenster *UnitTest1.cs* oder *UnitTest1.vb* durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="42820-160">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]
   [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   <span data-ttu-id="42820-161">Der Test für Großbuchstaben in der `TestStartsWithUpper`-Methode enthält den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+041C).</span><span class="sxs-lookup"><span data-stu-id="42820-161">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="42820-162">Der Test für Kleinbuchstaben in der `TestDoesNotStartWithUpper`-Methode enthält den griechischen Kleinbuchstaben alpha (U+03B1) und den kyrillischen Kleinbuchstaben ghe (U+0433).</span><span class="sxs-lookup"><span data-stu-id="42820-162">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="42820-163">Wählen Sie in der Menüleiste **Datei** > **UnitTest1.cs speichern unter** oder **Datei** > **UnitTest1.vb speichern unter** aus.</span><span class="sxs-lookup"><span data-stu-id="42820-163">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="42820-164">Wählen Sie im Dialogfeld **Datei speichern unter** den Pfeil neben der Schaltfläche **Speichern**, und wählen Sie dann **Mit Codierung speichern...** aus.</span><span class="sxs-lookup"><span data-stu-id="42820-164">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42820-165">![Visual Studio-Dialogfeld „Datei speichern unter“](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="42820-165">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="42820-166">Wählen Sie im Dialogfeld **Speichern unter bestätigen** die Schaltfläche **Ja**, um die Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="42820-166">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="42820-167">Wählen Sie im Dialogfeld **Erweiterte Speicheroptionen** **Unicode (UTF-8 mit Signatur) – Codepage 65001** aus der Dropdownliste **Codierung** aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="42820-167">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42820-168">![Visual Studio-Dialogfeld „Erweiterte Speicheroptionen“](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="42820-168">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="42820-169">Wenn Sie den Quellcode nicht in einer UTF8-codierten Datei speichern, kann Visual Studio ihn als ASCII-Datei speichern.</span><span class="sxs-lookup"><span data-stu-id="42820-169">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="42820-170">Wenn dies geschieht, decodiert die Laufzeit die UTF8-Zeichen außerhalb des ASCII-Bereichs nicht ordnungsgemäß, und die Testergebnisse sind nicht richtig.</span><span class="sxs-lookup"><span data-stu-id="42820-170">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="42820-171">Wählen Sie auf der Menüleiste **Test** > **Ausführen** > **Alle Tests** aus.</span><span class="sxs-lookup"><span data-stu-id="42820-171">On the menu bar, select **Test** > **Run** > **All Tests**.</span></span> <span data-ttu-id="42820-172">Das Fenster **Test-Explorer** wird geöffnet und zeigt, dass der Test erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="42820-172">The **Test Explorer** window opens and shows that the tests ran successfully.</span></span> <span data-ttu-id="42820-173">Die drei Tests sind im Abschnitt **Bestandene Tests** aufgelistet, und im Abschnitt **Zusammenfassung** wird das Ergebnis des Testlaufs berichtet.</span><span class="sxs-lookup"><span data-stu-id="42820-173">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42820-174">![Test Explorer-Fenster mit erfolgreichen Tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="42820-174">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="42820-175">Behandeln von Testfehlern</span><span class="sxs-lookup"><span data-stu-id="42820-175">Handle test failures</span></span>

<span data-ttu-id="42820-176">In Ihrem Testlauf sind keine Fehler aufgetreten, darum verändern Sie ihn leicht , sodass eine der Testmethoden nicht fortgesetzt wird:</span><span class="sxs-lookup"><span data-stu-id="42820-176">Your test run had no failures, but change it slightly so that one of the test methods fails:</span></span>

1. <span data-ttu-id="42820-177">Verändern Sie das `words`-Array in der `TestDoesNotStartWithUpper`-Methode, um die Zeichenfolge "Error" einzufügen.</span><span class="sxs-lookup"><span data-stu-id="42820-177">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="42820-178">Sie müssen die Datei nicht speichern, das Visual Studio offene Dateien automatisch speichert, wenn eine Projektmappe zum Ausführen von Tests erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="42820-178">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="42820-179">Führen Sie den Test aus, indem Sie **Test** > **Ausführen** > **Alle Tests** aus der Menüleiste auswählen.</span><span class="sxs-lookup"><span data-stu-id="42820-179">Run the test by selecting **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="42820-180">Das Fenster **Test-Explorer** zeigt, dass zwei Tests erfolgreich ausgeführt wurden und einer nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="42820-180">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42820-181">![Test Explorer-Fenster mit fehlschlagenden Tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="42820-181">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="42820-182">Wählen Sie den fehlgeschlagenen Test (`TestDoesNotStartWith`) aus.</span><span class="sxs-lookup"><span data-stu-id="42820-182">Select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="42820-183">Im Fenster **Test-Explorer** wird die Assert-Meldung angezeigt: „Fehler bei Assert.IsFalse.</span><span class="sxs-lookup"><span data-stu-id="42820-183">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="42820-184">Für 'Error' erwartet: False; tatsächlich: True“.</span><span class="sxs-lookup"><span data-stu-id="42820-184">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="42820-185">Wegen des Fehlers wurden alle auf „Error“ folgenden Zeichenfolgen im Array nicht getestet.</span><span class="sxs-lookup"><span data-stu-id="42820-185">Because of the failure, all strings in the array after "Error" weren't tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42820-186">![Fenster „Test-Explorer“, das den Assertionsfehler isFalse zeigt](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="42820-186">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="42820-187">Machen Sie die Änderung rückgängig, die Sie in Schritt 1 vorgenommen haben, und entfernen Sie die Zeichenfolge „Error“ (Fehler).</span><span class="sxs-lookup"><span data-stu-id="42820-187">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="42820-188">Führen Sie die Tests erneut aus, und sie werden erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="42820-188">Rerun the test and the tests will pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="42820-189">Testen der Releaseversion der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="42820-189">Test the Release version of the library</span></span>

<span data-ttu-id="42820-190">Sie haben Ihre Tests für die Debugversion der Bibliothek ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="42820-190">You've been running your tests against the Debug version of the library.</span></span> <span data-ttu-id="42820-191">Da nun alle Ihre Tests erfolgreich waren, und Sie Ihre Bibliothek ausreichend getestet haben, sollten Sie die Tests ein weiteres Mal für die endgültige Produktversion der Bibliothek ausführen.</span><span class="sxs-lookup"><span data-stu-id="42820-191">Now that your tests have all passed and you've adequately tested your library, you should run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="42820-192">Eine Reihe von Faktoren einschließlich der Compileroptimierungen kann manchmal zu einem unterschiedlichen Verhalten von Debug- und endgültiger Produktversion führen.</span><span class="sxs-lookup"><span data-stu-id="42820-192">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="42820-193">So testen Sie die endgültige Produktversion:</span><span class="sxs-lookup"><span data-stu-id="42820-193">To test the Release build:</span></span>

1. <span data-ttu-id="42820-194">Ändern Sie in der Symbolleiste von Visual Studio die Buildkonfiguration von **Debuggen** zu **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="42820-194">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42820-195">![Visual Studio-Symbolleiste mit hervorgehobenem Releasebuild](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="42820-195">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="42820-196">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **StringLibrary**-Projekt, und wählen Sie aus dem Kontextmenü **Erstellen** aus, um die Bibliothek erneut zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="42820-196">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42820-197">![StringLibrary-Kontextmenü mit Befehl „Erstellen“](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="42820-197">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="42820-198">Führen Sie den Komponententest aus, indem Sie **Test** > **Ausführen** > **Alle Tests** aus der Menüleiste auswählen.</span><span class="sxs-lookup"><span data-stu-id="42820-198">Run the unit tests by choosing **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="42820-199">Die Tests sind erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="42820-199">The tests pass.</span></span>

<span data-ttu-id="42820-200">Das Testen Ihrer Bibliothek ist jetzt abgeschlossen, und im nächsten Schritt machen Sie sie für die Aufrufer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="42820-200">Now that you've finished testing your library, the next step is to make it available to callers.</span></span> <span data-ttu-id="42820-201">Sie können sie mit einer oder mehreren Anwendungen bündeln oder sie als NuGet-Paket verteilen.</span><span class="sxs-lookup"><span data-stu-id="42820-201">You can bundle it with one or more applications, or you can distribute it as a NuGet package.</span></span> <span data-ttu-id="42820-202">Informationen hierzu finden Sie unter [Consuming a .NET Standard Class Library (Nutzen einer .NET-Standardklassenbibliothek)](consuming-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="42820-202">For more information, see [Consuming a .NET Standard Class Library](consuming-library-with-visual-studio.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="42820-203">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42820-203">See also</span></span>

- [<span data-ttu-id="42820-204">Grundlagen zu Komponententests: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="42820-204">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)
