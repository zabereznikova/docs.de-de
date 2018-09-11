---
title: Testen einer Klassenbibliothek mit .NET Core in Visual Studio 2017
description: Erfahren Sie, wie Sie eine in C# geschriebene Klassenbibliothek mithilfe von Visual Studio 2017 testen.
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
dev_langs:
- csharp
- vb
ms.openlocfilehash: 8ea958ad5d3eba394eb914da81111a0eaf707cf4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43398877"
---
# <a name="testing-a-class-library-with-net-core-in-visual-studio-2017"></a>Testen einer Klassenbibliothek mit .NET Core in Visual Studio 2017

In [Building a class library with C# and .NET Core in Visual Studio 2017 (Erstellen einer Klassenbibliothek mit C# und .NET Core in Visual Studio2017)](library-with-visual-studio.md) oder [Building a class library with Visual Basic and .NET Core in Visual Studio 2017 (Erstellen einer Klassenbibliothek mit Visual Basic und .NET Core in Visual Studio 2017)](vb-library-with-visual-studio.md) haben Sie eine einfache Klassenbibliothek erstellt, die eine Erweiterungsmethode zur Klasse <xref:System.String> hinzufügt. Jetzt erstellen Sie einen Komponententest, um sicherzustellen, dass es wie erwartet funktioniert. Sie fügen Ihr Komponententestprojekt der Projektmappe hinzu, die Sie im vorherigen Thema erstellt haben.

## <a name="creating-a-unit-test-project"></a>Erstellen eines Komponententestprojekts

Um das Komponententestprojekt zu erstellen, führen Sie folgende Schritte aus:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü des Projektmappenknotens **ClassLibraryProject**, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.

1. Klicken Sie auf den Knoten **Visual C#** im Dialogfeld **Neues Projekt hinzufügen**. Klicken Sie dann auf den Knoten **.NET Core**, gefolgt von der Projektvorlage **MSTest-Testprojekt (.NET Core)**. Geben Sie im Textfeld **Name** „StringLibraryTest“ als Namen des Projekts ein. Klicken Sie auf **OK**, um das Komponententestprojekt zu erstellen

   ![Dialogfeld „Neues Projekt hinzufügen“](./media/testing-library-with-visual-studio/testproject.png)

   > [!NOTE]  
   > Neben einem MSTest-Testprojekt können Sie auch Visual Studio verwenden, um ein xUnit-Testprojekt für .NET Core zu erstellen.

1. Visual Studio erstellt das Projekt und öffnet die *UnitTest1.cs*-Datei im Codefenster.

   ![Das Codefenster von Visual Studio zeigt das standardmäßige UnitTest1-Klasse und TestMethod1-Methode des Komponententestprojekts.](./media/testing-library-with-visual-studio/unittestwindow.png)

   Der von der Vorlage für Komponententests erstellte Quellcode führt Folgendes aus:

   * Er importiert den Namespace <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, der für Komponententests verwendeten Typen enthält.

   * Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> auf die Klasse `UnitTest1` an. Jede mit dem \[TestMethod\]-Attribut markierte Testmethode in einer Testklasse wird automatisch ausgeführt, wenn der Komponententest ausgeführt wird.

   * Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> an, um `TestMethod1` als Testmethode für die automatische Ausführung zu definieren, wenn der Komponententest ausgeführt wird.

1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für den Knoten **Abhängigkeiten** des **StringLibraryTest**-Projekts, und wählen Sie **Verweis hinzufügen** aus.

   ![Kontextmenü der StringLibraryTest-Abhängigkeiten](./media/testing-library-with-visual-studio/addreference.png)

1. Erweitern Sie im Dialogfeld **Reference Manager** den Knoten **Projekte** und aktivieren Sie das Feld neben **StringLibrary**. Das Hinzufügen eines Verweises auf die `StringLibrary`-Assembly ermöglicht dem Compiler, **StringLibrary**-Methoden zu finden. Klicken Sie auf die Schaltfläche **OK**. Dadurch wird ein Verweis auf Ihr Klassenbibliotheksprojekt, `StringLibrary`, hinzugefügt.

   ![Verweis-Manager](./media/testing-library-with-visual-studio/referencemanager.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic) 
1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü des Projektmappenknotens **ClassLibraryProject**, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.

1. Klicken Sie auf den Knoten **Visual Basic** im Dialogfeld **Neues Projekt hinzufügen**. Klicken Sie dann auf den Knoten **.NET Core**, gefolgt von der Projektvorlage **MSTest-Testprojekt (.NET Core)**. Geben Sie im Textfeld **Name** „StringLibraryTest“ als Namen des Projekts ein. Klicken Sie auf **OK**, um das Komponententestprojekt zu erstellen

   ![Dialogfeld „Neues Projekt hinzufügen“](./media/testing-library-with-visual-studio/vb-testproject.png)

   > [!NOTE]  
   > Neben einem MSTest-Testprojekt können Sie auch Visual Studio verwenden, um ein xUnit-Testprojekt für .NET Core zu erstellen.

1. Visual Studio erstellt das Projekt und öffnet die *UnitTest1.vb*-Datei im Codefenster.

   ![Das Codefenster von Visual Studio zeigt das standardmäßige UnitTest1-Klasse und TestMethod1-Methode des Komponententestprojekts.](./media/testing-library-with-visual-studio/vb-unittestwindow.png)

   Der von der Vorlage für Komponententests erstellte Quellcode führt Folgendes aus:

   * Er importiert den Namespace [Microsoft.VisualStudio.TestTools.UnitTesting]<xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=namewithType>, der die für Komponententests verwendeten Typen enthält.

   * Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> auf die Klasse `UnitTest1` an. Jede mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> markierte Testmethode in einer Testklasse wird bei Ausführung des Komponententests automatisch ausgeführt.

   * Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> an, um `TestMethod1` als Testmethode für die automatische Ausführung zu definieren, wenn der Komponententest ausgeführt wird.

1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für den Knoten **Abhängigkeiten** des **StringLibraryTest**-Projekts, und wählen Sie **Verweis hinzufügen** aus.

   ![Kontextmenü der StringLibraryTest-Abhängigkeiten](./media/testing-library-with-visual-studio/addreference.png)

1. Erweitern Sie im Dialogfeld **Reference Manager** den Knoten **Projekte** und aktivieren Sie das Feld neben **StringLibrary**. Das Hinzufügen eines Verweises auf die `StringLibrary`-Assembly ermöglicht dem Compiler, **StringLibrary**-Methoden zu finden. Klicken Sie auf die Schaltfläche **OK**. Dadurch wird ein Verweis auf Ihr Klassenbibliotheksprojekt, `StringLibrary`, hinzugefügt.

   ![Verweis-Manager](./media/testing-library-with-visual-studio/referencemanager.png)
---

## <a name="adding-and-running-unit-test-methods"></a>Hinzufügen und Ausführen von Komponententestmethoden

Wenn Visual Studio einen Komponententest ausführt, wird jede Methode in einer Komponententestklasse – der Klasse, auf die das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> angewendet wird – ausgeführt, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> markiert ist. Eine Testmethode endet, wenn der erste Fehler aufgetreten ist, oder wenn alle in der Methode enthaltenen Tests erfolgreich ausgeführt wurden.

In den am häufigsten verwendeten Tests werden Member der Klasse <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> aufgerufen. Viele Assert-Methoden enthalten mindestens zwei Parameter, von denen einer das erwartete und der andere das tatsächliche Testergebnis ist. Die am häufigsten aufgerufenen Methoden sind in der nachfolgenden Tabelle aufgeführt.

Assert-Methoden | Funktion
--- | ---
`Assert.AreEqual` | Überprüft, ob zwei Werte oder Objekte gleich sind. Die Bestätigung ist nicht erfolgreich, wenn die Werte oder Objekte nicht gleich sind.
`Assert.AreSame` | Überprüft, ob zwei Objektvariablen auf das gleiche Objekt verweisen. Die Bestätigung ist nicht erfolgreich, wenn die Variablen auf verschiedene Objekte verweisen.
`Assert.IsFalse` | Überprüft, ob eine Bedingung `false` ist. Die Bestätigung ist nicht erfolgreich, wenn die Bedingung `true` ist.
`Assert.IsNotNull` | Überprüft, ob ein Objekt nicht `null` ist. Die Bestätigung ist nicht erfolgreich, wenn das Objekt `null` ist.

Sie können auch das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> auf eine Testmethode anwenden. Es gibt den Typ der Ausnahme an, die eine Testmethode auslösen soll. Der Test ist nicht erfolgreich, wenn die angegebene Ausnahme nicht ausgelöst wird.

Beim Testen der `StringLibrary.StartsWithUpper`-Methode möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die mit einem Großbuchstaben beginnen. Sie erwarten, dass die Methode in diesen Fällen `true` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> aufrufen. Außerdem möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die nicht mit einem Großbuchstaben beginnen. Sie erwarten, dass die Methode in diesen Fällen `false` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> aufrufen.

Da Ihre Bibliotheksmethode Zeichenfolgen behandelt, möchten Sie auch sicherstellen, dass sie eine [leere Zeichenfolge (`String.Empty`)](xref:System.String.Empty), eine gültige Zeichenfolge, die keine Zeichen enthält und deren <xref:System.String.Length> 0 ist, und eine `null`-Zeichenfolge, die nicht initialisiert wurde, erfolgreich behandelt. Wenn `StartsWithUpper` als eine Erweiterungsmethode für eine <xref:System.String>-Instanz aufgerufen wird, kann ihr keine `null`-Zeichenfolge übergeben werden. Allerdings kann sie auch direkt als statische Methode aufgerufen und ihr ein einzelnes <xref:System.String>-Argument übergeben werden.

Sie definieren drei Methoden, von denen jede die zugehörige Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> wiederholt für jedes Element in einem Zeichenfolgenarray aufruft. Da die Testmethode nicht fortgesetzt wird, sobald sie auf den ersten Fehler trifft, rufen Sie eine Methodenüberladung auf, mit der Sie eine Zeichenfolge übergeben können, die den Zeichenfolgenwert angibt, der im Methodenaufruf verwendet wird.

So erstellen Sie die Testmethoden:

# <a name="ctabcsharp"></a>[C#](#tab/csharp) 
1. Ersetzen Sie den Code im Codefenster *UnitTest1.cs* durch den folgenden Code:

   [!CODE-csharp[Test#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]

   Beachten Sie, dass Ihr Großbuchstabentest in der `TestStartsWithUpper`-Methode den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+ 041C) umfasst, und der Kleinbuchstabentest in der `TestDoesNotStartWithUpper`-Methode den griechischen Kleinbuchstaben Alpha (U+03B1) und den kyrillischen Kleinbuchstaben Ghe (U+0433).

1. Wählen Sie in der Menüleiste **Datei** > **UnitTest1.cs speichern unter** aus. Wählen Sie im Dialogfeld **Datei speichern unter** den Pfeil neben der Schaltfläche **Speichern**, und wählen Sie dann **Mit Codierung speichern...** aus.

   ![Dialogfeld „Datei speichern unter“](./media/testing-library-with-visual-studio/savefileas.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic) 
1. Ersetzen Sie den Code im Codefenster *UnitTest1.vb* durch den folgenden Code:

    [!CODE-vb[Test#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   Beachten Sie, dass Ihr Großbuchstabentest in der `TestStartsWithUpper`-Methode den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+ 041C) umfasst, und der Kleinbuchstabentest in der `TestDoesNotStartWithUpper`-Methode den griechischen Kleinbuchstaben Alpha (U+03B1) und den kyrillischen Kleinbuchstaben Ghe (U+0433).

1. Wählen Sie in der Menüleiste **Datei** > **UnitTest1.vb speichern unter** aus. Wählen Sie im Dialogfeld **Datei speichern unter** den Pfeil neben der Schaltfläche **Speichern**, und wählen Sie dann **Mit Codierung speichern...** aus.

   ![Dialogfeld „Datei speichern unter“](./media/testing-library-with-visual-studio/savefileas.png)
---

1. Wählen Sie im Dialogfeld **Speichern unter bestätigen** die Schaltfläche **Ja**, um die Datei zu speichern.

1. Wählen Sie im Dialogfeld **Erweiterte Speicheroptionen** **Unicode (UTF-8 mit Signatur) – Codepage 65001** aus der Dropdownliste **Codierung** aus, und klicken Sie auf **OK**.

   ![Dialogfeld „Erweiterte Speicheroptionen“](./media/testing-library-with-visual-studio/advancedsaveoptions.png)

   Wenn Sie den Quellcode nicht in einer UTF8-codierten Datei speichern, kann Visual Studio ihn als ASCII-Datei speichern. Wenn dies geschieht, decodiert die Laufzeit die UTF8-Zeichen außerhalb des ASCII-Bereichs nicht ordnungsgemäß, und die Testergebnisse sind nicht präzise.

1. Wählen Sie auf der Menüleiste **Test** > **Ausführen** > **Alle Tests** aus. Das Fenster **Test-Explorer** wird geöffnet und zeigt, dass der Test erfolgreich ausgeführt wurde. Die drei Tests sind im Abschnitt **Bestandene Tests** aufgelistet, und im Abschnitt **Zusammenfassung** wird das Ergebnis des Testlaufs berichtet.

   ![Fenster „Test-Explorer“](./media/testing-library-with-visual-studio/firsttest.png)

## <a name="handling-test-failures"></a>Behandeln von Testfehlern

In Ihrem Testlauf sind keine Fehler aufgetreten, darum verändern Sie ihn leicht , sodass eine der Testmethoden nicht fortgesetzt wird:

1. Verändern Sie das `words`-Array in der `TestDoesNotStartWithUpper`-Methode, um die Zeichenfolge "Error" einzufügen. Sie müssen die Datei nicht speichern, das Visual Studio offene Dateien automatisch speichert, wenn eine Projektmappe zum Ausführen von Tests erstellt wurde.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```
   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```
1. Führen Sie den Test aus, indem Sie **Test** > **Ausführen** > **Alle Tests** aus der Menüleiste auswählen. Das Fenster **Test-Explorer** zeigt, dass zwei Tests erfolgreich ausgeführt wurden und einer nicht erfolgreich war.

   ![Fenster „Test-Explorer“](./media/testing-library-with-visual-studio/failedtest.png)

1. Wählen Sie den fehlerhaften Test, `TestDoesNotStartWith`, im Abschnitt **Fehlgeschlagene Tests** aus. Im Fenster **Test-Explorer** wird die Assert-Meldung angezeigt: „Fehler bei Assert.IsFalse. Für 'Error' erwartet False; tatsächlich: True“. Wegen des Fehlers wurden alle auf „Error“ folgenden Zeichenfolgen im Array nicht getestet.

   ![Fenster „Test-Explorer“, das den Assertionsfehler „Ist FALSE“ zeigt](./media/testing-library-with-visual-studio/failedtestdetail.png)

1. Entfernen Sie den Code, der hinzugefügt wurde (`"Error", `), und führen den Test erneut aus. Die Tests werden erfolgreich ausgeführt.

## <a name="testing-the-release-version-of-the-library"></a>Testen der endgültigen Produktversion der Bibliothek

Sie haben Ihre Tests für die Debugversion der Bibliothek ausgeführt. Da nun alle Ihre Tests erfolgreich waren, und Sie Ihre Bibliothek ausreichend getestet haben, sollten Sie die Tests ein weiteres Mal für die endgültige Produktversion der Bibliothek ausführen. Eine Reihe von Faktoren einschließlich der Compileroptimierungen kann manchmal zu einem unterschiedlichen Verhalten von Debug- und endgültiger Produktversion führen.

So testen Sie die endgültige Produktversion:

1. Ändern Sie in der Symbolleiste von Visual Studio die Buildkonfiguration von **Debuggen** zu **Freigabe**.

   ![Visual Studio-Symbolleiste](./media/testing-library-with-visual-studio/toolbar.png)

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **StringLibrary**-Projekt, und wählen Sie aus dem Kontextmenü **Erstellen** aus, um die Bibliothek erneut zu kompilieren.

   ![Kontextmenü „StringLibrary“](./media/testing-library-with-visual-studio/buildlibrary.png)

1. Führen Sie den Komponententest aus, indem Sie **Test** > **Ausführen** > **Alle Tests** aus der Menüleiste auswählen. Die Tests sind erfolgreich.

Das Testen Ihrer Bibliothek ist jetzt abgeschlossen, und im nächsten Schritt machen Sie sie für die Aufrufer verfügbar. Sie können sie mit einer oder mehreren Anwendungen bündeln oder sie als NuGet-Paket verteilen. Informationen hierzu finden Sie unter [Consuming a .NET Standard Class Library (Nutzen einer .NET-Standardklassenbibliothek)](./consuming-library-with-visual-studio.md).
