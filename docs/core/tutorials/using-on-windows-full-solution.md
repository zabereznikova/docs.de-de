---
title: "Erstellen einer vollständigen .NET Core-Lösung unter Windows mit Visual Studio 2017"
description: "Erfahren Sie, wie Sie eine vollständige .NET Core-Projektmappe in Visual Studio 2017 unter Windows erstellen."
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ba7e082c-a7c8-431e-a342-f67734b660f6
ms.openlocfilehash: 694201c1a2a2c373f62b0e0d8e3c1d8aa7e6e881
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="building-a-complete-net-core-solution-on-windows-using-visual-studio-2017"></a><span data-ttu-id="890cc-104">Erstellen einer vollständigen .NET Core-Lösung unter Windows mit Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="890cc-104">Building a complete .NET Core solution on Windows, using Visual Studio 2017</span></span>

<span data-ttu-id="890cc-105">Visual Studio 2017 bietet eine umfassende Entwicklungsumgebung für die Entwicklung von .NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="890cc-105">Visual Studio 2017 provides a full-featured development environment for developing .NET Core applications.</span></span> <span data-ttu-id="890cc-106">Die Verfahren in diesem Dokument beschreiben die erforderlichen Schritte zum Erstellen einer herkömmlichen .NET Core-Lösung, die wiederverwendbare Bibliotheken, Tests und das Verwenden von Bibliotheken von Drittanbietern vorsieht.</span><span class="sxs-lookup"><span data-stu-id="890cc-106">The procedures in this document describe the steps necessary to build a typical .NET Core solution that includes reusable libraries, testing, and using third-party libraries.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="890cc-107">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="890cc-107">Prerequisites</span></span>

<span data-ttu-id="890cc-108">Befolgen Sie die Anweisungen auf [unserer Seite über erforderliche Komponenten](../windows-prerequisites.md), um Ihre Umgebung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="890cc-108">Follow the instructions on [our prerequisites page](../windows-prerequisites.md) to update your environment.</span></span>

## <a name="a-solution-using-only-net-core-projects"></a><span data-ttu-id="890cc-109">Eine Projektmappe nur mit .NET Core-Projekten</span><span class="sxs-lookup"><span data-stu-id="890cc-109">A solution using only .NET Core projects</span></span>

### <a name="writing-the-library"></a><span data-ttu-id="890cc-110">Schreiben der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="890cc-110">Writing the library</span></span>

1. <span data-ttu-id="890cc-111">Klicken Sie in Visual Studio auf **Datei** > **Neu** > **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="890cc-111">In Visual Studio, choose **File**, **New**, **Project**.</span></span> <span data-ttu-id="890cc-112">In der **neues Projekt** Dialogfeld erweitern Sie die **Visual C#-** Knoten, und wählen Sie die **.NET Standard** Knoten, und wählen Sie dann **-Klassenbibliothek (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="890cc-112">In the **New Project** dialog, expand the **Visual C#** node and choose the **.NET Standard** node, and then choose **Class Library (.NET Standard)**.</span></span> 

2. <span data-ttu-id="890cc-113">Geben Sie dem Projekt den Namen „Library“ und der Projektmappe den Namen „Golden“.</span><span class="sxs-lookup"><span data-stu-id="890cc-113">Name the project "Library" and the solution "Golden".</span></span> <span data-ttu-id="890cc-114">Lassen Sie **Projektmappenverzeichnis erstellen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="890cc-114">Leave **Create directory for solution** checked.</span></span> <span data-ttu-id="890cc-115">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="890cc-115">Click **OK**.</span></span>

3. <span data-ttu-id="890cc-116">Öffnen Sie im Projektmappen-Explorer das Kontextmenü für den Knoten **Abhängigkeiten**, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="890cc-116">In Solution Explorer, open the context menu for the **Dependencies** node and choose **Manage NuGet Packages**.</span></span>

