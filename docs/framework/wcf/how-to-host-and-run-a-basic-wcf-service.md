---
title: 'Tutorial: Hosten und Ausführen eines grundlegenden Windows Communication Foundation Diensts'
description: Erfahren Sie, wie Sie einen WCF-Dienst in einer Konsolenanwendung als Teil einer Reihe von Artikeln hosten können, die Ihnen beim Einstieg in die Erstellung einer WCF-Anwendung helfen.
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 5318991087e71430523681d601d3b38c4513027b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246128"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="cd97c-103">Tutorial: Hosten und Ausführen eines grundlegenden Windows Communication Foundation Diensts</span><span class="sxs-lookup"><span data-stu-id="cd97c-103">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="cd97c-104">In diesem Tutorial wird die dritte von fünf Aufgaben beschrieben, die zum Erstellen einer Basic Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cd97c-104">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="cd97c-105">Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Einstieg in Windows Communication Foundation Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="cd97c-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="cd97c-106">Die nächste Aufgabe zum Erstellen einer WCF-Anwendung besteht darin, einen WCF-Dienst in einer Konsolenanwendung zu hosten.</span><span class="sxs-lookup"><span data-stu-id="cd97c-106">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="cd97c-107">Ein WCF-Dienst macht einen oder mehrere *Endpunkte*verfügbar, von denen jeder einen oder mehrere Dienst Vorgänge verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="cd97c-107">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="cd97c-108">Ein Dienst Endpunkt gibt die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="cd97c-108">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="cd97c-109">Eine Adresse, an der Sie den Dienst finden können.</span><span class="sxs-lookup"><span data-stu-id="cd97c-109">An address where you can find the service.</span></span>
- <span data-ttu-id="cd97c-110">Eine Bindung, die die Informationen enthält, die beschreiben, wie ein Client mit dem Dienst kommunizieren muss.</span><span class="sxs-lookup"><span data-stu-id="cd97c-110">A binding that contains the information that describes how a client must communicate with the service.</span></span>
- <span data-ttu-id="cd97c-111">Ein Vertrag, der die Funktionalität definiert, die der Dienst für seine Clients bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="cd97c-111">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="cd97c-112">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="cd97c-112">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="cd97c-113">Erstellen und konfigurieren Sie ein Konsolen-App-Projekt zum Hosting eines WCF-Diensts.</span><span class="sxs-lookup"><span data-stu-id="cd97c-113">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="cd97c-114">Hinzufügen von Code zum Hosten des WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="cd97c-114">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="cd97c-115">Aktualisieren Sie die Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="cd97c-115">Update the configuration file.</span></span>
> - <span data-ttu-id="cd97c-116">Starten Sie den WCF-Dienst, und prüfen Sie, ob er ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="cd97c-116">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="cd97c-117">Erstellen und Konfigurieren eines Konsolen-App-Projekts zum Hosting des Diensts</span><span class="sxs-lookup"><span data-stu-id="cd97c-117">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="cd97c-118">Erstellen eines Konsolen-App-Projekts in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="cd97c-118">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="cd97c-119">Wählen Sie im Menü **Datei** die **Open**Option  >  **Projekt/Projekt** Mappe öffnen aus, und navigieren Sie zur zuvor erstellten Lösung **GettingStarted** (*GettingStarted. sln*).</span><span class="sxs-lookup"><span data-stu-id="cd97c-119">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="cd97c-120">Wählen Sie **Open**(Öffnen).</span><span class="sxs-lookup"><span data-stu-id="cd97c-120">Select **Open**.</span></span>

    2. <span data-ttu-id="cd97c-121">Wählen Sie im Menü **Ansicht** die Option **Projektmappen-Explorer**aus.</span><span class="sxs-lookup"><span data-stu-id="cd97c-121">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="cd97c-122">Wählen Sie im Fenster **Projektmappen-Explorer** die Lösung **GettingStarted** (oberer Knoten) aus, und klicken Sie dann im Kontextmenü auf **Add**  >  **Neues Projekt** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cd97c-122">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="cd97c-123">Wählen Sie im Fenster **Neues Projekt hinzufügen** auf der linken Seite unter **Visual c#** die Kategorie **Windows-Desktop** aus, oder **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="cd97c-123">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="cd97c-124">Wählen Sie die Vorlage **Konsolen-app (.NET Framework)** aus, und geben Sie als **Name den Namen** *gettingstartedhost* ein.</span><span class="sxs-lookup"><span data-stu-id="cd97c-124">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="cd97c-125">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd97c-125">Select **OK**.</span></span>

