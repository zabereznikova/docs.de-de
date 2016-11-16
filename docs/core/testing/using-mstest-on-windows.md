---
title: Verwenden von MSTest mit .NET Core unter Windows
description: Verwenden von MSTest mit .NET Core unter Windows mit Visual Studio 2015
keywords: MSTest, .NET, .NET Core
author: ncarandini
manager: wpickett
ms.date: 08/18/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
translationtype: Human Translation
ms.sourcegitcommit: 6795f1ace77e6f4d1b2fe07e6281f4acb6d21271
ms.openlocfilehash: c9d6bb1d45b9a6cb88334050669a4c064e53d54e

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



<!--HONumber=Nov16_HO1-->


