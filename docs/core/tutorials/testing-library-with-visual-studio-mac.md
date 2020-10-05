---
title: Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio für Mac
description: Erstellen Sie ein Komponententestprojekt für eine .NET Core-Klassenbibliothek. Sie überprüfen mithilfe von Komponententests, ob die .NET Core-Klassenbibliothek ordnungsgemäß funktioniert.
ms.date: 06/08/2020
ms.openlocfilehash: 3adcddc96abf77012f89a28c1cf60ea57ae506a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180529"
---
# <a name="test-a-net-standard-class-library-with-net-core-using-visual-studio"></a>Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio

In diesem Tutorial wird gezeigt, wie Sie Komponententests automatisieren, indem Sie einer Projektmappe ein Testprojekt hinzufügen.

## <a name="prerequisites"></a>Voraussetzungen

- In diesem Tutorial wird die Projektmappe verwendet, die Sie in [Erstellen einer .NET Standard-Bibliothek mithilfe von Visual Studio für Mac](library-with-visual-studio-mac.md) erstellen.

## <a name="create-a-unit-test-project"></a>Ein Komponententestprojekt erstellen

Komponententests bieten automatisierte Softwaretests während der Entwicklung und Veröffentlichung. [MSTest](https://github.com/Microsoft/testfx-docs) ist eines von drei Testframeworks, aus denen Sie wählen können. Die beiden anderen sind [xUnit](https://xunit.net/) und [nUnit](https://nunit.org/).

1. Starten Sie Visual Studio für Mac.

1. Öffnen Sie die `ClassLibraryProjects`-Projektmappe, die Sie in [Erstellen einer .NET Standard-Bibliothek mithilfe von Visual Studio für Mac](library-with-visual-studio-mac.md) erstellt haben.

1. Klicken Sie im Pad **Projektmappe** bei gedrückter <kbd>CTRL-TASTE</kbd> auf die Projektmappe `ClassLibraryProjects`, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.

1. Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **Web und Konsole** die Option **Tests** aus. Wählen Sie das Projekt**MSTest-Projekt** und dann **Weiter** aus.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-project.png" alt-text="Visual Studio für Mac, Dialogfeld „Neues Projekt“, Erstellen des Testprojekts":::

1. Wählen Sie die **.NET Core 3.1** aus. Nennen Sie das neue Projekt „StringLibraryTest“, und wählen Sie **Erstellen** aus.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-new-project-name.png" alt-text="Visual Studio für Mac, Dialogfeld „Neues Projekt“, Erstellen des Testprojekts":::

   Visual Studio erstellt eine Klassendatei mit folgendem Code:

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

   Der von der Vorlage für Komponententests erstellte Quellcode führt Folgendes aus:

   - Er importiert den Namespace <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, der für Komponententests verwendeten Typen enthält.
   - Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> auf die Klasse `UnitTest1` an.
   - Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> auf `TestMethod1` an.

   Jede mit [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) gekennzeichnete Methode in einer mit [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) gekennzeichneten Testklasse wird automatisch ausgeführt, wenn der Komponententest ausgeführt wird.

## <a name="add-a-project-reference"></a>Hinzufügen eines Projektverweises

Damit das Testprojekt mit der `StringLibrary`-Klasse funktioniert, fügen Sie einen Verweis auf das Projekt `StringLibrary` hinzu.

1. Klicken Sie im Pad **Projektmappe** bei gedrückter <kbd>CTRL-TASTE</kbd> unter **StringLibraryTest** auf **Abhängigkeiten**. Wählen Sie im Kontextmenü **Verweis hinzufügen** aus.

1. Wählen Sie im Dialogfeld **Verweise** das Projekt **StringLibrary** aus. Klicken Sie auf **OK**.

      :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-edit-references.png" alt-text="Visual Studio für Mac, Dialogfeld „Neues Projekt“, Erstellen des Testprojekts":::

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

Da Ihre Bibliotheksmethode Zeichenfolgen verarbeitet, möchten Sie auch sicherstellen, dass sie eine [leere Zeichenfolge (`String.Empty`)](xref:System.String.Empty), eine gültige Zeichenfolge, die keine Zeichen enthält und deren <xref:System.String.Length> 0 ist, und eine `null`-Zeichenfolge, die nicht initialisiert wurde, erfolgreich verarbeitet. Sie können `StartsWithUpper` als statische Methode direkt aufrufen und ein einzelnes <xref:System.String>-Argument übergeben. Alternativ können Sie `StartsWithUpper` als Erweiterungsmethode für eine `string`-Variable aufrufen, die `null` zugewiesen ist.

Sie definieren drei Methoden, von denen jede eine zugehörige <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>-Methode für jedes Element in einem Zeichenfolgenarray aufruft. Sie rufen eine Methodenüberladung auf, mit der Sie eine Fehlermeldung angeben können, die bei einem Testfehler angezeigt werden soll. Die Meldung enthält die Zeichenfolge, die den Fehler verursacht hat.

So erstellen Sie die Testmethoden:

1. Öffnen Sie die Datei *UnitTest1.cs*, und ersetzen Sie den Code durch den folgenden Code:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   Der Test für Großbuchstaben in der `TestStartsWithUpper`-Methode enthält den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+041C). Der Test für Kleinbuchstaben in der `TestDoesNotStartWithUpper`-Methode enthält den griechischen Kleinbuchstaben alpha (U+03B1) und den kyrillischen Kleinbuchstaben ghe (U+0433).

