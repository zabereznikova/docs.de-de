---
title: "Erstellen einer vollständigen .NET Core-Lösung unter macOS mit Visual Studio für Mac | Microsoft-Dokumentation"
description: "Dieses Thema führt Sie durch die Erstellung einer .NET Core-Lösung, die eine wiederverwendbare Bibliothek und Komponententests enthält."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 03/16/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 6945bedf-5bf3-4955-8588-83fb87511b79
translationtype: Human Translation
ms.sourcegitcommit: ff143583ba62fc1d82561e739a75107e50ebee88
ms.openlocfilehash: c76168d1c9ae65ef0d17c55aab156a4f16ecea52
ms.lasthandoff: 03/20/2017

---

# <a name="building-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a>Erstellen einer vollständigen .NET Core-Lösung unter macOS mit Visual Studio für Mac

Visual Studio für Mac bietet eine umfassende integrierte Entwicklungsumgebung (IDE) für die Entwicklung von .NET Core-Anwendungen. Dieses Thema führt Sie durch die Erstellung einer .NET Core-Lösung, die eine wiederverwendbare Bibliothek und Komponententests enthält.

Dieses Tutorial zeigt Ihnen, wie Sie eine Anwendung erstellen, die einen Suchbegriff und eine Textzeichenfolge vom Benutzer akzeptiert, das Vorkommen des Suchbegriffs in der Zeichenfolge mit einer Methode in einer Klassenbibliothek zählt und das Ergebnis an den Benutzer zurückgibt. Die Lösung umfasst auch Komponententests für die Klassenbibliothek als Einführung in die Konzepte der testgesteuerten Entwicklung (Test-Driven Development, TDD). Wenn Sie das Tutorial lieber mit einem vollständigen Beispiel durchlaufen möchten, laden Sie die [Beispielprojektmappe](https://github.com/dotnet/docs/blob/master/samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter) herunter.

> [!NOTE]
> Visual Studio für Mac ist eine Preview-Software. Wie bei allen Preview-Versionen von Microsoft-Produkten wird Ihr Feedback sehr geschätzt. Es gibt zwei Möglichkeiten, wie Sie Feedback für das Entwicklungsteam von Visual Studio für Mac bereitstellen können:
> * Wählen Sie in Visual Studio für Mac **Hilfe > Ein Problem melden** aus dem Menü oder **Ein Problem melden** von der Willkommensseite aus, sodass ein Fenster für das Einreichen eines Fehlerberichts geöffnet wird.
> * Um einen Vorschlag zu machen, wählen Sie **Hilfe > Vorschlag senden** aus dem Menü oder **Vorschlag senden** von der Willkommensseite aus, sodass Sie zur [Visual Studio for Mac UserVoice webpage (UserVoice-Webseite von Visual Studio für Mac)](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac) gelangen.

## <a name="prerequisites"></a>Erforderliche Komponenten

[.NET Core und OpenSSL](https://www.microsoft.com/net/core#macos)

Weitere Informationen über erforderliche Komponenten finden Sie unter [Prerequisites for .NET Core on Mac (Erforderliche Komponenten für .NET Core unter Mac)](../../core/macos-prerequisites.md).

## <a name="getting-started"></a>Erste Schritte

Wenn Sie bereits die erforderlichen Komponenten und Visual Studio für Mac installiert haben, überspringen Sie diesen Abschnitt, und fahren Sie mit [Erstellen einer Bibliothek](#building-a-library) fort. Um die erforderlichen Komponenten und Visual Studio für Mac zu installieren, gehen Sie wie folgt vor:

1. Laden Sie [.NET Core und OpenSSL](https://www.microsoft.com/net/core#macos) herunter und installieren Sie es.

1. Laden Sie den [Visual Studio für Mac-Installer](https://www.visualstudio.com/vs/visual-studio-mac/) herunter. Führen Sie den Installer aus. Lesen und akzeptieren Sie die Lizenzbedingungen. Während der Installation haben Sie die Möglichkeit zum Installieren von Xamarin, einer plattformübergreifenden mobilen App-Entwicklungstechnologie. Das Installieren von Xamarin und den zugehörigen Komponenten ist für die Entwicklung mit .NET Core optional. Eine exemplarische Vorgehensweise für den Visual Studio für Mac-Installationsvorgang finden Sie unter [Introducing Visual Studio for Mac (Einführung in Visual Studio für Mac)](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/). Wenn die Installation abgeschlossen ist, starten Sie Visual Studio für Mac-IDE.

## <a name="building-a-library"></a>Erstellen einer Bibliothek

1. Wählen Sie auf der Willkommensseite **Neues Projekt** aus. Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **Multiplatform** (Mehrere Plattformen) die Vorlage **.NET-Standardbibliothek** aus. Klicken Sie auf **Weiter**.

   ![Dialogfeld "Neues Projekt"](./media/using-on-mac-vs-full-solution/vsmacfull01.png)

1. Nennen Sie das Projekt „TextUtils“ (eine Kurzform von „Text Utilities“) und die Projektmappe „WordCounter“. Lassen Sie **Erstellt ein Projektverzeichnis innerhalb des Projektmappenverzeichnisses** aktiviert. Wählen Sie **Erstellen** aus.

   ![Dialogfeld "Neues Projekt"](./media/using-on-mac-vs-full-solution/vsmacfull02.png)

1. Erweitern Sie in der Randleiste **Projektmappe** den `TextUtils`-Knoten, um die von der Vorlage bereitgestellte Klassendatei *Class1.cs* anzuzeigen. Klicken Sie mit der rechten Maustaste auf die Datei, wählen Sie im Kontextmenü **Umbenennen** aus, und benennen Sie die Datei in *WordCount.cs* um. Öffnen Sie die Datei und ersetzen Sie den Inhalt durch den folgenden Code:

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/TextUtils/WordCount.cs)]

1. Speichern Sie die Datei mit einer von drei verschiedenen Methoden: Verwenden Sie die Tastenkombination <kbd>&#8984;</kbd>+<kbd>s</kbd>, wählen Sie im Menü **Datei > Speichern** aus, oder klicken Sie mit der rechten Maustaste auf die Registerkarte der Datei, und wählen Sie im Kontextmenü **Speichern** aus. Die folgende Abbildung zeigt das IDE-Fenster:

   ![IDE-Fenster mit TextUtils-Klassenbibliothek, WordCount-Klassendatei, statischer WordCount-Klasse und GetWordCount-Methode](./media/using-on-mac-vs-full-solution/vsmacfull03.png)

1. Wählen Sie am unteren Rand des IDE-Fensters **Fehler** aus, um den Bereich **Fehler** zu öffnen. Wählen Sie die Schaltfläche **Buildausgabe** aus.

   ![Unterer Rand der IDE mit Fehler-Schaltfläche](./media/using-on-mac-vs-full-solution/vsmacfull03b.png)

1. Wählen Sie im Menü **Build > Build All** (Erstellen > Alle erstellen) aus.

   Die Projektmappe wird erstellt. Im Bereich „Buildausgabe“ wird angezeigt, dass der Build erfolgreich erstellt wurde.

   ![Bereich „Buildausgabe“ des Bereichs „Fehler“ mit Meldung, dass der Build erfolgreich war](./media/using-on-mac-vs-full-solution/vsmacfull04.png)

## <a name="creating-a-test-project"></a>Erstellen eines Testprojekts

Komponententests bieten automatisierte Softwaretests während der Entwicklung und Veröffentlichung. In diesem Tutorial verwenden Sie das Testframework [xUnit](https://xunit.github.io/).

1. Klicken Sie in der Randleiste **Projektmappe** mit der rechten Maustaste auf die Projektmappe `WordCounter`, und wählen Sie **Hinzufügen > Neues Projekt hinzufügen** aus.

1. Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **.NET Core** **Tests** aus. Wählen Sie das **xUnit-Testprojekt** aus, und klicken Sie auf **Weiter**.

   ![Dialogfeld „Neues Projekt“, Erstellen des xUnit-Testprojekts](./media/using-on-mac-vs-full-solution/vsmacfull05.png)

1. Nennen Sie das neue Projekt „TestLibrary“, und wählen Sie **Erstellen** aus.

   ![Dialogfeld „Neues Projekt“, Angeben des Projektnamens](./media/using-on-mac-vs-full-solution/vsmacfull06.png)

1. Fügen Sie einen Verweis auf das `TextUtils`-Projekt hinzu, damit die Testbibliothek mit der `WordCount`-Klasse arbeitet. Klicken Sie in der Randleiste **Projektmappe** mit der rechten Maustaste unter **TestLibrary** auf **Abhängigkeiten**. Wählen Sie im Kontextmenü **Verweise bearbeiten** aus.

1. Wählen Sie im Dialogfeld **Verweise bearbeiten** auf der Registerkarte **Projekte** das Projekt **TextUtils** aus. Klicken Sie auf **OK**.

   ![Dialogfeld „Verweise bearbeiten“](./media/using-on-mac-vs-full-solution/vsmacfull07.png)

1. Benennen Sie im Projekt **TestLibrary** die Datei *UnitTest1.cs* in *TextUtilsTests.cs* um.

1. Öffnen Sie die Datei, und ersetzen Sie den Code folgendermaßen:

   ```csharp
   using Xunit;
   using TextUtils;
   using System.Diagnostics;

   namespace TestLibrary
   {
       public class TextUtils_GetWordCountShould
       {
           [Fact]
           public void IgnoreCasing()
           {
               var wordCount = WordCount.GetWordCount("Jack", "Jack jack");
   
               Assert.NotEqual(2, wordCount);
           }
       }
   }
   ```

   Die folgende Abbildung zeigt die IDE mit vorhandenem Komponententestcode. Beachten Sie die `Assert.NotEquals`-Anweisung.

   ![Erster Komponententest zur Überprüfung von GetWordCount im IDE-Hauptfenster](./media/using-on-mac-vs-full-solution/vsmacfull08.png)

   Bei Verwendung von TDD ist es wichtig, bei einem neuen Test einmal einen Fehler auftreten zu lassen, um die Richtigkeit der Testlogik zu bestätigen. Die Methode übergibt den Namen „Jack“ (Großschreibung) und eine Zeichenfolge mit „Jack“ und „jack“ (Groß- und Kleinschreibung). Wenn die `GetWordCount`-Methode ordnungsgemäß funktioniert, gibt sie für den Suchbegriffs eine Anzahl von zwei Instanzen zurück. Um diesen Test absichtlich fehlschlagen zu lassen, implementieren Sie den Test zuerst so, dass behauptet wird, dass für den Suchbegriff „Jack“ von der `GetWordCount`-Methode nicht zwei Instanzen zurückgegeben werden. Fahren Sie mit dem nächsten Schritt fort, um den Test absichtlich fehlschlagen zu lassen.

1. Derzeit integriert Visual Studio für Mac keine xUnit-Tests in das integrierte Testprogramm, sodass xUnit-Tests in der Konsole ausgeführt werden müssen. Klicken Sie mit der rechten Maustaste auf das Projekt `TestLibrary`, und wählen Sie im Kontextmenü **Tools > In Terminal öffnen** aus. Führen Sie an der Eingabeaufforderung `dotnet test` aus.
   
   Der Test schlägt fehl, was das richtige Ergebnis ist. Die Testmethode behauptet, dass bei Bereitstellen der Zeichenfolge „Jack jack“ an die `GetWordCount`-Methode nicht zwei Instanzen von `inputString` „Jack“ zurückgegeben werden. Da die Wortschreibweise in der `GetWordCount`-Methode ausgelagert wurde, werden zwei Instanzen zurückgegeben. Die Assertion, dass 2 *nicht gleich* 2 ist, schlägt fehl. Dies ist das richtige Ergebnis, und die Logik unseres Tests funktioniert. Lassen Sie das Konsolenfenster geöffnet, wenn Sie den Test für die endgültige Version im nächsten Schritt ändern.

   ![Anzeige im Konsolenfenster, dass der Test fehlgeschlagen ist. Gesamtanzahl von Tests: 1 Erfolgreich: 0 Fehler: 1. Testlauf konnte nicht durchgeführt werden.](./media/using-on-mac-vs-full-solution/vsmacfull09.png)

1. Ändern Sie die `IgnoreCasing`-Testmethode, indem Sie `Assert.NotEqual` in `Assert.Equal` ändern. Speichern Sie die Datei mit der Tastenkombination <kbd>&#8984;</kbd>+<kbd>s</kbd>, **Datei > Speichern** im Menü, oder durch Klicken mit der rechten Maustaste auf die Registerkarte der Datei und Auswählen von **Speichern** im Kontextmenü.

   Sie erwarten, dass `searchWord` „Jack“ zwei Instanzen zurückgibt, wenn `inputString` „Jack jack“ an `GetWordCount` übergeben wird. Führen Sie im Konsolenfenster erneut `dotnet test` aus. Der Test wurde erfolgreich ausgeführt. Es gibt zwei Instanzen von „Jack“ in der Zeichenfolge „Jack jack“ (wenn Groß- und Kleinschreibung ignoriert wird), und die Testassertion ist `true`.

   ![Anzeige im Konsolenfenster, dass der Test erfolgreich war. Gesamtanzahl von Tests: 1 Erfolgreich: 1 Fehler: 0. Testlauf wurde erfolgreich durchgeführt.](./media/using-on-mac-vs-full-solution/vsmacfull10.png)

1. Das Testen einzelner Rückgabewerte mit `Fact` ist nur ein Teil von allem, was Sie mit Komponententests durchführen können. Mit einem weiteren leistungsfähigen Verfahren können Sie mit `Theory` mehrere Werte gleichzeitig testen. Fügen Sie der `TextUtils_GetWordCountShould`-Klasse die folgende Methode hinzu. Nach dem Hinzufügen dieser Methode gibt es zwei Methoden in der Klasse:

   ```csharp
   [Theory]
   [InlineData(0, "Ting", "Does not appear in the string.")]
   [InlineData(1, "Ting", "Ting appears once.")]
   [InlineData(2, "Ting", "Ting appears twice with Ting.")]
   public void CountInstancesCorrectly(int count, 
                                       string searchWord, 
                                       string inputString)
   {
       Assert.Equal(count, WordCount.GetWordCount(searchWord,
                                                  inputString));
   }
   ```

   Die Methode `CountInstancesCorrectly` überprüft, ob die Methode `GetWordCount` ordnungsgemäß zählt. Die Methode `InlineData` bietet eine Anzahl, einen Suchbegriff und eine Eingabezeichenfolge zur Überprüfung an. Die Testmethode wird für jede Datenzeile einmal ausgeführt. Beachten Sie nochmals, dass Sie zunächst mit `Assert.NotEqual` einen Fehler behaupten, selbst wenn Sie wissen, dass die Zahlen in den Daten korrekt sind und die Werte mit der von der `GetWordCount`-Methode zurückgegebenen Anzahl übereinstimmen werden. Den Test absichtlich fehlschlagen zu lassen, mag zunächst wie Zeitverschwendung erscheinen, aber dies ist eine wichtige Überprüfung der Logik des Tests. Irgendwann werden Sie wahrscheinlich auf eine Testmethode stoßen, die erfolgreich ist, wenn Sie erwarten, dass ein Fehler auftritt, und finden so einen Fehler in der Logik des Tests. Es lohnt sich, diesen Aufwand jedes Mal zu tätigen, wenn Sie eine Testmethode erstellen.
   
1. Speichern Sie die Datei, und führen Sie `dotnet test` im Konsolenfenster aus. Der Test der Schreibweise ist erfolgreich, aber die drei Tests der Anzahl schlagen fehl. Dies ist genau das, was Sie erwarten.

   ![Anzeige im Konsolenfenster, dass der Test fehlgeschlagen ist. Gesamtanzahl von Tests: 4 Erfolgreich: 1 Fehler: 3. Testlauf konnte nicht durchgeführt werden.](./media/using-on-mac-vs-full-solution/vsmacfull11.png)

1. Ändern Sie die `CountInstancesCorrectly`-Testmethode, indem Sie `Assert.NotEqual` in `Assert.Equal` ändern. Speichern Sie die Datei. Führen Sie im Konsolenfenster erneut `dotnet test` aus. Alle Tests erfolgreich.

   ![Anzeige im Konsolenfenster, dass der Test erfolgreich war. Gesamtanzahl von Tests: 4 Erfolgreich: 4 Fehler: 0. Testlauf wurde erfolgreich durchgeführt.](./media/using-on-mac-vs-full-solution/vsmacfull12.png)

## <a name="adding-a-console-app"></a>Hinzufügen einer Konsolenanwendung

1. Klicken Sie in der Randleiste **Projektmappe** mit der rechten Maustaste auf die Projektmappe `WordCounter`. Fügen Sie ein neues **Konsolenanwendungsprojekt** hinzu, indem Sie die Vorlage aus den Vorlagen unter **.NET Core > App** auswählen. Klicken Sie auf **Weiter**. Nennen Sie das Projekt **WordCounterApp**. Wählen Sie **Erstellen** aus, um das Projekt in der Projektmappe zu erstellen.

1. Klicken Sie in der Randleiste **Projektmappe** mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des neuen **WordCounterApp**-Projekts. Aktivieren Sie im Dialogfeld **Verweise bearbeiten** das Kontrollkästchen **TextUtils**, und klicken Sie auf **OK**.

1. Öffnen Sie die Datei *Program.cs*. Ersetzen Sie den Code durch Folgendes:

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/WordCounterApp/Program.cs)]

1. Zum Ausführen der Anwendung in einem Konsolenfenster anstatt in IDE klicken Sie mit der rechten Maustaste auf das `WordCounterApp`-Projekt, wählen **Optionen** aus, und öffnen unter **Konfigurationen** den Knoten **Standard**. Aktivieren Sie das Kontrollkästchen für **Auf externer Konsole ausführen**. Lassen Sie die Option **Konsolenausgabe anhalten** aktiviert. Diese Einstellung bewirkt, dass die Anwendung in einem Konsolenfenster gestartet wird und Sie Eingaben für die `Console.ReadLine`-Anweisungen eingeben können. Wenn Sie die Anwendung weiterhin in IDE ausführen, sehen Sie nur die Ausgabe von `Console.WriteLine`-Anweisungen. `Console.ReadLine`-Anweisungen funktionieren nicht im Bereich **Anwendungsausgabe** von IDE.

   ![Fenster „Projektoptionen“](./media/using-on-mac-vs-full-solution/vsmacfull13.png)

1. Da die Visual Studio-Vorschau für Mac derzeit keine Tests ausführen kann, wenn die Projektmappe ausgeführt wird, führen Sie die Konsolenanwendung direkt aus. Klicken Sie mit der rechten Maustaste auf das `WordCounterApp`-Projekt, und wählen Sie im Kontextmenü **Run item** (Element ausführen) aus. Wenn Sie versuchen, die Anwendung mit der Schaltfläche „Wiedergabe“ auszuführen, schlägt die Ausführung des Testprogramms und der Anwendung fehl. Weitere Informationen über den Stand der Arbeit an diesem Problem finden Sie unter [xunit/xamarinstudio.xunit (#60)](https://github.com/xunit/xamarinstudio.xunit/issues/60). Geben Sie bei der Ausführung der Anwendung Werte für den Suchbegriff und die Eingabezeichenfolge an den Eingabeaufforderungen im Konsolenfenster an. Die Anwendung gibt an, wie oft der Suchbegriff in der Zeichenfolge vorkommt.

   ![Konsolenfenster mit dem Wort „olives“ (Oliven), das in der Zeichenfolge „Iro ate olives by the lake, and the olives were wonderful.“ (Iro hat am See Oliven gegessen, und die Oliven waren wunderbar.) gesucht wurde Die Anwendung antwortet „The search word olives appears 2 times.“ (Der Suchbegriff Oliven kommt zweimal vor.)](./media/using-on-mac-vs-full-solution/vsmacfull14.png)

1. Die letzte Funktion, die wir erkunden, ist das Debuggen mit Visual Studio für Mac. Setzen Sie einen Haltepunkt an der Anweisung `Console.WriteLine`. Klicken Sie auf den Rand links neben Zeile 23. Daraufhin wird neben der Codezeile ein roter Kreis angezeigt. Wählen Sie alternativ eine beliebige Stelle in der Codezeile und dann im Menü **Ausführen > Haltepunkt ein/aus** aus.

   ![Haltepunkt auf Zeile 23 (Console.WriteLine-Anweisung) festgelegt](./media/using-on-mac-vs-full-solution/vsmacfull15.png)

1. Klicken Sie mit der rechten Maustaste auf das `WordCounterApp`-Projekt. Wählen Sie im Kontextmenü **Start Debugging item** (Debuggen des Elements starten) aus. Wenn die Anwendung ausgeführt wird, geben Sie den Suchbegriff „cat“ (Katze) und „The dog chased the cat, but the cat escaped.“ (Der Hund jagte die Katze, aber die Katze entkam.) für die zu durchsuchende Zeichenfolge ein. Wenn die `Console.WriteLine`-Anweisung erreicht wird, wird die Ausführung des Programms angehalten, bevor die Anweisung ausgeführt wird. In der Registerkarte **Lokal** sehen Sie die Werte `searchWord`, `inputString`, `wordCount` und `pluralChar`.

   ![Ausführung des Programms bei Console.WriteLine-Anweisung angehalten, Fenster „Lokal“ zeigt die Werte unmittelbar vor der Ausführung der Console.WriteLine-Anweisung](./media/using-on-mac-vs-full-solution/vsmacfull16.png)

1. Geben Sie im Bereich **Direkt** „wordCount = 999;“ ein, und drücken Sie die Eingabetaste. Dadurch wird der unsinnige Wert 999 der `wordCount`-Variable zugewiesen, was zeigt, dass Sie während des Debuggens Variablenwerte ersetzen können.

   ![Unser Haltepunkt wird erreicht. Im Fenster „Direkt“ wird wordCount in den Wert 999 geändert](./media/using-on-mac-vs-full-solution/vsmacfull17.png)

1. Klicken Sie in der Symbolleiste auf den Pfeil *Weiter*. Betrachten Sie die Ausgabe im Konsolenfenster. Sie zeigt den falschen Wert 999 an, den Sie beim Debuggen der Anwendung festgelegt haben.

   ![Schaltfläche „Weiter“ auf der Symbolleiste](./media/using-on-mac-vs-full-solution/vsmacfull18.png)

   ![Die Anzahl des gesuchten Begriffs wird in der Ausgabe der Anwendung auf den Wert 999 geändert](./media/using-on-mac-vs-full-solution/vsmacfull19.png)

## <a name="next-steps"></a>Nächste Schritte

* Erkunden Sie die zusätzlichen Funktionen von Visual Studio für Mac unter [Introducing Visual Studio for Mac (Einführung in Visual Studio für Mac)](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/) auf der Xamarin-Entwicklerwebseite.
* Noch mehr Informationen zu den Funktionen von Visual Studio für Mac erhalten Sie im Leitfaden [Xamarin Studio Tour (Xamarin Studio-Tour)](https://developer.xamarin.com/guides/cross-platform/xamarin-studio/ide-tour/).

