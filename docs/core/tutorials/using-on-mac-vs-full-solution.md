---
title: Erstellen einer vollständigen .NET Core-Lösung unter macOS mit Visual Studio für Mac
description: Dieses Thema führt Sie durch die Erstellung einer .NET Core-Lösung, die eine wiederverwendbare Bibliothek und Komponententests enthält.
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.openlocfilehash: 17d7cc5b085b4d47ebf1e5ed9a766be9d5d8b01f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43457042"
---
# <a name="building-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a>Erstellen einer vollständigen .NET Core-Lösung unter macOS mit Visual Studio für Mac

Visual Studio für Mac bietet eine umfassende integrierte Entwicklungsumgebung (IDE) für die Entwicklung von .NET Core-Anwendungen. Dieses Thema führt Sie durch die Erstellung einer .NET Core-Lösung, die eine wiederverwendbare Bibliothek und Komponententests enthält.

Dieses Tutorial zeigt Ihnen, wie Sie eine Anwendung erstellen, die einen Suchbegriff und eine Textzeichenfolge vom Benutzer akzeptiert, das Vorkommen des Suchbegriffs in der Zeichenfolge mit einer Methode in einer Klassenbibliothek zählt und das Ergebnis an den Benutzer zurückgibt. Die Lösung umfasst auch Komponententests für die Klassenbibliothek als Einführung in die Konzepte für Komponententests. Wenn Sie das Tutorial lieber mit einem vollständigen Beispiel durchlaufen möchten, laden Sie die [Beispielprojektmappe](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter) herunter. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

> [!NOTE]
> Ihr Feedback wird sehr geschätzt. Es gibt zwei Möglichkeiten, wie Sie Feedback für das Entwicklungsteam von Visual Studio für Mac bereitstellen können:
> * Klicken Sie in Visual Studio für Mac auf **Hilfe** > **Ein Problem melden** im Menü oder auf **Ein Problem melden** auf der Willkommensseite. Dadurch wird ein Fenster für das Einreichen eines Fehlerberichts geöffnet. Sie können Ihr Feedback im Portal der [Entwicklercommunity](https://developercommunity.visualstudio.com/spaces/41/index.html) verfolgen.
> * Um einen Vorschlag zu machen, klicken Sie auf **Hilfe** > **Vorschlag senden** im Menü oder auf **Vorschlag senden** auf der Willkommensseite. Dadurch gelangen Sie zur [Visual Studio for Mac UserVoice webpage (UserVoice-Webseite von Visual Studio für Mac)](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).

## <a name="prerequisites"></a>Erforderliche Komponenten

- OpenSSL (wenn .NET Core 1.1 ausgeführt wird): Weitere Informationen finden Sie unter dem Thema [Voraussetzungen für .NET Core unter Mac](../macos-prerequisites.md).
- [.NET Core SDK 1.1 oder höher](https://www.microsoft.com/net/core#macos)
- [Visual Studio 2017 für Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/)

Weitere Informationen über erforderliche Komponenten finden Sie unter [Prerequisites for .NET Core on Mac (Erforderliche Komponenten für .NET Core unter Mac)](../../core/macos-prerequisites.md). Die vollständigen Systemanforderungen von Visual Studio 2017 für Mac finden Sie unter [Visual Studio 2017 für Mac – Systemanforderungen der Produktfamilie](/visualstudio/productinfo/vs2017-system-requirements-mac).

## <a name="building-a-library"></a>Erstellen einer Bibliothek

1. Wählen Sie auf der Willkommensseite **Neues Projekt** aus. Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **Multiplatform** (Mehrere Plattformen) die Vorlage **.NET-Standardbibliothek** aus. Klicken Sie auf **Weiter**.

   ![Dialogfeld "Neues Projekt"](./media/using-on-mac-vs-full-solution/vsmacfull01.png)

1. Nennen Sie das Projekt „TextUtils“ (eine Kurzform von „Text Utilities“) und die Projektmappe „WordCounter“. Lassen Sie **Erstellt ein Projektverzeichnis innerhalb des Projektmappenverzeichnisses** aktiviert. Wählen Sie **Erstellen** aus.

   ![Dialogfeld "Neues Projekt"](./media/using-on-mac-vs-full-solution/vsmacfull02.png)

1. Erweitern Sie in der Randleiste **Projektmappe** den `TextUtils`-Knoten, um die von der Vorlage bereitgestellte Klassendatei *Class1.cs* anzuzeigen. Klicken Sie mit der rechten Maustaste auf die Datei, wählen Sie im Kontextmenü **Umbenennen** aus, und benennen Sie die Datei in *WordCount.cs* um. Öffnen Sie die Datei und ersetzen Sie den Inhalt durch den folgenden Code:

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/TextUtils/WordCount.cs)]