1. Wählen Sie auf der Menüleiste **Datei** > **Speichern unter** aus. Stellen Sie im Dialogfeld sicher, dass **Codierung** auf **Unicode (UTF-8)** festgelegt ist.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/save-file-as-dialog.png" alt-text="Visual Studio für Mac, Dialogfeld „Neues Projekt“, Erstellen des Testprojekts":::

1. Wenn Sie gefragt werden, ob Sie die vorhandene Datei ersetzen möchten, wählen Sie **Ersetzen** aus.

   Wenn Sie den Quellcode nicht in einer UTF8-codierten Datei speichern, kann Visual Studio ihn als ASCII-Datei speichern. Wenn dies geschieht, decodiert die Laufzeit die UTF8-Zeichen außerhalb des ASCII-Bereichs nicht ordnungsgemäß, und die Testergebnisse sind nicht richtig.

1. Öffnen Sie das Panel **Komponententests** auf der rechten Seite des Bildschirms. Wählen Sie **Ansicht** > **Tests** aus dem Menü aus.

1. Klicken Sie auf das **Andocksymbol**, um das Panel geöffnet zu lassen.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-dock-icon.png" alt-text="Visual Studio für Mac, Dialogfeld „Neues Projekt“, Erstellen des Testprojekts":::

1. Klicken Sie auf die Schaltfläche **Alle ausführen**.

   Alle Tests erfolgreich.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-pass.png" alt-text="Visual Studio für Mac, Dialogfeld „Neues Projekt“, Erstellen des Testprojekts":::

## <a name="handle-test-failures"></a>Behandeln von Testfehlern

Bei der testgesteuerten Entwicklung (Test-Driven Development, TDD) schreiben Sie zunächst Tests, bei deren ersten Ausführung Fehler auftreten. Anschließend fügen Sie der App Code hinzu, mit dem der Test erfolgreich ausgeführt wird. Für dieses Tutorial haben Sie den Test, der den Code überprüft, nach Schreiben des App-Codes erstellt, sodass beim Test kein Fehler aufgetreten ist. Fügen Sie einen ungültigen Wert zur Testeingabe hinzu, um zu überprüfen, ob beim Test auch wirklich erwartungsgemäß ein Fehler auftritt.

1. Verändern Sie das `words`-Array in der `TestDoesNotStartWithUpper`-Methode, um die Zeichenfolge "Error" einzufügen. Sie müssen die Datei nicht speichern, das Visual Studio offene Dateien automatisch speichert, wenn eine Projektmappe zum Ausführen von Tests erstellt wurde.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. Führen Sie die Tests erneut aus.

   Das Fenster **Test-Explorer** zeigt nun an, dass zwei Tests erfolgreich waren und einer nicht.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/failed-test-window.png" alt-text="Visual Studio für Mac, Dialogfeld „Neues Projekt“, Erstellen des Testprojekts":::

