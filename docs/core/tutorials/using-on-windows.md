---
title: Erste Schritte mit .NET Core unter Windows
description: Erste Schritte mit .NET Core unter Windows mit Visual Studio 2015
keywords: .NET, .NET Core
author: bleroy
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d743134a-08a3-4ff6-aab7-49f71f0568c3
translationtype: Human Translation
ms.sourcegitcommit: 54da8aebd64e86c064214074bc261f72c3b0aedc
ms.openlocfilehash: 299d479ce74a0e1f41ff42a0e6619f4964788194

---

# <a name="getting-started-with-net-core-on-windows-using-visual-studio-2015"></a>Erste Schritte mit .NET Core unter Windows mit Visual Studio 2015

von [Bertrand Le Roy](https://github.com/bleroy) und [Phillip Carter](https://github.com/cartermp)

Visual Studio 2015 bietet eine umfassende Entwicklungsumgebung für die Entwicklung von .NET Core-Anwendungen. Mit den Verfahren in diesem Dokument werden die erforderlichen Schritte zum Erstellen einer Reihe von typischen .NET Core-Projektmappen oder Projektmappen, die .NET Core-Komponenten enthalten, mithilfe von Visual Studio beschrieben. Die Szenarios enthalten Tests. Zudem werden Bibliotheken von Drittanbietern verwendet, die nicht explizit für die neueste Version von .NET Core erstellt wurden. 

## <a name="prerequisites"></a>Erforderliche Komponenten

Befolgen Sie die Anweisungen auf [unserer Seite über erforderliche Komponenten](../windows-prerequisites.md), um Ihre Umgebung anzupassen.

## <a name="getting-started"></a>Erste Schritte

Mit den folgenden Schritten richten Sie Visual Studio 2015 für die .NET Core-Entwicklung ein:

1. Öffnen Sie Visual Studio, und wählen Sie im Menü **Datei** die Option **Neu** > **Projekt**.

2. Erweitern Sie im Dialogfeld **Neues Projekt** in der Liste **Vorlagen** den Knoten **Visual C#**, und wählen Sie **.NET Core** aus. Es werden drei neue Projektvorlagen für **Klassenbibliothek (.NET Core)**, **Konsolenanwendung (.NET Core)** und **ASP.NET Core-Webanwendung (.NET Core)** angezeigt.

<a name="a-solution-using-only-net-core-projects"></a>Eine Projektmappe nur mit .NET Core-Projekten
----------------------------------------

### <a name="writing-the-library"></a>Schreiben der Bibliothek

1. Klicken Sie in Visual Studio auf **Datei** > **Neu** > **Projekt**. Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#**. Wählen Sie den Knoten **.NET Core** und anschließend den Knoten **Klassenbibliothek (.NET Core)** aus. 

2. Geben Sie dem Projekt den Namen „Library“ und der Projektmappe den Namen „Golden“. Lassen Sie **Projektmappenverzeichnis erstellen** aktiviert. Klicken Sie auf **OK**.

3. Öffnen Sie im Projektmappen-Explorer das Kontextmenü für den Knoten **Verweise**, und wählen Sie **NuGet-Pakete verwalten** aus.

4. Wählen Sie „nuget.org“ als **Paketquelle** aus, und klicken Sie auf die Registerkarte **Durchsuchen**. Suchen Sie nach **Newtonsoft.Json**. Klicken Sie auf **Installieren**. 

5. Öffnen Sie das Kontextmenü des Knotens **Verweise**, und wählen Sie **Pakete wiederherstellen** aus.

6. Benennen Sie die Datei `Class1.cs` in `Thing.cs` um. Akzeptieren Sie die Umbenennung der Klasse. Entfernen Sie den Konstruktor, und fügen Sie eine Methode hinzu: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`

7. Wählen Sie im Menü **Erstellen** die Option **Projektmappe erstellen**.

   Die Projektmappe wird fehlerfrei erstellt.

### <a name="writing-the-test-project"></a>Schreiben des Testprojekts

1. Öffnen Sie im Projektmappen-Explorer das Kontextmenü des Knotens **Projektmappe**, und wählen Sie die Option **Hinzufügen** > **Neuer Projektmappenordner** aus. Geben Sie dem Ordner den Namen „test“. 
   Dies ist lediglich ein Projektmappenordner, kein physischer Ordner.

2. Öffnen Sie das Kontextmenü des Ordners **test**, und wählen Sie **Hinzufügen** > **Neues Projekt** aus. Wählen Sie im Dialogfeld **Neues Projekt** die Option **Konsolenanwendung (.NET Core)** aus. Geben Sie dem Projekt den Namen „Testbibliothek“, und speichern Sie sie ausdrücklich im Verzeichnis `Golden\test`. 

> [!IMPORTANT]
> Bei dem Projekt muss es sich um eine Konsolenanwendung, nicht um eine Klassenbibliothek handeln.

3. Öffnen Sie im Projekt **Testbibliothek** das Kontextmenü des Knotens **Verweise**, und wählen Sie **Verweis hinzufügen** aus. 

4. Aktivieren Sie im Dialogfeld **Verweis-Manager** die Option **Bibliothek** unter **Projekte** im Knoten **Projektmappe**, und klicken Sie auf **OK**. 

5. Öffnen Sie im Projekt **Testbibliothek** die Datei `project.json`, und ersetzen Sie `"Library": "1.0.0-*"` durch `"Library": {"target": "project", "version": "1.0.0-*"}`. 

   Damit wird vermieden, dass das Projekt `Library` in ein NuGet-Paket mit demselben Namen aufgelöst wird. Wenn Sie für das Ziel ausdrücklich „project“ festlegen, wird zuerst nach einem Projekt mit diesem Namen und nicht nach einem Paket gesucht. 
   
6. Öffnen Sie im Projekt **Testbibliothek** das Kontextmenü des Knotens **Verweise**, und wählen Sie **Pakete wiederherstellen** aus.

7. Öffnen Sie das Kontextmenü des Knotens **Verweise**, und wählen Sie **NuGet-Pakete verwalten** aus.

8. Wählen Sie „nuget.org“ als **Paketquelle** aus, und klicken Sie auf die Registerkarte **Durchsuchen**. Aktivieren Sie das Kontrollkästchen **Vorabversion einbeziehen**, suchen Sie nach **xUnit** Version 2.2.0 oder höher, und klicken Sie anschließend auf **Installieren**. 

9. Suchen Sie nach **dotnet-test-xunit** Version 2.2.0 oder höher, und klicken Sie auf **Installieren**.

10. Bearbeiten Sie `project.json`, und ersetzen Sie `"imports": "dnxcore50"` durch `"imports": [ "dnxcore50", "portable-net45+win8" ]`. 

   Auf diese Weise können xUnit-Bibliotheken ordnungsgemäß wiederhergestellt, und vom Projekt verwendet werden: Diese Bibliotheken wurden so kompiliert, dass sie mit portierbaren Profilen verwendet werden können, die „portable-net45+win8“ enthalten, nicht jedoch .NET Core, das es noch nicht gab, als diese erstellt wurden. `import` vereinfacht die Toolversionsprüfungen beim Erstellen. Nun können Pakete fehlerfrei wiederhergestellt werden.

11. Bearbeiten Sie `project.json`, um `"testRunner": "xunit",` nach dem Abschnitt `"frameworks"` hinzuzufügen.

12. Fügen Sie zum Projekt **Testbibliothek** eine `LibraryTests.cs`-Klassendatei hinzu, fügen Sie am Anfang der Datei die `using`-Anweisungen `using Xunit;` und `using Library;` hinzu, und fügen Sie anschließend den folgenden Code zur Klasse hinzu:
    ```csharp
    [Fact]
    public void ThingGetsObjectValFromNumber() {
        Assert.Equal(42, new Thing().Get(42));
    }
    ```
    * Optional können Sie die Datei `Program.cs` im Projekt **Testbibliothek** löschen und `"buildOptions": {"emitEntryPoint": true},` in `project.json` entfernen.

   Sie sollten nun die Projektmappe erstellen können. 
   
13. Wählen Sie im Menü **Test** die Option **Windows** > **Test-Explorer** und anschließend im Test-Explorer die Option **Alle ausführen** aus.
   
   Der Test sollte erfolgreich verlaufen.

### <a name="writing-the-console-app"></a>Schreiben der Konsolenanwendung

1. Öffnen Sie im Projektmappen-Explorer das Kontextmenü für den Ordner `src`, und fügen Sie ein neues Projekt vom Typ **Konsolenanwendung (.NET Core)** hinzu. Geben Sie ihm den Namen „App“, und legen Sie `Golden\src` als Speicherort fest.

2. Öffnen Sie im Projekt **App** das Kontextmenü des Knotens **Verweise**, und wählen Sie **Hinzufügen** > **Verweis** aus. 

3. Aktivieren Sie im Dialogfeld **Verweis-Manager** die Option **Bibliothek** unter **Projekte** im Knoten **Projektmappe**, und klicken Sie auf **OK**.

4. Öffnen Sie im Projekt **App** die Datei `project.json`, und ersetzen Sie `"Library": "1.0.0-*"` durch `"Library": {"target": "project"}`.

5. Öffnen Sie das Kontextmenü des Knotens **Verweise**, und wählen Sie **Pakete wiederherstellen** aus.

6. Öffnen Sie das Kontextmenü für den Knoten **App**, und wählen Sie **Als Startprojekt festlegen** aus.

7. Öffnen Sie die Datei `Program.cs`, fügen Sie am Anfang der Datei eine `using Library;`-Anweisung und anschließend `Console.WriteLine($"The answer is {new Thing().Get(42)}");` zur `Main`-Methode hinzu.

8. Legen Sie am Ende der hinzugefügten Zeile einen Haltepunkt fest.

9. Drücken Sie F5, um die Anwendung auszuführen.

   Die Anwendung sollte ohne Fehler erstellt werden, und Sie sollten beim Haltepunkt ankommen. Darüber hinaus sollten Sie prüfen können, ob die Ausgabe der Anwendung „42“ lautet.

<a name="a-mixed-net-core-library-and-net-framework-application"></a>Eine gemischte Anwendung von .NET Core-Bibliothek und .NET Framework
--------------------------------------------------------

Führen Sie beginnend mit der aus dem vorherigen Skript erhaltenen Projektmappe die folgenden Schritte aus:

1. Öffnen Sie im Projektmappen-Explorer die Datei `project.json` für das Projekt **Bibliothek**, und ersetzen Sie `"frameworks": {
    "netstandard1.6" }` durch `"frameworks": {
    "netstandard1.4" }`.

2. Öffnen Sie im Projekt **Bibliothek** das Kontextmenü des Knotens **Verweise**, und wählen Sie **Pakete wiederherstellen** aus.

   Die Projektmappe sollte weiterhin wie gehabt erstellt werden und genauso funktionieren: Der Test sollte erfolgreich verlaufen, und die Konsolenanwendung sollte ausgeführt werden können und debugfähig sein.

3. Öffnen Sie im Projekt **Bibliothek** das Kontextmenü, und wählen Sie **Erstellen** aus.

4. Öffnen Sie im Projektmappen-Explorer das Kontextmenü für den Ordner `src`, und wählen Sie **Hinzufügen** >  **Neues Projekt** aus.

5. Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend **Konsolenanwendung** aus.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie eine standardmäßige Konsolenanwendung und nicht die .NET Core-Version verwenden. In diesem Abschnitt nutzen Sie die Bibliothek aus einer .NET Framework-Anwendung.

6. Geben Sie dem Projekt den Namen „FxApp“, und legen Sie für den Speicherort `Golden\src` fest.

7. Öffnen Sie im Projekt **FxApp** das Kontextmenü des Knotens **Verweise**, und wählen Sie **Verweis hinzufügen** aus.

8. Wählen Sie im Dialogfeld **Verweis-Manager** die Option **Durchsuchen** aus, wechseln Sie zum Verzeichnis des Builds `Library.dll` (im Pfad ..Golden\src\Library\bin\Debug\netstandard1.4), und klicken Sie auf **Hinzufügen**. 

   Eine andere Möglichkeit, auf .NET Core-Code aus dem .NET Framework zu verweisen, besteht darin, die Bibliothek zu packen und auf das Paket zu verweisen.

9. Öffnen Sie das Kontextmenü des Knotens **Verweise**, und wählen Sie **NuGet-Pakete verwalten** aus.

10. Wählen Sie „nuget.org“ als **Paketquelle** aus, und klicken Sie auf die Registerkarte **Durchsuchen**. Aktivieren Sie das Kontrollkästchen **Vorabversion einbeziehen**, und suchen Sie nach **Newtonsoft.Json**. Klicken Sie auf **Installieren**. 

11. Öffnen Sie im Projekt **FxApp** die Datei `Program.cs`, und fügen Sie am Anfang der Datei die Anweisung `using Library;`, und anschließend `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` zur `Main`-Methode des Programms hinzu.

12. Legen Sie am Ende der hinzugefügten Zeile einen Haltepunkt fest.

13. Legen Sie **FxApp** als Startanwendung für die Projektmappe fest.

14. Drücken Sie F5, um die App auszuführen.

   Die Anwendung sollte erstellt werden und beim Haltepunkt ankommen. Die Ausgabe der Anwendung sollte „42“ lauten.
   
   > [!TIP]
   > Auf einer Windows-Plattform können Sie MSTest verwenden. Weitere Informationen finden Sie im Dokument [Verwenden von MSTest unter Windows](../testing/using-mstest-on-windows.md).

<a name="moving-a-library-from-netstandard-14-to-13"></a>Wechsel einer Bibliothek von Netstandard 1.4 zu 1.3
--------------------------------------------

1. Öffnen Sie im Projektmappen-Explorer die Datei `project.json` für das Projekt **Bibliothek**.

2. Ersetzen Sie `frameworks": { "netstandard1.4" }` durch `frameworks": { "netstandard1.3" }`.

3. Öffnen Sie im Projekt **Bibliothek** das Kontextmenü des Knotens **Verweise**, und wählen Sie **Pakete wiederherstellen** aus.

4. Wählen Sie im Menü **Erstellen** die Option **Bibliothek erstellen**.

5. Entfernen Sie den Verweis `Library` aus dem Projekt **FxApp**, und fügen Sie ihn zum Pfad ..Golden\src\Library\bin\Debug\netstandard1.3 hinzu. Damit wird nun auf Version 1.3 verwiesen.

6. Drücken Sie F5, um die Anwendung auszuführen.

   Alles sollte weiterhin wie gehabt funktionieren. Überprüfen Sie, ob die Ausgabe der Anwendung „42“ lautet, ob der Haltepunkt erreicht wurde und ob die Variablen geprüft werden können.

<a name="a-mixed-pcl-library-and-net-framework-application"></a>Eine gemischte Anwendung von PCL-Bibliothek und .NET Framework
--------------------------------------------------

Falls die vorherige Projektmappe geöffnet ist, schließen Sie sie. In diesem Abschnitt beginnen Sie mit einem neuen Skript.

### <a name="writing-the-library"></a>Schreiben der Bibliothek

1. Klicken Sie in Visual Studio auf **Datei** > **Neu** > **Projekt**. Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#**, und wählen Sie **Klassenbibliothek (portierbar für iOS, Android und Windows)** aus. 

2. Geben Sie dem Projekt den Namen „PCLLibrary“ und der Projektmappe den Namen „GoldenPCL“. Lassen Sie **Projektmappenverzeichnis erstellen** aktiviert. Klicken Sie auf **OK**.

3. Öffnen Sie im Projektmappen-Explorer das Kontextmenü für den Knoten **Verweise**, und wählen Sie **NuGet-Pakete verwalten** aus.

4. Wählen Sie „nuget.org“ als **Paketquelle** aus, und klicken Sie auf die Registerkarte **Durchsuchen**. Aktivieren Sie das Kontrollkästchen **Vorabversion einbeziehen**, und suchen Sie nach **Newtonsoft.Json**. Klicken Sie auf **Installieren**. 

5. Benennen Sie die Klasse in „Thing“ um, und fügen Sie eine Methode hinzu: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`

6. Wählen Sie im Menü **Erstellen** die Option **Projektmappe erstellen** aus, und prüfen Sie, ob die Projektmappe erstellt wird.

### <a name="writing-the-console-app"></a>Schreiben der Konsolenanwendung

1. Öffnen Sie im Projektmappen-Explorer das Kontextmenü des Knotens **Projektmappe 'GoldenPCL'**, und wählen Sie die Option **Hinzufügen** >  **Neues Projekt** aus. Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#**, wählen Sie die Option **Konsolenanwendung** aus, und geben Sie dem Projekt den Namen „App“. 

2. Öffnen Sie im Projekt **App** das Kontextmenü des Knotens **Verweise**, und wählen Sie **Hinzufügen** > **Verweis** aus. 

3. Wählen Sie im Dialogfeld **Verweis-Manager** die Option **Durchsuchen** aus, wechseln Sie zum Verzeichnis des Builds `PCLLibrary.dll` (im Pfad ..GoldenPCL\PCLLibrary\bin\Debug), und klicken Sie auf **Hinzufügen**. 

4. Öffnen Sie im Projekt **App** die Datei `Program.cs`, und fügen Sie am Anfang der Datei die Anweisung `using PCLLibrary;` und anschließend `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` zur `Main`-Methode des Programms hinzu.

5. Legen Sie am Ende der hinzugefügten Zeile einen Haltepunkt fest.

6. Öffnen Sie im Projektmappen-Explorer das Kontextmenü für den Knoten **App**, und wählen Sie **Als Startprojekt festlegen** aus.

7. Drücken Sie F5, um die App auszuführen.

   Die Anwendung sollte erstellt werden, ausgeführt werden und nach der Ausgabe von „42“ den Haltepunkt erreichen.

<a name="moving-a-pcl-to-a-netstandard-library"></a>Wechsel von einer portablen Klassenbibliothek zu einer NetStandard-Bibliothek
-------------------------------------
Das Tool für portable Klassenbibliotheken kann Ihre portable Klassenbibliothek automatisch an .NET Standard anpassen. 

1.  Doppelklicken Sie auf den Knoten „Eigenschaften“, um die Seite „Projekteigenschaften“ zu öffnen.

2.  Klicken Sie unter dem „Zielheader“ auf den Hyperlink „Ziel: .NET-Plattform (Standard)“.

3.  Klicken Sie auf „Ja“, wenn Sie zur Bestätigung aufgefordert werden.

Das Tool wählt automatisch die Version von .NET Standard aus, die alle von Ihrer portablen Klassenbibliothek ursprünglich als Ziel verwendeten Ziele enthält. Über das Dropdownmenü „.NET Standard“ auf der Seite „Projekteigenschaften“ können Sie auch eine andere Version von .NET Standard auswählen.
 
* Wenn Sie zuvor „packages.config“ verwendet haben, werden Sie möglicherweise aufgefordert, vor der Konvertierung alle installierten Pakete zu deinstallieren.

### <a name="manually-edit-projectjson-to-target-net-standard-from-an-existing-portable-class-library"></a>Bearbeiten Sie „project.json“ so, dass .NET Standard aus einer vorhandenen portablen Klassenbibliothek als Ziel verwendet wird.

1.  Wenn „project.json“ im „supports“-Element „dnxcore50“ enthält, entfernen Sie es.

2.  Entfernen Sie die Abhängigkeit von „Microsoft.NETCore“.

3.  Ändern Sie die Abhängigkeit von „Microsoft.NETCore.Portable.Compatibility“ Version „1.0.0“ in Version „1.0.1“.

4.  Fügen Sie eine Abhängigkeit von „NETStandard.Library“ Version „1.6.0“ hinzu.

5.  Entfernen Sie im „frameworks“-Element das „dotnet“-Framework (und das darin enthaltene „imports“-Element).

6.  Fügen Sie ` "netstandard1.x” : { } ` zum „frameworks“-Element hinzu. Ersetzen Sie dabei x durch die Version von .NET Standard, die Sie als Ziel verwenden möchten.

### <a name="example-projectjson"></a>Beispiel für „project.json“

Diese „project.json“-Datei enthält „supports“-Klauseln für UWP und .NET 4.6 und verwendet Netstandard 1.3 als Ziel:
```
{
  "supports": {
    "net46.app": {},
    "uwp.10.0.app": {},
  },
  "dependencies": {
    "NETStandard.Library": "1.6.0",
    "Microsoft.NETCore.Portable.Compatibility": "1.0.1"
  },
  "frameworks": {
    "netstandard1.3" : {}
  }
}
```





<!--HONumber=Nov16_HO1-->


