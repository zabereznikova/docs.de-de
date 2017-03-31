---
title: Testen einer Klassenbibliothek mit .NET Core in Visual Studio 2017
description: Erfahren Sie, wie Sie eine in C# geschriebene Klassenbibliothek mithilfe von Visual Studio 2017 testen.
keywords: .NET Core, .NET Standard-Klassenbibliothek, Visual Studio 2017, Komponententest
author: stevehoag
ms.author: shoag
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 069ad711-3eaa-45c6-94d7-b40249cc8b99
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ee21799706b971f0ec13285b0771b32b4367f570
ms.lasthandoff: 03/13/2017

---

# <a name="testing-a-class-library-with-net-core-in-visual-studio-2017"></a>Testen einer Klassenbibliothek mit .NET Core in Visual Studio 2017 #

In [Erstellen einer Klassenbibliothek mit C# und .NET Core in Visual Studio 2017](library-with-visual-studio-2017.md) haben wir eine einfache Klassenbibliothek erstellt, die der @System.String-Klasse eine Erweiterungsmethode hinzufügt. Jetzt erstellen wir einen Komponententest, um sicherzustellen, dass es wie erwartet funktioniert. Wir fügen unser Komponententestprojekt der Projektmappe hinzu, die wir im vorherigen Thema erstellt haben.

## <a name="creating-a-unit-test-project"></a>Erstellen eines Komponententestprojekts ##

Um das Komponententestprojekt zu erstellen, führen Sie folgende Schritte aus:

1. Öffnen Sie im Projektmappen-Explorer das Kontextmenü des Projektmappenknotens **ClassLibraryProject**, und wählen Sie **Hinzufügen**, **Neues Projekt** aus.

   <!-- Need a VS 2017 version  [!NOTE] In addition to a Unit Test project, you can also use Visual Studio to create an XUnit test project for .NET Core. For a walkthrough that includes an XUnit test project, see [Getting started with .NET Core on Windows, using Visual Studio 2015](../../core/tutorials/using-on-windows.md). --> 

1. Erweitern Sie im Dialogfeld **Neues Projekt hinzufügen** den **Visual C#**-Knoten und den **.NET Core**-Knoten, wählen Sie dann die **Komponententestprojekt (.NET Core)**-Projektvorlage aus, und nennen Sie sie `StringLibraryTest`, wie die folgende Abbildung zeigt.

   ![Bild](./media/testproject.jpg)

1. Wählen Sie die Schaltfläche **OK** aus, um das Projekt zu erstellen. Visual Studio erstellt das Projekt und öffnet die `UnitTest1.cs`-Datei im Codefenster, wie in der folgenden Abbildung dargestellt.

   ![Bild](./media/unit_test_code_window.jpg)

   Der von der Vorlage für Komponententests erstellte Quellcode führt Folgendes aus:

   - Er importiert den Namespace [Microsoft.VisualStudio.TestTools.UnitTesting](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.aspx), der die für die Komponententests verwendeten Typen enthält.

   - Er wendet das [\[TestClass\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx)-Attribut auf die `UnitTest1`-Klasse an. Jede mit dem \[TestMethod\]-Attribut markierte Testmethode in einer Testklasse wird automatisch ausgeführt, wenn der Komponententest ausgeführt wird.

   - Er wendet das [\[TestMethod\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx)-Attribut an, um `TestMethod1` als Testmethode zu definieren, die automatisch ausgeführt wird, wenn der Komponententest ausgeführt wird.

1. Öffnen Sie im Projektmappen-Explorer das Kontextmenü für den Knoten **Abhängigkeiten** des **StringLibraryTest**-Projekts, und wählen Sie **Verweis hinzufügen** aus. Dadurch wird ein Verweis auf unser Klassenbibliotheksprojekt, `StringLibrary`, hinzugefügt. 

1. Erweitern Sie im Dialogfeld **Verweis-Manager** den **Projekte**-Knoten, wählen Sie **Projektmappe**, und aktivieren Sie das Kontrollkästchen neben **StringLibrary**, wie in der folgenden Abbildung dargestellt. Das Hinzufügen eines Verweises auf die `StringLibrary`-Assembly ermöglicht dem Compiler, Aufrufe der **StringLibrary**-Methoden aufzulösen.

   ![Bild](./media/add_reference.jpg)

1. Klicken Sie auf die **OK**-Schaltfläche, um das **Verweis-Manager** Dialogfeld zu schließen.

## <a name="adding-and-running-unit-test-methods"></a>Hinzufügen und Ausführen von Komponententestmethoden ##

Wenn Visual Studio einen Komponententest ausführt, wird jede Methode in einer Komponententestklasse (der Klasse, auf die das [\[TestClass\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx)-Attribut angewendet wird) ausgeführt, die mit dem [\[TestMethod\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx)-Attribut markiert ist. Eine Testmethode endet, wenn der erste Fehler aufgetreten ist, oder wenn alle in der Methode enthaltenen Tests erfolgreich ausgeführt wurden.

Die am häufigsten verwendeten Tests rufen Member der [Assert](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.assert.aspx)-Klasse auf. Viele Assert-Methoden enthalten mindestens zwei Parameter, von denen einer das erwartete und der andere das tatsächliche Testergebnis ist. Zu den am häufigsten aufgerufenen Methoden zählen:

- `Assert.AreEqual`, die überprüft, ob zwei Werte oder Objekte gleich sind. Die Bestätigung ist nicht erfolgreich, wenn die Werte oder Objekte nicht gleich sind.

- `Assert.AreSame`, die überprüft, ob zwei Objektvariablen auf das gleiche Objekt verweisen. Die Bestätigung ist nicht erfolgreich, wenn die Variablen auf verschiedene Objekte verweisen.

- `Assert.IsFalse`, die überprüft, ob eine Bedingung „False“ ist. Die Bestätigung ist nicht erfolgreich, wenn die Bedingung „True“ ist.

- `Assert.IsNotNull`, die überprüft, ob ein Objekt nicht `null` ist. Die Bestätigung ist nicht erfolgreich, wenn das Objekt `null` ist.

Darüber hinaus kann das [\[ExpectedException\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.expectedexceptionattribute.aspx)-Attribut verwendet werden, um den Typ der Ausnahme anzugeben, den eine Testmethode auslösen soll. Sie testen damit Bedingungen, die zu einer Ausnahme führen sollten. Der Test ist nicht erfolgreich, wenn die angegebene Ausnahme nicht ausgelöst wird.

Beim Testen der `StringLibrary.StartsWithUpper`-Methode möchten wir eine Reihe von Zeichenfolgen bereitstellen, die mit einem Großbuchstaben beginnen. Wir erwarten, dass die Methode in diesen Fällen `True` zurückgibt, also können wir die [Assert.IsTrue(Boolean, String)](https://msdn.microsoft.com/library/ms243754.aspx)-Methode aufrufen. Außerdem möchten wir eine Reihe von Zeichenfolgen bereitstellen, die nicht mit einem Großbuchstaben beginnen. Wir erwarten, dass die Methode in diesen Fällen „False“ zurückgibt, also können wir die [Assert.IsFalse(Boolean, String)](https://msdn.microsoft.com/library/ms243805.aspx)-Methode aufrufen.

Da unsere Bibliotheksmethode Zeichenfolgen behandelt, möchten wir auch sicherstellen, dass sie eine [leere Zeichenfolge](xref:System.String.Empty) (eine gültige Zeichenfolge, die keine Zeichen enthält und deren @System.String.Length 0 ist) und eine `null`-Zeichenfolge (eine Zeichenfolge, die nicht initialisiert wurde) erfolgreich behandelt. Wenn `StartsWithUpper` als eine Erweiterungsmethode für eine @System.String-Instanz aufgerufen wird, kann ihr keine `null`-Zeichenfolge übergeben werden. Allerdings kann sie auch direkt als statische Methode aufgerufen und ihr ein einzelnes @System.String-Argument übergeben werden.

Wir definieren drei Methoden, von denen jede ihre [Assert](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.assert.aspx)-Methode wiederholt für jedes Element in einem Zeichenfolgenarray aufruft. Da die Testmethode nicht fortgesetzt wird, sobald sie auf den ersten Fehler trifft, rufen wir eine Methodenüberladung auf, mit der wir eine Zeichenfolge übergeben können, die den Zeichenfolgenwert angibt, der im Methodenaufruf verwendet wird.

So erstellen Sie die Testmethoden:

1. Ersetzen Sie den Code im Codefenster durch den folgenden Code:

   [!CODE-csharp[Test#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs#1)]

   Beachten Sie, dass unser Großbuchstabentest in der `TestStartsWithUpper`-Methode den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+ 041C) umfasst, und der Kleinbuchstabentest in der `TestDoesNotStartWithUpper`-Methode den griechischen Kleinbuchstaben Alpha (U+03B1) und den kyrillischen Kleinbuchstaben Ghe (U+0433).

1. Wählen Sie in der Menüleiste **Datei**, **UnitTest1.cs speichern unter** aus. Wählen Sie im Dialogfeld **Datei speichern unter** den Pfeil neben der Schaltfläche **Speichern**, und wählen Sie dann **Mit Codierung speichern...***.

1. Wählen Sie im Dialogfeld „Speichern unter bestätigen“ die Schaltfläche **Ja**, um die Datei zu speichern.

1. Wählen Sie in der Dropdownliste **Codierung** des Dialogfelds **Erweiterte Speicheroptionen** **Unicode (UTF-8 mit Signatur) - Codepage 65001** und dann **OK**.

   Wenn Sie den Quellcode nicht in einer UTF8-codierten Datei speichern, kann Visual Studio ihn als ASCII-Datei speichern. In diesem Fall decodiert die Laufzeit Zeichen außerhalb des ASCII-Bereichs nicht richtig, und die Testergebnisse sind nicht präzise.

1. Wählen Sie in der Menüleiste **Test**, **Ausführen**, **Alle Tests** aus. Das **Test-Explorer**-Fenster wird geöffnet und zeigt, dass beide Tests erfolgreich waren, wie die folgende Abbildung zeigt. Beachten Sie, dass die drei Tests im Abschnitt **Bestandene Tests** aufgelistet sind, und im Abschnitt **Zusammenfassung** das Ergebnis des Testlaufs berichtet wird.

   ![Bild](./media/first_test.jpg)

## <a name="handling-test-failures"></a>Behandeln von Testfehlern ##

In unserem Testlauf sind keine Fehler aufgetreten, darum verändern wir ihn leicht , sodass eine der Testmethoden nicht fortgesetzt wird:

1. Fügen Sie die Zeichenfolge „Error“ in das `words`-Array in der `TestDoesNotStartWithUpper`-Methode ein, sodass die Anweisung wie folgt lautet:

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. Führen Sie den Test mit **Test**, **Ausführen**, **Alle Tests** aus. Im **Test-Explorer**-Fenster wird jetzt angezeigt, dass zwei Tests erfolgreich waren und einer fehlerhaft ist, wie in der folgenden Abbildung dargestellt.

   ![Bild](./media/failed_test.jpg)

1. Wählen Sie den fehlerhaften Test, `TestDoesNotStartWith`, im Abschnitt **Fehlgeschlagene Tests** aus. Im unteren Bereich des **Test-Explorers** wird die Assert-Meldung angezeigt: „Fehler bei Assert.IsFalse. Für 'Error' erwartet: False; tatsächlich: True“, wie die folgende Abbildung des **Test-Explorers** zeigt. Wegen des Fehlers wurden alle auf „Error“ folgenden Zeichenfolgen im Array nicht getestet.

   ![Bild](./media/failed_test2.jpg)

1. Entfernen Sie den Code, der hinzugefügt wurde (`"Error", `), und führen den Test erneut aus. Er sollte jetzt erfolgreich sein.

## <a name="testing-the-release-version-of-the-library"></a>Testen der endgültigen Produktversion der Bibliothek ##

Wir haben unsere Tests für die Debugversion der Bibliothek ausgeführt. Da nun alle unsere Tests erfolgreich waren, und wir unsere Bibliothek ausreichend getestet haben, sollten wir die Tests ein weiteres Mal für die endgültige Produktversion der Bibliothek ausführen. Eine Reihe von Faktoren einschließlich der Compileroptimierungen kann manchmal zu einem unterschiedlichen Verhalten von Debug- und endgültiger Produktversion führen.

So testen Sie die endgültige Produktversion:

1. Ändern Sie in der Symbolleiste von Visual Studio die Buildkonfiguration von **Debuggen** zu **Freigabe**. Die folgende Abbildung zeigt einen Teil der Symbolleiste.

   ![Bild](./media/lib_release.jpg)

1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für den **StringLibrary**-Projektknoten, und wählen Sie **Erstellen**, um die Bibliothek neu zu kompilieren.

1. Führen Sie die Komponententests erneut durch Auswahl von **Test**, **Ausführen**, **Alle Tests** im Visual Studio-Menü aus. Alle Tests sollten erfolgreich sein.

Das Testen Ihrer Bibliothek ist jetzt abgeschlossen, und im nächsten Schritt machen Sie sie für die Aufrufer verfügbar. Sie können sie mit einer oder mehreren Anwendungen bündeln oder sie als NuGet-Paket verteilen. Informationen hierzu finden Sie unter [Consuming a .NET Standard Class Library](./consuming-library-with-visual-studio-2017.md) (Nutzen einer .NET-Standardklassenbibliothek).

