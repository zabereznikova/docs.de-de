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
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio"></a>Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio

In [Erstellen einer .NET Standard-Bibliothek in Visual Studio](library-with-visual-studio.md) haben Sie eine einfache Klassenbibliothek erstellt, die der <xref:System.String>-Klasse eine Erweiterungsmethode hinzufügt. Jetzt erstellen Sie einen Komponententest, um sicherzustellen, dass es wie erwartet funktioniert. Sie fügen Ihr Komponententestprojekt der Projektmappe hinzu, die Sie im vorherigen Artikel erstellt haben.

## <a name="create-a-unit-test-project"></a>Ein Komponententestprojekt erstellen

Um das Komponententestprojekt zu erstellen, führen Sie folgende Schritte aus:

1. Öffnen Sie die `ClassLibraryProjects`-Projektmappe, die Sie im Artikel [Erstellen einer .NET Standard-Bibliothek in Visual Studio](library-with-visual-studio.md) erstellt haben.

1. Fügen Sie der Projektmappe ein neues Komponententestprojekt mit dem Namen „StringLibraryTest“ hinzu.

   1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.

   1. Geben Sie auf der Seite **Neues Projekt hinzufügen** **mstest** in das Suchfeld ein. Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus. Klicken Sie auf die Vorlage **MsTest-Testprojekt (.NET Core)** und dann auf **Weiter**.

   1. Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **StringLibraryTest** ein. Wählen Sie dann **Erstellen** aus.

   > [!NOTE]
   > Neben einem MSTest-Testprojekt können Sie auch xUnit- und nUnit-Testprojekte für .NET Core in Visual Studio erstellen.

1. Visual Studio erstellt das Projekt und öffnet die Klassendatei mit dem folgenden Code im Codefenster:

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

   Der von der Vorlage für Komponententests erstellte Quellcode führt Folgendes aus:

   - Er importiert den Namespace <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, der für Komponententests verwendeten Typen enthält.

   - Er wendet das [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute)-Attribut auf die `UnitTest1`-Klasse an. Jede mit dem [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute)-Attribut markierte Testmethode in einer Testklasse wird automatisch ausgeführt, wenn der Komponententest ausgeführt wird.

   - Er wendet das Attribut [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) an, um `TestMethod1` in C# oder `TestSub` in Visual Basic als Testmethode für die automatische Ausführung beim Ausführen des Komponententests zu definieren.

1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für den Knoten **Abhängigkeiten** des **StringLibraryTest**-Projekts, und wählen Sie **Verweis hinzufügen** aus.

   > [!div class="mx-imgBorder"]
   > ![Kontextmenü der StringLibraryTest-Abhängigkeiten](./media/testing-library-with-visual-studio/add-reference-context-menu.png)

1. Erweitern Sie im Dialogfeld **Reference Manager** den Knoten **Projekte** und aktivieren Sie das Feld neben **StringLibrary**. Das Hinzufügen eines Verweises auf die `StringLibrary`-Assembly ermöglicht dem Compiler, **StringLibrary**-Methoden zu finden. Klicken Sie auf die Schaltfläche **OK**. Ein Verweis auf Ihr Klassenbibliotheksprojekt (`StringLibrary`) wird hinzugefügt.

   ![Dialogfeld „Verweis-Manager“ in Visual Studio](./media/testing-library-with-visual-studio/project-reference-manager.png)

## <a name="add-and-run-unit-test-methods"></a>Hinzufügen und Ausführen von Komponententestmethoden

Wenn Visual Studio einen Komponententest ausführt, wird jede Methode ausgeführt, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> in einer Komponententestklasse markiert ist: der Klasse, auf die das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> angewendet wird. Eine Testmethode endet, wenn der erste Fehler gefunden wird, oder wenn alle in der Methode enthaltenen Tests erfolgreich ausgeführt wurden.

In den am häufigsten verwendeten Tests werden Member der Klasse <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> aufgerufen. Viele Assert-Methoden enthalten mindestens zwei Parameter, von denen einer das erwartete und der andere das tatsächliche Testergebnis ist. Die am häufigsten aufgerufenen Methoden der `Assert`-Klasse werden in der nachfolgenden Tabelle aufgeführt:

