---
title: Verwenden von MSTest mit .NET Core unter Windows
description: Verwenden von MSTest mit .NET Core unter Windows mit Visual Studio 2015
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 08/18/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 94304cd742b63e77126bfa40651faa6974e58853
ms.lasthandoff: 03/03/2017

---

# <a name="unit-testing-with-mstest-and-net-core-on-windows-using-visual-studio-2015"></a>Unittests mit MSTest und .NET Core unter Windows mit Visual Studio 2015

Während xUnit bei Verwendung unterschiedlicher Plattformen möglicherweise besser geeignet ist, kann mit .NET Core unter Windows auch MSTest verwendet werden.

## <a name="prerequisites"></a>Erforderliche Komponenten

Befolgen Sie zum Erstellen des Bibliothekprojekts die Anweisungen unter [Erste Schritte mit .NET Core unter Windows](../tutorials/using-on-windows.md).

### <a name="writing-the-test-project-using-mstest"></a>Schreiben des Testprojekts mit MSTest

1. Öffnen Sie im Projektmappen-Explorer das Kontextmenü des Knotens **Projektmappe**, und wählen Sie die Option **Hinzufügen** > **Neuer Projektmappenordner** aus. Geben Sie dem Ordner den Namen „test“. 
   Dies ist lediglich ein Projektmappenordner, kein physischer Ordner.

2. Öffnen Sie das Kontextmenü des Ordners **test**, und wählen Sie **Hinzufügen** > **Neues Projekt** aus. Wählen Sie im Dialogfeld **Neues Projekt** die Option **Konsolenanwendung (.NET Core)** aus. Geben Sie dem Projekt den Namen „Testbibliothek“, und speichern Sie sie ausdrücklich im Verzeichnis `Golden\test`. 

   > [!IMPORTANT]
   > Bei dem Projekt muss es sich um eine Konsolenanwendung, nicht um eine Klassenbibliothek handeln.

3. Öffnen Sie im Projekt **Testbibliothek** das Kontextmenü des Knotens **Verweise**, und wählen Sie **Verweis hinzufügen** aus. 

4. Aktivieren Sie im Dialogfeld **Verweis-Manager** die Option **Bibliothek** unter **Projekte** im Knoten **Projektmappe**, und klicken Sie auf **OK**. 

5. Öffnen Sie im Projekt **Testbibliothek** die Datei `project.json`, und ersetzen Sie `"Library": "1.0.0-*"` durch `"Library": {"target": "project"}`. 

   Damit wird vermieden, dass das Projekt `Library` in ein NuGet-Paket mit demselben Namen aufgelöst wird. Wenn Sie für das Ziel ausdrücklich „project“ festlegen, wird zuerst nach einem Projekt mit diesem Namen und nicht nach einem Paket gesucht. 

6. Öffnen Sie das Kontextmenü des Knotens **Verweise**, und wählen Sie **NuGet-Pakete verwalten** aus.

7. Wählen Sie „nuget.org“ als **Paketquelle** aus, und klicken Sie auf die Registerkarte **Durchsuchen**. Aktivieren Sie das Kontrollkästchen **Vorabversion einbeziehen**, suchen Sie nach **MSTest.TestFramework** Version 1.0.1-Preview oder höher, und klicken Sie anschließend auf **Installieren**. 

8. Suchen Sie nach **dotnet-test-mstest** Version 1.1.1-Preview oder höher, und klicken Sie auf **Installieren**.

9. Bearbeiten Sie `project.json`, um `"testRunner": "mstest",` nach dem Abschnitt `"version"` hinzuzufügen.

10. Fügen Sie zum Projekt **Testbibliothek** eine `LibraryTests.cs`-Klassendatei hinzu, fügen Sie am Anfang der Datei die `using`-Anweisungen `Microsoft.VisualStudio.TestTools.UnitTesting;` und `using Library;` hinzu, und fügen Sie anschließend den folgenden Code zur Klasse hinzu:
    ```csharp
    [TestClass]
    public class LibraryTests
    {
        [TestMethod]
        public void ThingGetsObjectValFromNumber()
        {
            Assert.AreEqual(42, new Thing().Get(42));
        }
    }
    ```
    * Optional können Sie die Datei `Program.cs` im Projekt **Testbibliothek** löschen und `"buildOptions": {"emitEntryPoint": true},` in `project.json` entfernen.

   Sie sollten nun die Projektmappe erstellen können. 
   
11. Wählen Sie im Menü **Test** die Option **Windows** > **Test-Explorer** und anschließend im Test-Explorer die Option **Alle ausführen** aus.
   
   Der Test sollte erfolgreich verlaufen.