1. Speichern Sie die Datei mit einer von drei verschiedenen Methoden: Verwenden Sie die Tastenkombination <kbd>&#8984;</kbd>+<kbd>s</kbd>, klicken Sie im Menü auf **Datei** > **Speichern**, oder klicken Sie mit der rechten Maustaste auf die Registerkarte der Datei, und klicken Sie im Kontextmenü auf **Speichern**. Die folgende Abbildung zeigt das IDE-Fenster:

   ![IDE-Fenster mit TextUtils-Klassenbibliothek, WordCount-Klassendatei, statischer WordCount-Klasse und GetWordCount-Methode](./media/using-on-mac-vs-full-solution/vsmacfull03.png)

1. Wählen Sie am unteren Rand des IDE-Fensters **Fehler** aus, um den Bereich **Fehler** zu öffnen. Wählen Sie die Schaltfläche **Buildausgabe** aus.

   ![Unterer Rand der IDE mit Fehler-Schaltfläche](./media/using-on-mac-vs-full-solution/vsmacfull03b.png)

1. Klicken Sie im Menü auf **Build** > **Build All** (Erstellen > Alle erstellen).

   Die Projektmappe wird erstellt. Im Bereich „Buildausgabe“ wird angezeigt, dass der Build erfolgreich erstellt wurde.

   ![Bereich „Buildausgabe“ des Bereichs „Fehler“ mit Meldung, dass der Build erfolgreich war](./media/using-on-mac-vs-full-solution/vsmacfull04.png)

## <a name="creating-a-test-project"></a>Erstellen eines Testprojekts