| Assert-Methoden     | Funktion |
| ------------------ | -------- |
| `Assert.AreEqual`  | Überprüft, ob zwei Werte oder Objekte gleich sind. Der Assert ist nicht erfolgreich, wenn die Werte oder Objekte nicht gleich sind. |
| `Assert.AreSame`   | Überprüft, ob zwei Objektvariablen auf das gleiche Objekt verweisen. Die Bestätigung ist nicht erfolgreich, wenn die Variablen auf verschiedene Objekte verweisen. |
| `Assert.IsFalse`   | Überprüft, ob eine Bedingung `false` ist. Die Bestätigung ist nicht erfolgreich, wenn die Bedingung `true` ist. |
| `Assert.IsNotNull` | Überprüft, ob ein Objekt nicht `null` ist. Die Bestätigung ist nicht erfolgreich, wenn das Objekt `null` ist. |

Sie können auch die <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A>-Methode in einer Testmethode verwenden, um den Typ der Ausnahme anzugeben, die ausgelöst werden soll. Der Test ist nicht erfolgreich, wenn die angegebene Ausnahme nicht ausgelöst wird.

Beim Testen der `StringLibrary.StartsWithUpper`-Methode möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die mit einem Großbuchstaben beginnen. Sie erwarten, dass die Methode in diesen Fällen `true` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> aufrufen. Außerdem möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die nicht mit einem Großbuchstaben beginnen. Sie erwarten, dass die Methode in diesen Fällen `false` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> aufrufen.

Da Ihre Bibliotheksmethode Zeichenfolgen verarbeitet, möchten Sie auch sicherstellen, dass sie eine [leere Zeichenfolge (`String.Empty`)](xref:System.String.Empty), eine gültige Zeichenfolge, die keine Zeichen enthält und deren <xref:System.String.Length> 0 ist, und eine `null`-Zeichenfolge, die nicht initialisiert wurde, erfolgreich verarbeitet. Wenn `StartsWithUpper` als eine Erweiterungsmethode für eine <xref:System.String>-Instanz aufgerufen wird, kann ihr keine `null`-Zeichenfolge übergeben werden. Allerdings kann sie auch direkt als statische Methode aufgerufen und ihr ein einzelnes <xref:System.String>-Argument übergeben werden.

Sie definieren drei Methoden, von denen jede eine zugehörige Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> wiederholt für jedes Element in einem Zeichenfolgenarray aufruft. Da die Testmethode nicht fortgesetzt wird, sobald sie den ersten Fehler findet, rufen Sie eine Methodenüberladung auf, mit der Sie eine Zeichenfolge übergeben können, die den Zeichenfolgenwert angibt, der im Methodenaufruf verwendet wird.

So erstellen Sie die Testmethoden:

1. Ersetzen Sie den Code im Codefenster *UnitTest1.cs* oder *UnitTest1.vb* durch den folgenden Code:

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]
   [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   Der Test für Großbuchstaben in der `TestStartsWithUpper`-Methode enthält den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+041C). Der Test für Kleinbuchstaben in der `TestDoesNotStartWithUpper`-Methode enthält den griechischen Kleinbuchstaben alpha (U+03B1) und den kyrillischen Kleinbuchstaben ghe (U+0433).

1. Wählen Sie in der Menüleiste **Datei** > **UnitTest1.cs speichern unter** oder **Datei** > **UnitTest1.vb speichern unter** aus. Wählen Sie im Dialogfeld **Datei speichern unter** den Pfeil neben der Schaltfläche **Speichern**, und wählen Sie dann **Mit Codierung speichern...** aus.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio-Dialogfeld „Datei speichern unter“](./media/testing-library-with-visual-studio/save-file-as-dialog.png)

1. Wählen Sie im Dialogfeld **Speichern unter bestätigen** die Schaltfläche **Ja**, um die Datei zu speichern.