2. <span data-ttu-id="cd97c-126">Fügen Sie dem **gettingstartedlib** -Projekt einen Verweis im **gettingstartedhost** -Projekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="cd97c-126">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span>

    1. <span data-ttu-id="cd97c-127">Wählen Sie im Fenster **Projektmappen-Explorer** den Ordner **Verweise** unter dem **gettingstartedhost** -Projekt aus, und klicken Sie dann im Kontextmenü auf **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="cd97c-127">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="cd97c-128">**Wählen Sie**im Dialogfeld **Verweis hinzufügen** unter Projekte auf der linken Seite des Fensters **Projekt** Mappe aus.</span><span class="sxs-lookup"><span data-stu-id="cd97c-128">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span>

    3. <span data-ttu-id="cd97c-129">Wählen Sie im mittleren Bereich des Fensters **gettingstartedlib** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd97c-129">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span>

       <span data-ttu-id="cd97c-130">Durch diese Aktion werden die Typen, die im **gettingstartedlib** -Projekt definiert sind, für das **gettingstartedhost** -Projekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cd97c-130">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="cd97c-131">Fügen Sie der Assembly einen Verweis im **gettingstartedhost** -Projekt hinzu <xref:System.ServiceModel> :</span><span class="sxs-lookup"><span data-stu-id="cd97c-131">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="cd97c-132">Wählen Sie im Fenster **Projektmappen-Explorer** den Ordner **Verweise** unter dem **gettingstartedhost** -Projekt aus, und klicken Sie dann im Kontextmenü auf **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="cd97c-132">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="cd97c-133">Wählen Sie im Fenster **Verweis hinzufügen** unter Assemblys auf der linken Seite des Fensters **Framework** **aus.**</span><span class="sxs-lookup"><span data-stu-id="cd97c-133">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="cd97c-134">Wählen Sie **System. Service Model**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd97c-134">Select **System.ServiceModel**, and then select **OK**.</span></span>

    4. <span data-ttu-id="cd97c-135">Speichern Sie die Projekt Mappe, indem Sie **Datei**  >  **Alle speichern**auswählen.</span><span class="sxs-lookup"><span data-stu-id="cd97c-135">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="cd97c-136">Hinzufügen von Code zum Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="cd97c-136">Add code to host the service</span></span>

<span data-ttu-id="cd97c-137">Um den Dienst zu hosten, fügen Sie Code hinzu, um die folgenden Schritte auszuführen:</span><span class="sxs-lookup"><span data-stu-id="cd97c-137">To host the service, you add code to do the following steps:</span></span>

1. <span data-ttu-id="cd97c-138">Erstellen Sie einen URI für die Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="cd97c-138">Create a URI for the base address.</span></span>
2. <span data-ttu-id="cd97c-139">Erstellen Sie eine Klasseninstanz für das Hosting des Diensts.</span><span class="sxs-lookup"><span data-stu-id="cd97c-139">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="cd97c-140">Erstellen Sie einen Dienst Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="cd97c-140">Create a service endpoint.</span></span>
4. <span data-ttu-id="cd97c-141">Aktivieren des Metadatenaustauschs</span><span class="sxs-lookup"><span data-stu-id="cd97c-141">Enable metadata exchange.</span></span>
5. <span data-ttu-id="cd97c-142">Öffnen Sie den Dienst Host, um auf eingehende Nachrichten zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="cd97c-142">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="cd97c-143">Nehmen Sie die folgenden Änderungen am Code vor:</span><span class="sxs-lookup"><span data-stu-id="cd97c-143">Make the following changes to the code:</span></span>