Komponententests bieten automatisierte Softwaretests während der Entwicklung und Veröffentlichung. Das Testframework, das Sie in diesem Tutorial verwenden, ist [xUnit (Version 2.2.0 oder höher)](https://xunit.github.io/), was automatisch installiert wird, wenn das Testprojekt xUnit der Projektmappe in den folgenden Schritten hinzugefügt wird:

1. Klicken Sie in der Randleiste **Projektmappe** mit der rechten Maustaste auf die Projektmappe `WordCounter` und auf **Hinzufügen** > **Neues Projekt hinzufügen**.

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

   Die folgende Abbildung zeigt die IDE mit vorhandenem Komponententestcode. Beachten Sie die `Assert.NotEqual`-Anweisung.

   ![Erster Komponententest zur Überprüfung von GetWordCount im IDE-Hauptfenster](./media/using-on-mac-vs-full-solution/vsmacfull08.png)

   Es ist wichtig, bei einem neuen Test einmal einen Fehler auftreten zu lassen, um zu prüfen, ob die Testlogik richtig ist. Die Methode übergibt den Namen „Jack“ (Großschreibung) und eine Zeichenfolge mit „Jack“ und „jack“ (Groß- und Kleinschreibung). Wenn die `GetWordCount`-Methode ordnungsgemäß funktioniert, gibt sie für den Suchbegriffs eine Anzahl von zwei Instanzen zurück. Um diesen Test absichtlich fehlschlagen zu lassen, implementieren Sie den Test zuerst so, dass behauptet wird, dass für den Suchbegriff „Jack“ von der `GetWordCount`-Methode nicht zwei Instanzen zurückgegeben werden. Fahren Sie mit dem nächsten Schritt fort, um den Test absichtlich fehlschlagen zu lassen.

1. Öffnen Sie das Panel **Komponententests** auf der rechten Seite des Bildschirms.

   ![Panel Komponententests](./media/using-on-mac-vs-full-solution/vsmacfull_UnitTestPanel.png)

1. Klicken Sie auf das **Andocksymbol**, um das Panel geöffnet zu lassen.

   ![Andocksymbol des Panels Komponententest](./media/using-on-mac-vs-full-solution/vsmacfull_UnitTestPanelDockIcon.png)

1. Klicken Sie auf die Schaltfläche **Alle ausführen**.

   Der Test schlägt fehl, was das richtige Ergebnis ist. Die Testmethode behauptet, dass bei Bereitstellen der Zeichenfolge „Jack jack“ an die `GetWordCount`-Methode nicht zwei Instanzen von `inputString` „Jack“ zurückgegeben werden. Da die Wortschreibweise in der `GetWordCount`-Methode ausgelagert wurde, werden zwei Instanzen zurückgegeben. Die Assertion, dass 2 *nicht gleich* 2 ist, schlägt fehl. Dies ist das richtige Ergebnis, und die Logik unseres Tests funktioniert.

   ![Test fehlgeschlagen](./media/using-on-mac-vs-full-solution/vsmacfull09.png)

1. Ändern Sie die `IgnoreCasing`-Testmethode, indem Sie `Assert.NotEqual` in `Assert.Equal` ändern. Speichern Sie die Datei mit der Tastenkombination <kbd>&#8984;</kbd>+<kbd>s</kbd>, **Datei** > **Speichern** im Menü, oder durch Klicken mit der rechten Maustaste auf die Registerkarte der Datei und Auswählen von **Speichern** im Kontextmenü.

   Sie erwarten, dass `searchWord` „Jack“ zwei Instanzen zurückgibt, wenn `inputString` „Jack jack“ an `GetWordCount` übergeben wird. Führen Sie den Test erneut aus, indem Sie auf die Schaltfläche **Tests ausführen** des Panels **Komponententests** oder auf die Schaltfläche **Tests erneut ausführen** des Panels **Testergebnisse** am unteren Rand des Bildschirms klicken. Der Test wurde erfolgreich ausgeführt. Es gibt zwei Instanzen von „Jack“ in der Zeichenfolge „Jack jack“ (wenn Groß- und Kleinschreibung ignoriert wird), und die Testassertion ist `true`.

   ![Test erfolgreich](./media/using-on-mac-vs-full-solution/vsmacfull10.png)

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
       Assert.NotEqual(count, WordCount.GetWordCount(searchWord,
                                                  inputString));
   }
   ```

   Die Methode `CountInstancesCorrectly` überprüft, ob die Methode `GetWordCount` ordnungsgemäß zählt. Die Methode `InlineData` bietet eine Anzahl, einen Suchbegriff und eine Eingabezeichenfolge zur Überprüfung an. Die Testmethode wird für jede Datenzeile einmal ausgeführt. Beachten Sie nochmals, dass Sie zunächst mit `Assert.NotEqual` einen Fehler behaupten, selbst wenn Sie wissen, dass die Zahlen in den Daten korrekt sind und die Werte mit der von der `GetWordCount`-Methode zurückgegebenen Anzahl übereinstimmen. Den Test absichtlich fehlschlagen zu lassen, mag zunächst wie Zeitverschwendung erscheinen, aber dies ist eine wichtige Überprüfung der Logik des Tests. Wenn Sie auf eine Testmethode stoßen, die erfolgreich ist, wenn Sie erwarten, dass ein Fehler auftritt, haben Sie einen Fehler in der Logik des Tests gefunden. Es lohnt sich, diesen Aufwand jedes Mal zu tätigen, wenn Sie eine Testmethode erstellen.

1. Speichern Sie die Datei, und führen Sie die Tests erneut aus. Der Test der Schreibweise ist erfolgreich, aber die drei Tests der Anzahl schlagen fehl. Dies ist genau das, was Sie erwarten.

   ![Test fehlgeschlagen](./media/using-on-mac-vs-full-solution/vsmacfull11.png)

1. Ändern Sie die `CountInstancesCorrectly`-Testmethode, indem Sie `Assert.NotEqual` in `Assert.Equal` ändern. Speichern Sie die Datei. Führen Sie die Tests erneut aus. Alle Tests erfolgreich.

   ![Test erfolgreich](./media/using-on-mac-vs-full-solution/vsmacfull12.png)

## <a name="adding-a-console-app"></a>Hinzufügen einer Konsolenanwendung

1. Klicken Sie in der Randleiste **Projektmappe** mit der rechten Maustaste auf die Projektmappe `WordCounter`. Fügen Sie ein neues **Konsolenanwendungsprojekt** hinzu, indem Sie die Vorlage aus den Vorlagen unter **.NET Core** > **App** auswählen. Klicken Sie auf **Weiter**. Nennen Sie das Projekt **WordCounterApp**. Wählen Sie **Erstellen** aus, um das Projekt in der Projektmappe zu erstellen.

1. Klicken Sie in der Randleiste **Projektmappe** mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des neuen **WordCounterApp**-Projekts. Aktivieren Sie im Dialogfeld **Verweise bearbeiten** das Kontrollkästchen **TextUtils**, und klicken Sie auf **OK**.

1. Öffnen Sie die Datei *Program.cs*. Ersetzen Sie den Code durch Folgendes:

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/WordCounterApp/Program.cs)]

1. Zum Ausführen der Anwendung in einem Konsolenfenster anstatt in IDE klicken Sie mit der rechten Maustaste auf das `WordCounterApp`-Projekt, wählen **Optionen** aus, und öffnen unter **Konfigurationen** den Knoten **Standard**. Aktivieren Sie das Kontrollkästchen für **Auf externer Konsole ausführen**. Lassen Sie die Option **Konsolenausgabe anhalten** aktiviert. Diese Einstellung bewirkt, dass die Anwendung in einem Konsolenfenster gestartet wird und Sie Eingaben für die `Console.ReadLine`-Anweisungen eingeben können. Wenn Sie die Anwendung weiterhin in IDE ausführen, sehen Sie nur die Ausgabe von `Console.WriteLine`-Anweisungen. `Console.ReadLine`-Anweisungen funktionieren nicht im Bereich **Anwendungsausgabe** von IDE.

   ![Fenster „Projektoptionen“](./media/using-on-mac-vs-full-solution/vsmacfull13.png)

1. Da die aktuelle Version von Visual Studio für Mac keine Tests ausführen kann, wenn die Projektmappe ausgeführt wird, führen Sie die Konsolenanwendung direkt aus. Klicken Sie mit der rechten Maustaste auf das `WordCounterApp`-Projekt, und wählen Sie im Kontextmenü **Run item** (Element ausführen) aus. Wenn Sie versuchen, die Anwendung mit der Schaltfläche „Wiedergabe“ auszuführen, schlägt die Ausführung des Testprogramms und der Anwendung fehl. Weitere Informationen über den Stand der Arbeit an diesem Problem finden Sie unter [xunit/xamarinstudio.xunit (#60)](https://github.com/xunit/xamarinstudio.xunit/issues/60). Geben Sie bei der Ausführung der Anwendung Werte für den Suchbegriff und die Eingabezeichenfolge an den Eingabeaufforderungen im Konsolenfenster an. Die Anwendung gibt an, wie oft der Suchbegriff in der Zeichenfolge vorkommt.

   ![Konsolenfenster mit dem Wort „olives“ (Oliven), das in der Zeichenfolge „Iro ate olives by the lake, and the olives were wonderful.“ (Iro hat am See Oliven gegessen, und die Oliven waren wunderbar.) gesucht wurde Die Anwendung antwortet „The search word olives appears 2 times.“ (Der Suchbegriff Oliven kommt zweimal vor.)](./media/using-on-mac-vs-full-solution/vsmacfull14.png)

1. Die letzte Funktion, die wir erkunden, ist das Debuggen mit Visual Studio für Mac. Setzen Sie einen Haltepunkt an der Anweisung `Console.WriteLine`. Klicken Sie auf den Rand links neben Zeile 23. Daraufhin wird neben der Codezeile ein roter Kreis angezeigt. Klicken Sie alternativ auf eine beliebige Stelle in der Codezeile und dann im Menü auf **Ausführen** > **Haltepunkt ein/aus**.

   ![Haltepunkt auf Zeile 23 (Console.WriteLine-Anweisung) festgelegt](./media/using-on-mac-vs-full-solution/vsmacfull15.png)

1. Klicken Sie mit der rechten Maustaste auf das `WordCounterApp`-Projekt. Wählen Sie im Kontextmenü **Start Debugging item** (Debuggen des Elements starten) aus. Wenn die Anwendung ausgeführt wird, geben Sie den Suchbegriff „cat“ (Katze) und „The dog chased the cat, but the cat escaped.“ (Der Hund jagte die Katze, aber die Katze entkam.) für die zu durchsuchende Zeichenfolge ein. Wenn die `Console.WriteLine`-Anweisung erreicht wird, wird die Ausführung des Programms angehalten, bevor die Anweisung ausgeführt wird. In der Registerkarte **Lokal** sehen Sie die Werte `searchWord`, `inputString`, `wordCount` und `pluralChar`.

   ![Ausführung des Programms bei Console.WriteLine-Anweisung angehalten, Fenster „Lokal“ zeigt die Werte unmittelbar vor der Ausführung der Console.WriteLine-Anweisung](./media/using-on-mac-vs-full-solution/vsmacfull16.png)

1. Geben Sie im Bereich **Direkt** „wordCount = 999;“ ein, und drücken Sie die Eingabetaste. Dadurch wird der unsinnige Wert 999 der `wordCount`-Variable zugewiesen, was zeigt, dass Sie während des Debuggens Variablenwerte ersetzen können.

   ![Unser Haltepunkt wird erreicht. Im Fenster „Direkt“ wird wordCount in den Wert 999 geändert](./media/using-on-mac-vs-full-solution/vsmacfull17.png)

1. Klicken Sie in der Symbolleiste auf den Pfeil *Weiter*. Betrachten Sie die Ausgabe im Konsolenfenster. Sie zeigt den falschen Wert 999 an, den Sie beim Debuggen der Anwendung festgelegt haben.

   ![Schaltfläche „Weiter“ auf der Symbolleiste](./media/using-on-mac-vs-full-solution/vsmacfull18.png)

   ![Die Anzahl des gesuchten Begriffs wird in der Ausgabe der Anwendung auf den Wert 999 geändert](./media/using-on-mac-vs-full-solution/vsmacfull19.png)

## <a name="see-also"></a>Siehe auch

* [Versionsanmerkungen für Visual Studio 2017 für Mac](/visualstudio/releasenotes/vs2017-mac-relnotes)