1. Wählen Sie im Dialogfeld **Erweiterte Speicheroptionen** **Unicode (UTF-8 mit Signatur) – Codepage 65001** aus der Dropdownliste **Codierung** aus, und klicken Sie auf **OK**.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio-Dialogfeld „Erweiterte Speicheroptionen“](./media/testing-library-with-visual-studio/advanced-save-options.png)

   Wenn Sie den Quellcode nicht in einer UTF8-codierten Datei speichern, kann Visual Studio ihn als ASCII-Datei speichern. Wenn dies geschieht, decodiert die Laufzeit die UTF8-Zeichen außerhalb des ASCII-Bereichs nicht ordnungsgemäß, und die Testergebnisse sind nicht richtig.

1. Wählen Sie auf der Menüleiste **Test** > **Ausführen** > **Alle Tests** aus. Das Fenster **Test-Explorer** wird geöffnet und zeigt, dass der Test erfolgreich ausgeführt wurde. Die drei Tests sind im Abschnitt **Bestandene Tests** aufgelistet, und im Abschnitt **Zusammenfassung** wird das Ergebnis des Testlaufs berichtet.

   > [!div class="mx-imgBorder"]
   > ![Test Explorer-Fenster mit erfolgreichen Tests](./media/testing-library-with-visual-studio/test-explorer-window.png)

## <a name="handle-test-failures"></a>Behandeln von Testfehlern

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

   > [!div class="mx-imgBorder"]
   > ![Test Explorer-Fenster mit fehlschlagenden Tests](./media/testing-library-with-visual-studio/failed-test-window.png)

1. Wählen Sie den fehlgeschlagenen Test (`TestDoesNotStartWith`) aus. Im Fenster **Test-Explorer** wird die Assert-Meldung angezeigt: „Fehler bei Assert.IsFalse. Für 'Error' erwartet: False; tatsächlich: True“. Wegen des Fehlers wurden alle auf „Error“ folgenden Zeichenfolgen im Array nicht getestet.

   > [!div class="mx-imgBorder"]
   > ![Fenster „Test-Explorer“, das den Assertionsfehler isFalse zeigt](./media/testing-library-with-visual-studio/failed-test-detail.png)

1. Machen Sie die Änderung rückgängig, die Sie in Schritt 1 vorgenommen haben, und entfernen Sie die Zeichenfolge „Error“ (Fehler). Führen Sie die Tests erneut aus, und sie werden erfolgreich ausgeführt.

## <a name="test-the-release-version-of-the-library"></a>Testen der Releaseversion der Bibliothek

Sie haben Ihre Tests für die Debugversion der Bibliothek ausgeführt. Da nun alle Ihre Tests erfolgreich waren, und Sie Ihre Bibliothek ausreichend getestet haben, sollten Sie die Tests ein weiteres Mal für die endgültige Produktversion der Bibliothek ausführen. Eine Reihe von Faktoren einschließlich der Compileroptimierungen kann manchmal zu einem unterschiedlichen Verhalten von Debug- und endgültiger Produktversion führen.

So testen Sie die endgültige Produktversion:

1. Ändern Sie in der Symbolleiste von Visual Studio die Buildkonfiguration von **Debuggen** zu **Freigabe**.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio-Symbolleiste mit hervorgehobenem Releasebuild](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **StringLibrary**-Projekt, und wählen Sie aus dem Kontextmenü **Erstellen** aus, um die Bibliothek erneut zu kompilieren.

   > [!div class="mx-imgBorder"]
   > ![StringLibrary-Kontextmenü mit Befehl „Erstellen“](./media/testing-library-with-visual-studio/build-library-context-menu.png)

1. Führen Sie den Komponententest aus, indem Sie **Test** > **Ausführen** > **Alle Tests** aus der Menüleiste auswählen. Die Tests sind erfolgreich.

Das Testen Ihrer Bibliothek ist jetzt abgeschlossen, und im nächsten Schritt machen Sie sie für die Aufrufer verfügbar. Sie können sie mit einer oder mehreren Anwendungen bündeln oder sie als NuGet-Paket verteilen. Informationen hierzu finden Sie unter [Consuming a .NET Standard Class Library (Nutzen einer .NET-Standardklassenbibliothek)](consuming-library-with-visual-studio.md).

## <a name="see-also"></a>Siehe auch

- [Grundlagen zu Komponententests: Visual Studio](/visualstudio/test/unit-test-basics)