4. <span data-ttu-id="890cc-117">Wählen Sie „nuget.org“ als **Paketquelle** aus, und klicken Sie auf die Registerkarte **Durchsuchen**. Suchen Sie nach **Newtonsoft.Json**.</span><span class="sxs-lookup"><span data-stu-id="890cc-117">Choose "nuget.org" as the **Package source**, and choose the **Browse** tab. Browse for **Newtonsoft.Json**.</span></span> <span data-ttu-id="890cc-118">Klicken Sie auf **Installieren**, und akzeptieren Sie die Lizenzbedingungen.</span><span class="sxs-lookup"><span data-stu-id="890cc-118">Click **Install**, and accept the license agreement.</span></span> <span data-ttu-id="890cc-119">Das Paket sollte jetzt unter **Abhängigkeiten/NuGet** angezeigt und automatisch wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="890cc-119">The package should now appear under **Dependencies/NuGet** and be automatically restored.</span></span>

5. <span data-ttu-id="890cc-120">Benennen Sie die Datei `Class1.cs` in `Thing.cs` um.</span><span class="sxs-lookup"><span data-stu-id="890cc-120">Rename the `Class1.cs` file to `Thing.cs`.</span></span> <span data-ttu-id="890cc-121">Akzeptieren Sie die Umbenennung der Klasse.</span><span class="sxs-lookup"><span data-stu-id="890cc-121">Accept the rename of the class.</span></span> <span data-ttu-id="890cc-122">Fügen Sie eine Methode hinzu: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span><span class="sxs-lookup"><span data-stu-id="890cc-122">Add a method: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span></span>

7. <span data-ttu-id="890cc-123">Wählen Sie im Menü **Erstellen** die Option **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="890cc-123">On the **Build** menu, choose **Build Solution**.</span></span>

   <span data-ttu-id="890cc-124">Die Projektmappe wird fehlerfrei erstellt.</span><span class="sxs-lookup"><span data-stu-id="890cc-124">The solution should build without error.</span></span>

### <a name="writing-the-test-project"></a><span data-ttu-id="890cc-125">Schreiben des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="890cc-125">Writing the test project</span></span>

1. <span data-ttu-id="890cc-126">Öffnen Sie in Projektmappen-Explorer das Kontextmenü des Knotens **Projektmappe**, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="890cc-126">In Solution Explorer, open the context menu for the **Solution** node and choose **Add**, **New Project**.</span></span> <span data-ttu-id="890cc-127">Wählen Sie im Dialogfeld **Neues Projekt** unter **Visual C#/.NET Core** die Option **Komponententestprojekt (.NET Core)** aus.</span><span class="sxs-lookup"><span data-stu-id="890cc-127">In the **New Project** dialog, under **Visual C# / .NET Core**, choose **Unit Test Project (.NET Core)**.</span></span> <span data-ttu-id="890cc-128">Nennen Sie sie „Testbibliothek“, und klicken Sie auf „OK“.</span><span class="sxs-lookup"><span data-stu-id="890cc-128">Name it "TestLibrary" and click OK.</span></span> 

2. <span data-ttu-id="890cc-129">Öffnen Sie im Projekt **Testbibliothek** das Kontextmenü des Knotens **Abhängigkeiten**, und wählen Sie **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="890cc-129">In the **TestLibrary** project, open the context menu for the **Dependencies** node and choose **Add Reference**.</span></span> <span data-ttu-id="890cc-130">Klicken Sie auf **Projekte**, überprüfen Sie das Projekt „Bibliothek“, und klicken Sie auf „OK“.</span><span class="sxs-lookup"><span data-stu-id="890cc-130">Click **Projects**, then check the Library project and click OK.</span></span> <span data-ttu-id="890cc-131">Dadurch wird einen Verweis auf die Bibliothek aus dem Testprojekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="890cc-131">This adds a reference to your library from the test project.</span></span>

3. <span data-ttu-id="890cc-132">Benennen Sie die Datei `UnitTest1.cs` in `LibraryTests.cs` um, und übernehmen Sie die Klassenumbenennung.</span><span class="sxs-lookup"><span data-stu-id="890cc-132">Rename the `UnitTest1.cs` file to `LibraryTests.cs` and accept the class rename.</span></span> <span data-ttu-id="890cc-133">Fügen Sie oben in der Datei `using Library;` hinzu, und ersetzen Sie die `TestMethod1`-Methode durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="890cc-133">Add `using Library;` to the top of the file, and replace the `TestMethod1` method with the following code:</span></span>
    ```csharp
    [TestMethod]
    public void ThingGetsObjectValFromNumber()
    {
        Assert.AreEqual(42, new Thing().Get(42));
    }
    ```

   <span data-ttu-id="890cc-134">Sie sollten nun die Projektmappe erstellen können.</span><span class="sxs-lookup"><span data-stu-id="890cc-134">You should now be able to build the solution.</span></span> 
   
