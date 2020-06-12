---
title: Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio
description: Erstellen Sie ein Komponententestprojekt für Ihre .NET Core-Klassenbibliothek. Stellen Sie sicher, dass Ihre .NET Core-Klassenbibliothek mit Komponententests funktioniert.
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 48ada77b8422030fd93aa29df1df50a3ae5104fe
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283506"
---
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio"></a>Tutorial: Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio

In diesem Tutorial wird gezeigt, wie Sie Komponententests automatisieren, indem Sie einer Projektmappe ein Testprojekt hinzufügen.

## <a name="prerequisites"></a>Voraussetzungen

- In diesem Tutorial wird die Projektmappe verwendet, die Sie in [Erstellen einer .NET Standard-Bibliothek in Visual Studio](library-with-visual-studio.md) erstellen.

## <a name="create-a-unit-test-project"></a>Ein Komponententestprojekt erstellen

1. Öffnen Sie die `ClassLibraryProjects`-Projektmappe, die Sie in [Erstellen einer .NET Standard-Bibliothek in Visual Studio](library-with-visual-studio.md) erstellt haben.

1. Fügen Sie der Projektmappe ein neues Komponententestprojekt mit dem Namen „StringLibraryTest“ hinzu.

   1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.

   1. Geben Sie auf der Seite **Neues Projekt hinzufügen** **mstest** in das Suchfeld ein. Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus.

   1. Klicken Sie auf die Vorlage **MSTest-Testprojekt (.NET Core)** und dann auf **Weiter**.

   1. Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **StringLibraryTest** ein. Wählen Sie dann **Erstellen** aus.

   > [!NOTE]
   > MSTest ist eines von drei Testframeworks, unter denen Sie wählen können. Die beiden anderen sind xUnit und nUnit.

1. Visual Studio erstellt das Projekt und öffnet die Klassendatei mit dem folgenden Code im Codefenster. Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.

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
   - Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> auf die Klasse `UnitTest1` an.
   - Er wendet das <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>-Attribut an, um `TestMethod1` in C# oder `TestSub` in Visual Basic zu definieren.

   Jede mit [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) gekennzeichnete Methode in einer mit [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) gekennzeichneten Testklasse wird automatisch ausgeführt, wenn der Komponententest ausgeführt wird.

1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für den Knoten **Abhängigkeiten** des **StringLibraryTest**-Projekts, und wählen Sie **Projektverweis hinzufügen** aus.

1. Erweitern Sie im Dialogfeld **Verweis-Manager** den Knoten **Projekte**, und aktivieren Sie das Kontrollkästchen neben **StringLibrary**. Das Hinzufügen eines Verweises auf die `StringLibrary`-Assembly ermöglicht dem Compiler, **StringLibrary**-Methoden zu finden, wenn das **StringLibraryTest**-Projekt kompiliert wird.

1. Klicken Sie auf **OK**.

## <a name="add-and-run-unit-test-methods"></a>Hinzufügen und Ausführen von Komponententestmethoden

Wenn Visual Studio einen Komponententest ausführt, erfolgt die Ausführung jeder Methode, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> gekennzeichnet ist, in einer Klasse, die mit dem Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> gekennzeichnet ist. Eine Testmethode endet, wenn der erste Fehler gefunden wird, oder wenn alle in der Methode enthaltenen Tests erfolgreich ausgeführt wurden.

In den am häufigsten verwendeten Tests werden Member der Klasse <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> aufgerufen. Viele Assert-Methoden enthalten mindestens zwei Parameter, von denen einer das erwartete und der andere das tatsächliche Testergebnis ist. Die am häufigsten aufgerufenen Methoden der `Assert`-Klasse werden in der nachfolgenden Tabelle aufgeführt:

| Assert-Methoden     | Funktion |
| ------------------ | -------- |
| `Assert.AreEqual`  | Überprüft, ob zwei Werte oder Objekte gleich sind. Der Assert ist nicht erfolgreich, wenn die Werte oder Objekte nicht gleich sind. |
| `Assert.AreSame`   | Überprüft, ob zwei Objektvariablen auf das gleiche Objekt verweisen. Die Bestätigung ist nicht erfolgreich, wenn die Variablen auf verschiedene Objekte verweisen. |
| `Assert.IsFalse`   | Überprüft, ob eine Bedingung `false` ist. Die Bestätigung ist nicht erfolgreich, wenn die Bedingung `true` ist. |
| `Assert.IsNotNull` | Überprüft, ob ein Objekt nicht `null` ist. Die Bestätigung ist nicht erfolgreich, wenn das Objekt `null` ist. |