1. <span data-ttu-id="cd97c-144">Öffnen Sie die Datei **Program.cs** oder **Module1. vb** im **gettingstartedhost** -Projekt, und ersetzen Sie den Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="cd97c-144">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using GettingStartedLib;

    namespace GettingStartedHost
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb);

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
                    selfHost.Close();
                }
                catch (CommunicationException ce)
                {
                    Console.WriteLine("An exception occurred: {0}", ce.Message);
                    selfHost.Abort();
                }
            }
        }
    }
    ```

    ```vb
    Imports System.ServiceModel
    Imports System.ServiceModel.Description
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```

    <span data-ttu-id="cd97c-145">Informationen dazu, wie dieser Code funktioniert, finden Sie unter [Service Hosting Program Steps](#service-hosting-program-steps).</span><span class="sxs-lookup"><span data-stu-id="cd97c-145">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="cd97c-146">Aktualisieren Sie die Projekteigenschaften:</span><span class="sxs-lookup"><span data-stu-id="cd97c-146">Update the project properties:</span></span>

   1. <span data-ttu-id="cd97c-147">Wählen Sie im Fenster **Projektmappen-Explorer** den Ordner **gettingstartedhost** aus, und klicken Sie dann im Kontextmenü auf **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="cd97c-147">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="cd97c-148">Wählen Sie auf der Eigenschaften Seite von **gettingstartedhost** die Registerkarte **Anwendung** aus:</span><span class="sxs-lookup"><span data-stu-id="cd97c-148">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="cd97c-149">Wählen Sie für c#-Projekte in der Liste **Start Objekt** den Befehl **gettingstartedhost. Program** aus.</span><span class="sxs-lookup"><span data-stu-id="cd97c-149">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="cd97c-150">Wählen Sie für Visual Basic Projekte in der Liste **Start Objekt** den Typ **Service. Program** aus.</span><span class="sxs-lookup"><span data-stu-id="cd97c-150">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="cd97c-151">Wählen Sie im Menü **Datei** die Option **Alle speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="cd97c-151">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="cd97c-152">Überprüfen, ob der Dienst funktioniert</span><span class="sxs-lookup"><span data-stu-id="cd97c-152">Verify the service is working</span></span>

1. <span data-ttu-id="cd97c-153">Erstellen Sie die Projekt Mappe, und führen Sie dann die **gettingstartedhost** -Konsolenanwendung in Visual Studio aus.</span><span class="sxs-lookup"><span data-stu-id="cd97c-153">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span>

    <span data-ttu-id="cd97c-154">Der Dienst muss mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cd97c-154">The service must be run with administrator privileges.</span></span> <span data-ttu-id="cd97c-155">Da Sie Visual Studio mit Administratorrechten geöffnet haben, wird die Anwendung beim Ausführen von **gettingstartedhost** in Visual Studio ebenfalls mit Administratorrechten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cd97c-155">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="cd97c-156">Als Alternative können Sie eine neue Eingabeaufforderung als Administrator öffnen (Wählen Sie im Kontextmenü **mehr**  >  **als Administrator ausführen** aus), und führen Sie **GettingStartedHost.exe** darin aus.</span><span class="sxs-lookup"><span data-stu-id="cd97c-156">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="cd97c-157">Öffnen Sie einen Webbrowser, und navigieren Sie zur Seite des Diensts unter `http://localhost:8000/GettingStarted/CalculatorService` .</span><span class="sxs-lookup"><span data-stu-id="cd97c-157">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cd97c-158">Dienste wie diese benötigen die richtige Berechtigung zum Registrieren von HTTP-Adressen auf dem Computer für die Überwachung.</span><span class="sxs-lookup"><span data-stu-id="cd97c-158">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="cd97c-159">Administratorkonten verfügen über diese Berechtigung, anderen Konten muss jedoch die Berechtigung für HTTP-Namespaces erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="cd97c-159">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="cd97c-160">Weitere Informationen zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS (Konfigurieren von HTTP und HTTPS)](feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="cd97c-160">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span>