1. Klicken Sie bei gedrückter <kbd>CTRL-TASTE</kbd> auf den fehlgeschlagenen Test, `TestDoesNotStartWithUpper`. Wählen Sie im Kontextmenü **Ergebnisbereich anzeigen** aus.

   Im Pad **Ergebnisse** wird die Meldung angezeigt, die von Assert generiert wurde: „Fehler bei Assert.IsFalse. Für 'Error' erwartet: False; tatsächlich: True“. Wegen des Fehlers wurden keine auf „Error“ folgenden Zeichenfolgen im Array getestet.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-failure.png" alt-text="Visual Studio für Mac, Dialogfeld „Neues Projekt“, Erstellen des Testprojekts":::

1. Entfernen Sie die Zeichenfolge „Error“, die Sie in Schritt 1 hinzugefügt haben. Führen Sie den Test erneut aus. Nun ist er erfolgreich.

## <a name="test-the-release-version-of-the-library"></a>Testen der Releaseversion der Bibliothek

Nachdem die Tests beim Ausführen des Debugbuilds der Bibliothek nun alle erfolgreich waren, führen Sie die Tests auch für den Releasebuild der Bibliothek aus. Eine Reihe von Faktoren einschließlich der Compileroptimierungen kann manchmal zu einem unterschiedlichen Verhalten von Debug- und endgültiger Produktversion führen.

So testen Sie die endgültige Produktversion:

1. Ändern Sie in der Symbolleiste von Visual Studio die Buildkonfiguration von **Debuggen** zu **Freigabe**.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Visual Studio für Mac, Dialogfeld „Neues Projekt“, Erstellen des Testprojekts":::

1. Klicken Sie im Pad **Projektmappe** bei gedrückter <kbd>CTRL-TASTE</kbd> auf das Projekt **StringLibrary**, und wählen Sie im Kontextmenü **Build** aus, um die Bibliothek erneut zu kompilieren.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/build-library-context-menu.png" alt-text="Visual Studio für Mac, Dialogfeld „Neues Projekt“, Erstellen des Testprojekts":::

1. Führen Sie die Komponententests erneut aus.

   Die Tests sind erfolgreich.

## <a name="debug-tests"></a>Debuggen von Tests

Wenn Sie Visual Studio für Mac als IDE verwenden, können Sie den gleichen Prozess wie im [Tutorial: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio für Mac](debugging-with-visual-studio-mac.md) beschrieben zum Debuggen von Code mithilfe Ihres Komponententestprojekts verwenden. Anstatt das App-Projekt *ShowCase* zu starten, klicken Sie bei gedrückter <kbd>STRG-TASTE</kbd> auf das **Projekt StringLibraryTests**. Wählen Sie dann im Kontextmenü die Option **Debuggen des Projekts starten** aus.

Visual Studio startet das Testprojekt mit angefügtem Debugger. Die Ausführung wird an jedem Haltepunkt angehalten, den Sie dem Testprojekt oder zugrunde liegenden Bibliothekscode hinzugefügt haben.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Komponententests in .NET Core und .NET Standard](../testing/index.md)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Komponententests für eine Klassenbibliothek ausgeführt. Sie können die Bibliothek anderen Benutzern zur Verfügung stellen, indem Sie sie als Paket auf [NuGet](https://nuget.org) veröffentlichen. Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:

> [!div class="nextstepaction"]
> [Erstellen und Veröffentlichen eines Pakets (dotnet CLI)](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

Wenn Sie eine Bibliothek als NuGet-Paket veröffentlichen, können andere Benutzer diese installieren und verwenden. Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:

> [!div class="nextstepaction"]
> [Installieren und Verwenden eines Pakets in Visual Studio für Mac](/nuget/quickstart/install-and-use-a-package-in-visual-studio-mac)

Eine Bibliothek muss nicht als Paket verteilt werden. Sie kann mit einer Konsolen-App gebündelt werden, die sie verwendet. Informationen zum Veröffentlichen einer Konsolen-App finden Sie in einem früheren Tutorial dieser Reihe:

> [!div class="nextstepaction"]
> [Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio für Mac](publishing-with-visual-studio-mac.md)