Sie können auch die <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType>-Methode in einer Testmethode verwenden, um den Typ der Ausnahme anzugeben, die ausgelöst werden soll. Der Test ist nicht erfolgreich, wenn die angegebene Ausnahme nicht ausgelöst wird.

Beim Testen der `StringLibrary.StartsWithUpper`-Methode möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die mit einem Großbuchstaben beginnen. Sie erwarten, dass die Methode in diesen Fällen `true` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> aufrufen. Außerdem möchten Sie eine Reihe von Zeichenfolgen bereitstellen, die nicht mit einem Großbuchstaben beginnen. Sie erwarten, dass die Methode in diesen Fällen `false` zurückgibt, also können Sie die Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> aufrufen.

Da Ihre Bibliotheksmethode Zeichenfolgen verarbeitet, möchten Sie auch sicherstellen, dass sie eine [leere Zeichenfolge (`String.Empty`)](xref:System.String.Empty), eine gültige Zeichenfolge, die keine Zeichen enthält und deren <xref:System.String.Length> 0 ist, und eine `null`-Zeichenfolge, die nicht initialisiert wurde, erfolgreich verarbeitet. Wenn `StartsWithUpper` als eine Erweiterungsmethode für eine <xref:System.String>-Instanz aufgerufen wird, kann ihr keine `null`-Zeichenfolge übergeben werden. Allerdings kann sie auch direkt als statische Methode aufgerufen und ihr ein einzelnes <xref:System.String>-Argument übergeben werden.

Sie definieren drei Methoden, von denen jede eine zugehörige Methode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> wiederholt für jedes Element in einem Zeichenfolgenarray aufruft. Da die Testmethode nicht fortgesetzt wird, sobald sie den ersten Fehler findet, rufen Sie eine Methodenüberladung auf, mit der Sie eine Zeichenfolge übergeben können, die den Zeichenfolgenwert angibt, der im Methodenaufruf verwendet wird.

So erstellen Sie die Testmethoden:

1. Ersetzen Sie den Code im Codefenster *UnitTest1.cs* oder *UnitTest1.vb* durch den folgenden Code:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   Der Test für Großbuchstaben in der `TestStartsWithUpper`-Methode enthält den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+041C). Der Test für Kleinbuchstaben in der `TestDoesNotStartWithUpper`-Methode enthält den griechischen Kleinbuchstaben alpha (U+03B1) und den kyrillischen Kleinbuchstaben ghe (U+0433).

1. Wählen Sie in der Menüleiste **Datei** > **UnitTest1.cs speichern unter** oder **Datei** > **UnitTest1.vb speichern unter** aus. Wählen Sie im Dialogfeld **Datei speichern unter** den Pfeil neben der Schaltfläche **Speichern**, und wählen Sie dann **Mit Codierung speichern...** aus.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio-Dialogfeld „Datei speichern unter“](./media/testing-library-with-visual-studio/save-file-as-dialog.png)

1. Wählen Sie im Dialogfeld **Speichern unter bestätigen** die Schaltfläche **Ja**, um die Datei zu speichern.

1. Wählen Sie im Dialogfeld **Erweiterte Speicheroptionen** **Unicode (UTF-8 mit Signatur) – Codepage 65001** aus der Dropdownliste **Codierung** aus, und klicken Sie auf **OK**.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio-Dialogfeld „Erweiterte Speicheroptionen“](./media/testing-library-with-visual-studio/advanced-save-options.png)

   Wenn Sie den Quellcode nicht in einer UTF8-codierten Datei speichern, kann Visual Studio ihn als ASCII-Datei speichern. Wenn dies geschieht, decodiert die Laufzeit die UTF8-Zeichen außerhalb des ASCII-Bereichs nicht ordnungsgemäß, und die Testergebnisse sind nicht richtig.

1. Wählen Sie auf der Menüleiste **Testen** > **Alle Tests ausführen** aus. Wenn das Fenster **Test-Explorer** nicht geöffnet ist, öffnen Sie es, indem Sie **Testen** > **Test-Explorer** auswählen. Die drei Tests sind im Abschnitt **Bestandene Tests** aufgelistet, und im Abschnitt **Zusammenfassung** wird das Ergebnis des Testlaufs berichtet.

   > [!div class="mx-imgBorder"]
   > ![Test Explorer-Fenster mit erfolgreichen Tests](./media/testing-library-with-visual-studio/test-explorer-window.png)

## <a name="handle-test-failures"></a>Behandeln von Testfehlern