## <a name="service-hosting-program-steps"></a><span data-ttu-id="cd97c-161">Schritte zum Dienst Hostingprogramm</span><span class="sxs-lookup"><span data-stu-id="cd97c-161">Service hosting program steps</span></span>

<span data-ttu-id="cd97c-162">Die Schritte im Code, den Sie zum Hosten des Diensts hinzugefügt haben, werden wie folgt beschrieben:</span><span class="sxs-lookup"><span data-stu-id="cd97c-162">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="cd97c-163">**Schritt 1**: Erstellen Sie eine Instanz der- `Uri` Klasse, die die Basisadresse des dienstanweises enthält.</span><span class="sxs-lookup"><span data-stu-id="cd97c-163">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="cd97c-164">Eine URL, die eine Basisadresse enthält, verfügt über einen optionalen URI, der einen Dienst identifiziert.</span><span class="sxs-lookup"><span data-stu-id="cd97c-164">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="cd97c-165">Die Basisadresse wird wie folgt formatiert: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>` .</span><span class="sxs-lookup"><span data-stu-id="cd97c-165">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="cd97c-166">Die Basisadresse für den Rechner Dienst verwendet den HTTP-Transport, localhost, Port 8000 und das URI-Segment "GettingStarted".</span><span class="sxs-lookup"><span data-stu-id="cd97c-166">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="cd97c-167">**Schritt 2**: Erstellen Sie eine Instanz der- <xref:System.ServiceModel.ServiceHost> Klasse, die Sie zum Hosten des Diensts verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd97c-167">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="cd97c-168">Der Konstruktor benötigt zwei Parameter: den Typ der Klasse, die den Dienstvertrag implementiert, und die Basisadresse des Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="cd97c-168">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="cd97c-169">**Schritt 3**: Erstellen Sie eine- <xref:System.ServiceModel.Description.ServiceEndpoint> Instanz.</span><span class="sxs-lookup"><span data-stu-id="cd97c-169">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="cd97c-170">Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen.</span><span class="sxs-lookup"><span data-stu-id="cd97c-170">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="cd97c-171">Der <xref:System.ServiceModel.Description.ServiceEndpoint> Konstruktor besteht aus dem Dienstvertragstyp, einer Bindung und einer Adresse.</span><span class="sxs-lookup"><span data-stu-id="cd97c-171">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="cd97c-172">Der Dienstvertrag ist `ICalculator`, den Sie definiert haben und im Diensttyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="cd97c-172">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="cd97c-173">Die Bindung für dieses Beispiel ist, bei der es sich um <xref:System.ServiceModel.WSHttpBinding> eine integrierte Bindung handelt und eine Verbindung mit Endpunkten herstellt, die den WS-\*-Spezifikationen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="cd97c-173">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="cd97c-174">Weitere Informationen zu WCF-Bindungen finden Sie unter [Übersicht über WCF-Bindungen](bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cd97c-174">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="cd97c-175">Sie fügen die Adresse an die Basisadresse an, um den Endpunkt zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="cd97c-175">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="cd97c-176">Der Code gibt die Adresse als CalculatorService und die voll qualifizierte Adresse für den Endpunkt als an `http://localhost:8000/GettingStarted/CalculatorService` .</span><span class="sxs-lookup"><span data-stu-id="cd97c-176">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cd97c-177">Für .NET Framework Version 4 und höher ist das Hinzufügen eines Dienst Endpunkts optional.</span><span class="sxs-lookup"><span data-stu-id="cd97c-177">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="cd97c-178">Wenn Sie den Code oder die Konfiguration nicht hinzufügen, fügt WCF für diese Versionen einen Standard Endpunkt für jede Kombination aus Basisadresse und Vertrag hinzu, die vom Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="cd97c-178">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="cd97c-179">Weitere Informationen zu Standard Endpunkten finden Sie unter [Angeben einer Endpunkt Adresse](specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="cd97c-179">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="cd97c-180">Weitere Informationen zu Standard Endpunkten, Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="cd97c-180">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="cd97c-181">**Schritt 4**: Aktivieren Sie den Metadatenaustausch.</span><span class="sxs-lookup"><span data-stu-id="cd97c-181">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="cd97c-182">Clients verwenden den Metadatenaustausch zum Generieren von Proxys zum Aufrufen der Dienst Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="cd97c-182">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="cd97c-183">Um den Metadatenaustausch zu aktivieren, erstellen Sie eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior> -Instanz, legen Sie Ihre <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> -Eigenschaft auf fest `true` , und fügen Sie das-Objekt der-Auflistung `ServiceMetadataBehavior` der- <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> <xref:System.ServiceModel.ServiceHost> Instanz</span><span class="sxs-lookup"><span data-stu-id="cd97c-183">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="cd97c-184">**Schritt 5**: Öffnen <xref:System.ServiceModel.ServiceHost> Sie, um auf eingehende Nachrichten zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="cd97c-184">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="cd97c-185">Die Anwendung wartet darauf, dass Sie die **Eingabe**Taste drücken.</span><span class="sxs-lookup"><span data-stu-id="cd97c-185">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="cd97c-186">Nachdem die Anwendung instanziiert <xref:System.ServiceModel.ServiceHost> wurde, wird ein try/catch-Block ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cd97c-186">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="cd97c-187">Weitere Informationen zum sicheren Abfangen von Ausnahmen <xref:System.ServiceModel.ServiceHost> , die von ausgelöst werden, finden [Sie unter Verwenden von schließen und Abbrechen zum Freigeben von WCF-Client Ressourcen](samples/use-close-abort-release-wcf-client-resources.md).</span><span class="sxs-lookup"><span data-stu-id="cd97c-187">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd97c-188">Wenn Sie eine WCF-Dienst Bibliothek hinzufügen, wird Sie von Visual Studio für Sie gehostet, wenn Sie Sie durchstarten eines Dienst Hosts Debuggen.</span><span class="sxs-lookup"><span data-stu-id="cd97c-188">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="cd97c-189">Um Konflikte zu vermeiden, können Sie verhindern, dass Visual Studio die WCF-Dienst Bibliothek gehostet.</span><span class="sxs-lookup"><span data-stu-id="cd97c-189">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span>
>
> 1. <span data-ttu-id="cd97c-190">Wählen Sie das **gettingstartedlib** -Projekt in **Projektmappen-Explorer** aus, und wählen Sie im Kontextmenü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="cd97c-190">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="cd97c-191">Wählen Sie **WCF-Optionen** aus, und deaktivieren Sie **beim Debuggen eines anderen Projekts in derselben Projekt Mappe den WCF-Dienst Host starten**</span><span class="sxs-lookup"><span data-stu-id="cd97c-191">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cd97c-192">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cd97c-192">Next steps</span></span>

<span data-ttu-id="cd97c-193">In diesem Tutorial haben Sie Folgendes gelernt:</span><span class="sxs-lookup"><span data-stu-id="cd97c-193">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="cd97c-194">Erstellen und konfigurieren Sie ein Konsolen-App-Projekt zum Hosting eines WCF-Diensts.</span><span class="sxs-lookup"><span data-stu-id="cd97c-194">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="cd97c-195">Hinzufügen von Code zum Hosten des WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="cd97c-195">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="cd97c-196">Aktualisieren Sie die Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="cd97c-196">Update the configuration file.</span></span>
> - <span data-ttu-id="cd97c-197">Starten Sie den WCF-Dienst, und prüfen Sie, ob er ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="cd97c-197">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="cd97c-198">Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie einen WCF-Client erstellen.</span><span class="sxs-lookup"><span data-stu-id="cd97c-198">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cd97c-199">Tutorial: Erstellen eines WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="cd97c-199">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
