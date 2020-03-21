---
title: 'Tutorial: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Dienstes'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 30eb86987b83427b94c6fff22755cde3d73dd9f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184085"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="f9298-102">Tutorial: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Dienstes</span><span class="sxs-lookup"><span data-stu-id="f9298-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="f9298-103">In diesem Tutorial wird die dritte von fünf Aufgaben beschrieben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f9298-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="f9298-104">Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="f9298-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="f9298-105">Die nächste Aufgabe zum Erstellen einer WCF-Anwendung besteht darin, einen WCF-Dienst in einer Konsolenanwendung zu hosten.</span><span class="sxs-lookup"><span data-stu-id="f9298-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="f9298-106">Ein WCF-Dienst macht einen oder mehrere *Endpunkte*verfügbar, von denen jeder einen oder mehrere Dienstvorgänge verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="f9298-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="f9298-107">Ein Dienstendpunkt gibt die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="f9298-107">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="f9298-108">Eine Adresse, an der Sie den Dienst finden können.</span><span class="sxs-lookup"><span data-stu-id="f9298-108">An address where you can find the service.</span></span>
- <span data-ttu-id="f9298-109">Eine Bindung, die die Informationen enthält, die beschreiben, wie ein Client mit dem Dienst kommunizieren muss.</span><span class="sxs-lookup"><span data-stu-id="f9298-109">A binding that contains the information that describes how a client must communicate with the service.</span></span>
- <span data-ttu-id="f9298-110">Ein Vertrag, der die Funktionalität definiert, die der Dienst seinen Clients bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f9298-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="f9298-111">In diesem Tutorial lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f9298-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f9298-112">Erstellen und konfigurieren Sie ein Konsolen-App-Projekt zum Hosten eines WCF-Dienstes.</span><span class="sxs-lookup"><span data-stu-id="f9298-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="f9298-113">Fügen Sie Code zum Hosten des WCF-Dienstes hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9298-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="f9298-114">Aktualisieren Sie die Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f9298-114">Update the configuration file.</span></span>
> - <span data-ttu-id="f9298-115">Starten Sie den WCF-Dienst, und überprüfen Sie, ob er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f9298-115">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="f9298-116">Erstellen und Konfigurieren eines Konsolen-App-Projekts zum Hosten des Dienstes</span><span class="sxs-lookup"><span data-stu-id="f9298-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="f9298-117">Erstellen eines Konsolen-App-Projekts in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="f9298-117">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="f9298-118">Wählen Sie im Menü **Datei** die Option**Projekt/Projektmappe** **öffnen** > aus, und navigieren Sie zur **Lösung "Erste Schritte",** die Sie zuvor erstellt haben (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="f9298-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="f9298-119">Wählen Sie **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-119">Select **Open**.</span></span>

    2. <span data-ttu-id="f9298-120">Wählen Sie im Menü **Ansicht** **den Projektmappen-Explorer**aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-120">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="f9298-121">Wählen Sie im **Projektmappen-Explorer** die **Lösung "Erste Schritte"** (oberster Knoten) und dann im Kontextmenü **"Neues Projekt hinzufügen"** **aus.** > </span><span class="sxs-lookup"><span data-stu-id="f9298-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="f9298-122">Wählen Sie im Fenster **Neues Projekt hinzufügen** auf der linken Seite die Windows **Desktop-Kategorie** unter Visual **C oder** Visual **Basic**aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="f9298-123">Wählen Sie die Vorlage **"Konsolen-App" (.NET Framework)** aus, und geben Sie *GettingStartedHost* für den **Namen**ein.</span><span class="sxs-lookup"><span data-stu-id="f9298-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="f9298-124">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-124">Select **OK**.</span></span>

2. <span data-ttu-id="f9298-125">Fügen Sie dem **GettingStartedLib-Projekt** einen Verweis im **GettingStartedHost-Projekt** hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9298-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span>

    1. <span data-ttu-id="f9298-126">Wählen Sie im **Projektmappen-Explorer** den Ordner **Referenzen** unter dem **Projekt GettingStartedHost** aus, und wählen Sie dann im Kontextmenü **Referenz hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="f9298-127">Wählen Sie im Dialogfeld **Referenz hinzufügen** unter **Projekte** auf der linken Seite des Fensters die Option **Projektmappe**aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span>

    3. <span data-ttu-id="f9298-128">Wählen Sie **GettingStartedLib** im mittleren Bereich des Fensters aus, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span>

       <span data-ttu-id="f9298-129">Mit dieser Aktion werden die im **GettingStartedLib-Projekt** definierten Typen für das **GettingStartedHost-Projekt** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f9298-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="f9298-130">Fügen Sie der <xref:System.ServiceModel> Assembly einen Verweis im **GettingStartedHost-Projekt** hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9298-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="f9298-131">Wählen Sie im **Projektmappen-Explorer** den Ordner **Referenzen** unter dem **Projekt GettingStartedHost** aus, und wählen Sie dann im Kontextmenü **Referenz hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="f9298-132">Wählen Sie im Fenster **Referenz hinzufügen** unter **Baugruppen** auf der linken Seite des Fensters **Framework**aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="f9298-133">Wählen Sie **System.ServiceModel**aus , und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-133">Select **System.ServiceModel**, and then select **OK**.</span></span>

    4. <span data-ttu-id="f9298-134">Speichern Sie die Lösung, indem Sie **Datei** > **speichern alle**auswählen.</span><span class="sxs-lookup"><span data-stu-id="f9298-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="f9298-135">Hinzufügen von Code zum Hosten des Dienstes</span><span class="sxs-lookup"><span data-stu-id="f9298-135">Add code to host the service</span></span>

<span data-ttu-id="f9298-136">Um den Dienst zu hosten, fügen Sie Code hinzu, um die folgenden Schritte auszuführen:</span><span class="sxs-lookup"><span data-stu-id="f9298-136">To host the service, you add code to do the following steps:</span></span>

1. <span data-ttu-id="f9298-137">Erstellen Sie einen URI für die Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="f9298-137">Create a URI for the base address.</span></span>
2. <span data-ttu-id="f9298-138">Erstellen Sie eine Klasseninstanz zum Hosten des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="f9298-138">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="f9298-139">Erstellen Sie einen Dienstendpunkt.</span><span class="sxs-lookup"><span data-stu-id="f9298-139">Create a service endpoint.</span></span>
4. <span data-ttu-id="f9298-140">Aktivieren des Metadatenaustauschs</span><span class="sxs-lookup"><span data-stu-id="f9298-140">Enable metadata exchange.</span></span>
5. <span data-ttu-id="f9298-141">Öffnen Sie den Diensthost, um eingehende Nachrichten zu hören.</span><span class="sxs-lookup"><span data-stu-id="f9298-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="f9298-142">Nehmen Sie die folgenden Änderungen am Code vor:</span><span class="sxs-lookup"><span data-stu-id="f9298-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="f9298-143">Öffnen Sie die **Datei Program.cs** oder **Module1.vb** im **GettingStartedHost-Projekt,** und ersetzen Sie den Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="f9298-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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
                    selfHost.Description.Behaviors.Add(smb)    ;

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

    <span data-ttu-id="f9298-144">Informationen zur Funktionsweise dieses Codes finden Sie unter [Servicehostingprogrammschritte](#service-hosting-program-steps).</span><span class="sxs-lookup"><span data-stu-id="f9298-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="f9298-145">Aktualisieren der Projekteigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f9298-145">Update the project properties:</span></span>

   1. <span data-ttu-id="f9298-146">Wählen Sie im **Projektmappen-Explorer-Fenster** den Ordner **GettingStartedHost** aus, und wählen Sie dann **Eigenschaften** im Kontextmenü aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="f9298-147">Wählen Sie auf der Seite **GettingStartedHost-Eigenschaften** die Registerkarte **Anwendung** aus:</span><span class="sxs-lookup"><span data-stu-id="f9298-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="f9298-148">Wählen Sie für C-Projekte aus der Liste des **Startobjekts** die Option **GettingStartedHost.Program** aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="f9298-149">Wählen Sie für Visual Basic-Projekte **Service.Program** aus der Liste **Startobjekt** aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="f9298-150">Wählen Sie im Menü **Datei** die Option **Alle speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-150">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="f9298-151">Überprüfen, ob der Dienst funktioniert</span><span class="sxs-lookup"><span data-stu-id="f9298-151">Verify the service is working</span></span>

1. <span data-ttu-id="f9298-152">Erstellen Sie die Lösung, und führen Sie dann die **GetStartedHost-Konsolenanwendung** in Visual Studio aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span>

    <span data-ttu-id="f9298-153">Der Dienst muss mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f9298-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="f9298-154">Da Sie Visual Studio mit Administratorrechten geöffnet haben, wird die Anwendung beim Ausführen von **GettingStartedHost** in Visual Studio ebenfalls mit Administratorrechten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f9298-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="f9298-155">Alternativ können Sie eine neue Eingabeaufforderung als Administrator öffnen (im Kontextmenü **mehr** > **ausführen als Administrator** auswählen) und **GettingStartedHost.exe** darin ausführen.</span><span class="sxs-lookup"><span data-stu-id="f9298-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="f9298-156">Öffnen Sie einen Webbrowser, und navigieren `http://localhost:8000/GettingStarted/CalculatorService`Sie zur Seite des Dienstes unter .</span><span class="sxs-lookup"><span data-stu-id="f9298-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f9298-157">Dienste wie dieser benötigen die entsprechende Berechtigung zum Registrieren von HTTP-Adressen auf dem Computer zum Abhören.</span><span class="sxs-lookup"><span data-stu-id="f9298-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="f9298-158">Administratorkonten verfügen über diese Berechtigung, anderen Konten muss jedoch die Berechtigung für HTTP-Namespaces erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="f9298-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="f9298-159">Weitere Informationen zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS (Konfigurieren von HTTP und HTTPS)](feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="f9298-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span>

## <a name="service-hosting-program-steps"></a><span data-ttu-id="f9298-160">Diensthostingprogrammschritte</span><span class="sxs-lookup"><span data-stu-id="f9298-160">Service hosting program steps</span></span>

<span data-ttu-id="f9298-161">Die Schritte im Code, den Sie dem Host des Dienstes hinzugefügt haben, werden wie folgt beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f9298-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="f9298-162">**Schritt 1**: Erstellen `Uri` Sie eine Instanz der Klasse, die die Basisadresse des Dienstes enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="f9298-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="f9298-163">Eine URL, die eine Basisadresse enthält, verfügt über einen optionalen URI, der einen Dienst identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f9298-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="f9298-164">Die Basisadresse ist wie `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`folgt formatiert: .</span><span class="sxs-lookup"><span data-stu-id="f9298-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="f9298-165">Die Basisadresse für den Rechnerdienst verwendet den HTTP-Transport, localhost, Port 8000 und das URI-Segment " Erste Schritte".</span><span class="sxs-lookup"><span data-stu-id="f9298-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="f9298-166">**Schritt 2**: Erstellen <xref:System.ServiceModel.ServiceHost> Sie eine Instanz der Klasse, die Sie zum Hosten des Dienstes verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9298-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="f9298-167">Der Konstruktor verwendet zwei Parameter: den Typ der Klasse, die den Servicevertrag implementiert, und die Basisadresse des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="f9298-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="f9298-168">**Schritt 3**: <xref:System.ServiceModel.Description.ServiceEndpoint> Erstellen Sie eine Instanz.</span><span class="sxs-lookup"><span data-stu-id="f9298-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="f9298-169">Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen.</span><span class="sxs-lookup"><span data-stu-id="f9298-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="f9298-170">Der <xref:System.ServiceModel.Description.ServiceEndpoint> Konstruktor besteht aus dem Dienstvertragsschnittstellentyp, einer Bindung und einer Adresse.</span><span class="sxs-lookup"><span data-stu-id="f9298-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="f9298-171">Der Dienstvertrag ist `ICalculator`, den Sie definiert haben und im Diensttyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="f9298-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="f9298-172">Die Bindung für <xref:System.ServiceModel.WSHttpBinding>dieses Beispiel ist , die eine integrierte Bindung ist und eine Verbindung mit Endpunkten herstellt, die den WS-\*-Spezifikationen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f9298-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="f9298-173">Weitere Informationen zu WCF-Bindungen finden Sie unter Übersicht über [WCF-Bindungen](bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f9298-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="f9298-174">Sie fügen die Adresse an die Basisadresse an, um den Endpunkt zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f9298-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="f9298-175">Der Code gibt die Adresse als CalculatorService und die `http://localhost:8000/GettingStarted/CalculatorService`vollqualifizierte Adresse für den Endpunkt als an.</span><span class="sxs-lookup"><span data-stu-id="f9298-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f9298-176">Für .NET Framework Version 4 und höher ist das Hinzufügen eines Dienstendpunkts optional.</span><span class="sxs-lookup"><span data-stu-id="f9298-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="f9298-177">Wenn Sie für diese Versionen keinen Code oder keine Konfiguration hinzufügen, fügt WCF für jede Kombination aus Basisadresse und Vertrag, die vom Dienst implementiert wird, einen Standardendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9298-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="f9298-178">Weitere Informationen zu Standardendpunkten finden Sie unter [Angeben einer Endpunktadresse](specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="f9298-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="f9298-179">Weitere Informationen zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Vereinfachte Konfiguration](simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f9298-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="f9298-180">**Schritt 4**: Aktivieren des Metadatenaustauschs.</span><span class="sxs-lookup"><span data-stu-id="f9298-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="f9298-181">Clients verwenden Metadatenaustausch, um Proxys zum Aufrufen der Dienstvorgänge zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f9298-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="f9298-182">Um den Metadatenaustausch <xref:System.ServiceModel.Description.ServiceMetadataBehavior> zu aktivieren, <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> erstellen `true`Sie eine `ServiceMetadataBehavior` Instanz, <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> legen <xref:System.ServiceModel.ServiceHost> Sie ihre Eigenschaft auf , und fügen Sie das Objekt der Auflistung der Instanz hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9298-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="f9298-183">**Schritt 5** <xref:System.ServiceModel.ServiceHost> : Öffnen Sie, um eingehende Nachrichten zu hören.</span><span class="sxs-lookup"><span data-stu-id="f9298-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="f9298-184">Die Anwendung wartet darauf, dass Sie **die Eingabetaste**drücken.</span><span class="sxs-lookup"><span data-stu-id="f9298-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="f9298-185">Nachdem die Anwendung instanziiert <xref:System.ServiceModel.ServiceHost>hat, führt sie einen try/catch-Block aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="f9298-186">Weitere Informationen zum sicheren Abfangen <xref:System.ServiceModel.ServiceHost>von Ausnahmen, die von ausgelöst werden, finden Sie unter [Verwenden von Schließen und Abbrechen zum Freigeben von WCF-Clientressourcen](samples/use-close-abort-release-wcf-client-resources.md).</span><span class="sxs-lookup"><span data-stu-id="f9298-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9298-187">Wenn Sie eine WCF-Dienstbibliothek hinzufügen, hostet Visual Studio sie für Sie, wenn Sie sie durch Starten eines Diensthosts debuggen.</span><span class="sxs-lookup"><span data-stu-id="f9298-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="f9298-188">Um Konflikte zu vermeiden, können Sie verhindern, dass Visual Studio die WCF-Dienstbibliothek hostet.</span><span class="sxs-lookup"><span data-stu-id="f9298-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span>
>
> 1. <span data-ttu-id="f9298-189">Wählen Sie das **Projekt GettingStartedLib** im **Projektmappen-Explorer** aus, und wählen Sie **Eigenschaften** im Kontextmenü aus.</span><span class="sxs-lookup"><span data-stu-id="f9298-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="f9298-190">Wählen Sie **WCF-Optionen aus,** und deaktivieren Sie **WCF-Diensthost starten, wenn Sie ein anderes Projekt in derselben Projektmappe debuggen.**</span><span class="sxs-lookup"><span data-stu-id="f9298-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f9298-191">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f9298-191">Next steps</span></span>

<span data-ttu-id="f9298-192">In diesem Tutorial haben Sie Folgendes gelernt:</span><span class="sxs-lookup"><span data-stu-id="f9298-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f9298-193">Erstellen und konfigurieren Sie ein Konsolen-App-Projekt zum Hosten eines WCF-Dienstes.</span><span class="sxs-lookup"><span data-stu-id="f9298-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="f9298-194">Fügen Sie Code zum Hosten des WCF-Dienstes hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9298-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="f9298-195">Aktualisieren Sie die Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f9298-195">Update the configuration file.</span></span>
> - <span data-ttu-id="f9298-196">Starten Sie den WCF-Dienst, und überprüfen Sie, ob er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f9298-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="f9298-197">Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie einen WCF-Client erstellen.</span><span class="sxs-lookup"><span data-stu-id="f9298-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f9298-198">Tutorial: Erstellen eines WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="f9298-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