Bei der testgesteuerten Entwicklung (Test-Driven Development, TDD) schreiben Sie zunächst Tests, bei deren ersten Ausführung Fehler auftreten. Anschließend fügen Sie der App Code hinzu, mit dem der Test erfolgreich ausgeführt wird. In diesem Fall haben Sie den Test, der den Code überprüft, nach Schreiben des App-Codes erstellt, sodass beim Test kein Fehler aufgetreten ist. Fügen Sie einen ungültigen Wert zur Testeingabe hinzu, um zu überprüfen, ob beim Test auch wirklich erwartungsgemäß ein Fehler auftritt.

1. Verändern Sie das `words`-Array in der `TestDoesNotStartWithUpper`-Methode, um die Zeichenfolge "Error" einzufügen. Sie müssen die Datei nicht speichern, das Visual Studio offene Dateien automatisch speichert, wenn eine Projektmappe zum Ausführen von Tests erstellt wurde.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. Führen Sie den Test aus, indem Sie auf der Menüleiste **Testen** > **Alle Tests ausführen** auswählen. Das Fenster **Test-Explorer** zeigt, dass zwei Tests erfolgreich ausgeführt wurden und einer nicht erfolgreich war.

   > [!div class="mx-imgBorder"]
   > ![Test Explorer-Fenster mit fehlschlagenden Tests](./media/testing-library-with-visual-studio/failed-test-window.png)

1. Wählen Sie den fehlgeschlagenen Test (`TestDoesNotStartWith`) aus. Im Fenster **Test-Explorer** wird die Assert-Meldung angezeigt: „Fehler bei Assert.IsFalse. Für 'Error' erwartet: False; tatsächlich: True“. Wegen des Fehlers wurden alle auf „Error“ folgenden Zeichenfolgen im Array nicht getestet.

   > [!div class="mx-imgBorder"]
   > ![Fenster „Test-Explorer“, das den Assertionsfehler isFalse zeigt](./media/testing-library-with-visual-studio/failed-test-detail.png)

1. Machen Sie die Änderung rückgängig, die Sie in Schritt 1 vorgenommen haben, und entfernen Sie die Zeichenfolge „Error“ (Fehler). Führen Sie den Test erneut aus. Nun ist er erfolgreich.

## <a name="test-the-release-version-of-the-library"></a>Testen der Releaseversion der Bibliothek

Nachdem die Tests beim Ausführen der Debugversion der Bibliothek nun alle erfolgreich waren, führen Sie die Tests auch für den Releasebuild der Bibliothek aus. Eine Reihe von Faktoren einschließlich der Compileroptimierungen kann manchmal zu einem unterschiedlichen Verhalten von Debug- und endgültiger Produktversion führen.

So testen Sie die endgültige Produktversion:

1. Ändern Sie in der Symbolleiste von Visual Studio die Buildkonfiguration von **Debuggen** zu **Freigabe**.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio-Symbolleiste mit hervorgehobenem Releasebuild](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **StringLibrary**-Projekt, und wählen Sie aus dem Kontextmenü **Erstellen** aus, um die Bibliothek erneut zu kompilieren.

   > [!div class="mx-imgBorder"]
   > ![StringLibrary-Kontextmenü mit Befehl „Erstellen“](./media/testing-library-with-visual-studio/build-library-context-menu.png)

1. Führen Sie den Komponententest aus, indem Sie auf der Menüleiste **Testen** > **Alle Tests** auswählen. Die Tests sind erfolgreich.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [Grundlagen zu Komponententests: Visual Studio](/visualstudio/test/unit-test-basics)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Komponententests für eine Klassenbibliothek ausgeführt. Sie können die Bibliothek anderen Benutzern zur Verfügung stellen, indem Sie sie als Paket auf [NuGet](https://nuget.org) veröffentlichen. Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:

> [!div class="nextstepaction"]
> [Erstellen und Veröffentlichen eines NuGet-Pakets mithilfe von Visual Studio](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

Wenn Sie eine Bibliothek als NuGet-Paket veröffentlichen, können andere Benutzer diese installieren und verwenden. Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:

> [!div class="nextstepaction"]
> [Installieren und Verwenden eines Pakets in Visual Studio](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

Eine Bibliothek muss nicht als Paket verteilt werden. Sie kann mit einer Konsolen-App gebündelt werden, die sie verwendet. Informationen zum Veröffentlichen einer Konsolen-App finden Sie in einem früheren Tutorial dieser Reihe:

> [!div class="nextstepaction"]
> [Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio](publishing-with-visual-studio.md)
