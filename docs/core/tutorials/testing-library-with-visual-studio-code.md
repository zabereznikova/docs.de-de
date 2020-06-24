---
title: Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio Code
description: Erstellen Sie ein Komponententestprojekt für eine .NET Core-Klassenbibliothek. Sie überprüfen mithilfe von Komponententests, ob die .NET Core-Klassenbibliothek ordnungsgemäß funktioniert.
ms.date: 06/08/2020
ms.openlocfilehash: a61fd952eea2dec0d5a9f351d3f3d01c738e8fad
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2020
ms.locfileid: "84701032"
---
# <a name="tutorial-test-a-net-standard-class-library-with-net-core-using-visual-studio-code"></a>Tutorial: Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio Code

In diesem Tutorial wird gezeigt, wie Sie Komponententests automatisieren, indem Sie einer Projektmappe ein Testprojekt hinzufügen.

## <a name="prerequisites"></a>Voraussetzungen

- In diesem Tutorial wird die Projektmappe verwendet, die Sie in [Erstellen einer .NET Standard-Bibliothek in Visual Studio Code](library-with-visual-studio-code.md) erstellen.

## <a name="create-a-unit-test-project"></a>Ein Komponententestprojekt erstellen

Komponententests bieten automatisierte Softwaretests während der Entwicklung und Veröffentlichung. Das in diesem Tutorial verwendete Testframework ist MSTest. [MSTest](https://github.com/Microsoft/testfx-docs) ist eines von drei Testframeworks, aus denen Sie wählen können. Die beiden anderen sind [xUnit](https://xunit.net/) und [nUnit](https://nunit.org/).

1. Starten Sie Visual Studio Code.

1. Öffnen Sie die `ClassLibraryProjects`-Projektmappe, die Sie in [Erstellen einer .NET Standard-Bibliothek in Visual Studio](library-with-visual-studio.md) erstellt haben.

1. Erstellen Sie ein Komponententestprojekt namens „StringLibraryTest“.

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   Die Projektvorlage erstellt die Datei „UnitTest1.cs“, die den folgenden Code enthält:

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
   - Er wendet das Attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> an, um `TestMethod1` zu definieren.

   Jede mit [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) gekennzeichnete Methode in einer mit [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) gekennzeichneten Testklasse wird automatisch ausgeführt, wenn der Komponententest ausgeführt wird.

1. Fügen Sie das Testprojekt zur Projektmappe hinzu.

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

## <a name="add-a-project-reference"></a>Hinzufügen eines Projektverweises

Damit das Testprojekt mit der `StringLibrary`-Klasse funktioniert, fügen Sie im Projekt `StringLibraryTest` einen Verweis auf das Projekt `StringLibrary` hinzu.

1. Führen Sie den folgenden Befehl aus:

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

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

Da Ihre Bibliotheksmethode Zeichenfolgen verarbeitet, sollten Sie sicherstellen, dass sie eine [leere Zeichenfolge (`String.Empty`)](xref:System.String.Empty) und eine `null`-Zeichenfolge erfolgreich verarbeiten kann. Eine leere Zeichenfolge enthält keine Zeichen, und ihre <xref:System.String.Length>-Eigenschaft weist den Wert „0“ auf. Eine `null`-Zeichenfolge ist eine Zeichenfolge, die nicht initialisiert wurde. Sie können `StartsWithUpper` als statische Methode direkt aufrufen und ein einzelnes <xref:System.String>-Argument übergeben. Alternativ können Sie `StartsWithUpper` als Erweiterungsmethode für eine `string`-Variable aufrufen, die `null` zugewiesen ist.

Sie definieren drei Methoden, von denen jede eine zugehörige <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>-Methode für jedes Element in einem Zeichenfolgenarray aufruft. Sie rufen eine Methodenüberladung auf, mit der Sie eine Fehlermeldung angeben können, die bei einem Testfehler angezeigt werden soll. Die Meldung enthält die Zeichenfolge, die den Fehler verursacht hat.

So erstellen Sie die Testmethoden:

1. Öffnen Sie die Datei *StringLibraryTest/UnitTest1.cs*, und ersetzen Sie den gesamten Code durch den folgenden:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   Der Test für Großbuchstaben in der `TestStartsWithUpper`-Methode enthält den griechischen Großbuchstaben Alpha (U+0391) und den kyrillischen Großbuchstaben EM (U+041C). Der Test für Kleinbuchstaben in der `TestDoesNotStartWithUpper`-Methode enthält den griechischen Kleinbuchstaben alpha (U+03B1) und den kyrillischen Kleinbuchstaben ghe (U+0433).

1. Speichern Sie die Änderungen.

1. Führen Sie die Tests aus:

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   Die Terminalausgabe gibt an, dass alle Tests bestanden wurden.

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
   Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a>Behandeln von Testfehlern

Bei der testgesteuerten Entwicklung (Test-Driven Development, TDD) schreiben Sie zunächst Tests, bei deren ersten Ausführung Fehler auftreten. Anschließend fügen Sie der App Code hinzu, mit dem der Test erfolgreich ausgeführt wird. Für dieses Tutorial haben Sie den Test, der den Code überprüft, nach Schreiben des App-Codes erstellt, sodass beim Test kein Fehler aufgetreten ist. Fügen Sie einen ungültigen Wert zur Testeingabe hinzu, um zu überprüfen, ob beim Test auch wirklich erwartungsgemäß ein Fehler auftritt.

1. Verändern Sie das `words`-Array in der `TestDoesNotStartWithUpper`-Methode, um die Zeichenfolge "Error" einzufügen.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. Führen Sie die Tests aus:

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   Die Terminalausgabe zeigt, dass bei einem Test ein Fehler auftritt, und gibt eine Fehlermeldung für diesen Test an: „Fehler bei Assert.IsFalse. Für 'Error' erwartet: False; tatsächlich: True“. Wegen des Fehlers wurden keine auf „Error“ folgenden Zeichenfolgen im Array getestet.

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

1. Entfernen Sie die Zeichenfolge „Error“, die Sie in Schritt 1 hinzugefügt haben. Führen Sie den Test erneut aus. Nun ist er erfolgreich.

## <a name="test-the-release-version-of-the-library"></a>Testen der Releaseversion der Bibliothek

Nachdem die Tests beim Ausführen des Debugbuilds der Bibliothek nun alle erfolgreich waren, führen Sie die Tests auch für den Releasebuild der Bibliothek aus. Eine Reihe von Faktoren einschließlich der Compileroptimierungen kann manchmal zu einem unterschiedlichen Verhalten von Debug- und endgültiger Produktversion führen.

1. Führen Sie die Tests mit der Releasebuildkonfiguration aus:

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   Die Tests sind erfolgreich.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Komponententests in .NET Core und .NET Standard](../testing/index.md)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Komponententests für eine Klassenbibliothek ausgeführt. Sie können die Bibliothek anderen Benutzern zur Verfügung stellen, indem Sie sie als Paket auf [NuGet](https://nuget.org) veröffentlichen. Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:

> [!div class="nextstepaction"]
> [Erstellen und Veröffentlichen eines Pakets mithilfe der dotnet-CLI](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

Wenn Sie eine Bibliothek als NuGet-Paket veröffentlichen, können andere Benutzer diese installieren und verwenden. Weitere Informationen dazu finden Sie in einem NuGet-Tutorial:

> [!div class="nextstepaction"]
> [Installieren und Verwenden eines Pakets mithilfe der dotnet-CLI](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

Eine Bibliothek muss nicht als Paket verteilt werden. Sie kann mit einer Konsolen-App gebündelt werden, die sie verwendet. Informationen zum Veröffentlichen einer Konsolen-App finden Sie in einem früheren Tutorial dieser Reihe:

> [!div class="nextstepaction"]
> [Veröffentlichen einer .NET Core-Konsolenanwendung mit Visual Studio Code](publishing-with-visual-studio-code.md)