4. <span data-ttu-id="890cc-135">Wählen Sie im Menü **Testen** zunächst **Windows** und dann **Test-Explorer** aus, um das Test-Explorer-Fenster in Ihrem Arbeitsbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="890cc-135">On the **Test** menu, choose **Windows**, **Test Explorer** in order to get the test explorer window into your workspace.</span></span> <span data-ttu-id="890cc-136">Nach wenigen Sekunden sollte der Test `ThingGetsObjectValFromNumber` im Test-Explorer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="890cc-136">After a few seconds, the `ThingGetsObjectValFromNumber` test should appear in the test explorer.</span></span> <span data-ttu-id="890cc-137">Wählen Sie **Alle ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="890cc-137">Choose **Run All**.</span></span>
   
   <span data-ttu-id="890cc-138">Der Test sollte erfolgreich verlaufen.</span><span class="sxs-lookup"><span data-stu-id="890cc-138">The test should pass.</span></span>

### <a name="writing-the-console-app"></a><span data-ttu-id="890cc-139">Schreiben der Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="890cc-139">Writing the console app</span></span>

1. <span data-ttu-id="890cc-140">Öffnen Sie im Projektmappen-Explorer das Kontextmenü für die Projektmappe, und fügen Sie ein neues Projekt des Typs **Konsolen-App (.NET Core)** hinzu.</span><span class="sxs-lookup"><span data-stu-id="890cc-140">In Solution Explorer, open the context menu for the solution, and add a new **Console App (.NET Core)** project.</span></span> <span data-ttu-id="890cc-141">Nennen Sie es „App“.</span><span class="sxs-lookup"><span data-stu-id="890cc-141">Name it "App".</span></span>

2. <span data-ttu-id="890cc-142">Öffnen Sie im Projekt **App** das Kontextmenü des Knotens **Abhängigkeiten**, und wählen Sie **Hinzufügen** > **Verweis** aus.</span><span class="sxs-lookup"><span data-stu-id="890cc-142">In the **App** project, open the context menu for the **Dependencies** node and choose **Add**,  **Reference**.</span></span> 

3. <span data-ttu-id="890cc-143">Aktivieren Sie im Dialogfeld **Verweis-Manager** die Option **Bibliothek** unter **Projekte** im Knoten **Projektmappe**, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="890cc-143">In the **Reference Manager** dialog, check **Library** under the **Projects**, **Solution** node, and then click **OK**</span></span>

6. <span data-ttu-id="890cc-144">Öffnen Sie das Kontextmenü für den Knoten **App**, und wählen Sie **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="890cc-144">Open the context menu for the **App** node and choose **Set as StartUp Project**.</span></span> <span data-ttu-id="890cc-145">Dadurch wird sichergestellt, dass bei Drücken von F5 oder STRG+F5 die Konsolen-App gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="890cc-145">This ensures that hitting F5 or CTRL+F5 will start the console app.</span></span>

7. <span data-ttu-id="890cc-146">Öffnen Sie die Datei `Program.cs`, fügen Sie am Anfang der Datei eine `using Library;`-Anweisung und anschließend `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` zur `Main`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="890cc-146">Open the `Program.cs` file, add a `using Library;` directive to the top of the file, and then add `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` to the `Main` method.</span></span>

8. <span data-ttu-id="890cc-147">Legen Sie am Ende der hinzugefügten Zeile einen Haltepunkt fest.</span><span class="sxs-lookup"><span data-stu-id="890cc-147">Set a breakpoint after the line that you just added.</span></span>

9. <span data-ttu-id="890cc-148">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="890cc-148">Press F5 to run the application..</span></span>

   <span data-ttu-id="890cc-149">Die Anwendung sollte ohne Fehler erstellt werden, und Sie sollten beim Haltepunkt ankommen.</span><span class="sxs-lookup"><span data-stu-id="890cc-149">The application should build without error, and should hit the breakpoint.</span></span> <span data-ttu-id="890cc-150">Darüber hinaus sollten Sie prüfen können, ob die Ausgabe der Anwendung „42“ lautet.</span><span class="sxs-lookup"><span data-stu-id="890cc-150">You should also be able to check that the application output "The answer is 42.".</span></span>
