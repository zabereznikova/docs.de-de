---
title: 'Tutorial: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 38fd9b89e2719be8ce4d33b1b50f68171d587369
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410094"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="f543c-102">Tutorial: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts</span><span class="sxs-lookup"><span data-stu-id="f543c-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="f543c-103">In diesem Tutorial wird beschrieben, die dritte von fünf Schritte zur Erstellung einer grundlegenden Windows Communication Foundation (WCF)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f543c-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="f543c-104">Eine Übersicht über die Lernprogramme, finden Sie unter [Lernprogramm: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="f543c-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="f543c-105">Die nächste Aufgabe zum Erstellen einer WCF-Anwendung wird zum Hosten eines WCF-Diensts in einer Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="f543c-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="f543c-106">Ein WCF-Dienst verfügbar macht, eine oder mehrere *Endpunkte*, von denen jeder macht eine oder mehrere Dienstvorgänge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f543c-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="f543c-107">Ein Dienstendpunkt gibt die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="f543c-107">A service endpoint specifies the following information:</span></span> 
- <span data-ttu-id="f543c-108">Eine Adresse, in dem Sie den Dienst finden können.</span><span class="sxs-lookup"><span data-stu-id="f543c-108">An address where you can find the service.</span></span>
- <span data-ttu-id="f543c-109">Eine Bindung, die Informationen enthält, die beschreibt, wie ein Client mit dem Dienst kommunizieren muss.</span><span class="sxs-lookup"><span data-stu-id="f543c-109">A binding that contains the information that describes how a client must communicate with the service.</span></span> 
- <span data-ttu-id="f543c-110">Ein Vertrag, der die Funktionalität definiert, die der Dienst seinen Clients bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f543c-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="f543c-111">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="f543c-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="f543c-112">Erstellen Sie und konfigurieren Sie ein Konsolenanwendungsprojekt für das Hosten eines WCF-Diensts.</span><span class="sxs-lookup"><span data-stu-id="f543c-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="f543c-113">Fügen Sie Code zum Hosten des WCF-Diensts.</span><span class="sxs-lookup"><span data-stu-id="f543c-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="f543c-114">Aktualisieren Sie die Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="f543c-114">Update the configuration file.</span></span>
> - <span data-ttu-id="f543c-115">Starten Sie den WCF-Dienst, und überprüfen Sie, ob er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f543c-115">Start the WCF service and verify it's running.</span></span>


## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="f543c-116">Erstellen Sie und konfigurieren Sie ein Konsolenanwendungsprojekt zum Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="f543c-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="f543c-117">Erstellen Sie ein Konsolenanwendungsprojekt in Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="f543c-117">Create a console app project in Visual Studio:</span></span> 
 
    1. <span data-ttu-id="f543c-118">Von der **Datei** , wählen Sie im Menü **öffnen** > **Projekt/Projektmappe** und navigieren Sie zu der **GettingStarted** Lösung Sie zuvor erstellt haben (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="f543c-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="f543c-119">Wählen Sie **öffnen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-119">Select **Open**.</span></span>

    2. <span data-ttu-id="f543c-120">Von der **Ansicht** , wählen Sie im Menü **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f543c-120">From the **View** menu, select **Solution Explorer**.</span></span>
    
    3. <span data-ttu-id="f543c-121">In der **Projektmappen-Explorer** wählen Sie im Fenster der **GettingStarted** -Lösung (obersten Knoten), und wählen Sie dann **hinzufügen** > **neues Projekt** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="f543c-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 

    4. <span data-ttu-id="f543c-122">In der **neues Projekt hinzufügen** Fenster auf der linken Seite auf die **Windows Desktop** unter Kategorie **Visual C#**  oder **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="f543c-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="f543c-123">Wählen Sie die **Konsolen-App ((.NET Framework)** Vorlage, und geben Sie *GettingStartedHost* für die **Namen**.</span><span class="sxs-lookup"><span data-stu-id="f543c-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="f543c-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f543c-124">Select **OK**.</span></span>

2. <span data-ttu-id="f543c-125">Fügen Sie einen Verweis in der **GettingStartedHost** Projekt die **GettingStartedLib** Projekt:</span><span class="sxs-lookup"><span data-stu-id="f543c-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span> 

    1. <span data-ttu-id="f543c-126">In der **Projektmappen-Explorer** wählen Sie im Fenster der **Verweise** Ordner unter dem **GettingStartedHost** Projekt, und wählen Sie dann **"Verweis hinzufügen"** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="f543c-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="f543c-127">In der **Verweis hinzufügen** Dialogfeld unter **Projekte** wählen Sie auf der linken Seite des Fensters **Lösung**.</span><span class="sxs-lookup"><span data-stu-id="f543c-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span> 
 
    3. <span data-ttu-id="f543c-128">Wählen Sie **GettingStartedLib** im mittleren Abschnitt des Fensters, und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="f543c-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span> 

       <span data-ttu-id="f543c-129">Dadurch wird die in definierten Typen der **GettingStartedLib** Projekt zur Verfügung, um die **GettingStartedHost** Projekt.</span><span class="sxs-lookup"><span data-stu-id="f543c-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="f543c-130">Fügen Sie einen Verweis in der **GettingStartedHost** Projekt die <xref:System.ServiceModel> Assembly:</span><span class="sxs-lookup"><span data-stu-id="f543c-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="f543c-131">In der **Projektmappen-Explorer** wählen Sie im Fenster der **Verweise** Ordner unter dem **GettingStartedHost** Projekt, und wählen Sie dann **"Verweis hinzufügen"** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="f543c-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>
    
    2. <span data-ttu-id="f543c-132">In der **Verweis hinzufügen** Fenster unter **Assemblys** wählen Sie auf der linken Seite des Fensters **Framework**.</span><span class="sxs-lookup"><span data-stu-id="f543c-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span> 

    3. <span data-ttu-id="f543c-133">Wählen Sie **System.ServiceModel**, und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="f543c-133">Select **System.ServiceModel**, and then select **OK**.</span></span> 
    
    4. <span data-ttu-id="f543c-134">Speichern Sie die Projektmappe durch Auswahl **Datei** > **Alles speichern**.</span><span class="sxs-lookup"><span data-stu-id="f543c-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="f543c-135">Fügen Sie Code zum Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="f543c-135">Add code to host the service</span></span>

<span data-ttu-id="f543c-136">Um den Dienst zu hosten, fügen Sie Code aus, um die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="f543c-136">To host the service, you add code to do the following steps:</span></span> 
   1. <span data-ttu-id="f543c-137">Erstellen Sie einen URI für die Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="f543c-137">Create a URI for the base address.</span></span>
   2. <span data-ttu-id="f543c-138">Erstellen Sie eine Klasseninstanz für den Dienst hostet.</span><span class="sxs-lookup"><span data-stu-id="f543c-138">Create a class instance for hosting the service.</span></span>
   3. <span data-ttu-id="f543c-139">Erstellen eines Dienstendpunkts.</span><span class="sxs-lookup"><span data-stu-id="f543c-139">Create a service endpoint.</span></span>
   4. <span data-ttu-id="f543c-140">Aktivieren des Metadatenaustauschs</span><span class="sxs-lookup"><span data-stu-id="f543c-140">Enable metadata exchange.</span></span>
   5. <span data-ttu-id="f543c-141">Öffnen Sie den Diensthost zum Lauschen auf eingehender Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f543c-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="f543c-142">Stellen Sie die folgenden Änderungen an den Code ein:</span><span class="sxs-lookup"><span data-stu-id="f543c-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="f543c-143">Öffnen der **"Program.cs"** oder **"Module1.vb"** Datei die **GettingStartedHost** Projekts, und Ersetzen Sie den Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="f543c-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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
    
    <span data-ttu-id="f543c-144">Informationen dazu, wie dieser Code funktioniert, finden Sie unter [-Dienst hosten der Anwendung, Schritte](#service-hosting-program-steps).</span><span class="sxs-lookup"><span data-stu-id="f543c-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>


2. <span data-ttu-id="f543c-145">Aktualisieren Sie die Projekteigenschaften an:</span><span class="sxs-lookup"><span data-stu-id="f543c-145">Update the project properties:</span></span>

   1. <span data-ttu-id="f543c-146">In der **Projektmappen-Explorer** wählen Sie im Fenster der **GettingStartedHost** Ordner, und wählen Sie dann **Eigenschaften** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="f543c-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="f543c-147">Auf der **GettingStartedHost** Seite "Eigenschaften", wählen die **Anwendung** Registerkarte:</span><span class="sxs-lookup"><span data-stu-id="f543c-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="f543c-148">Für C# -Projekten auf **GettingStartedHost.Program** aus der **Startobjekt** Liste.</span><span class="sxs-lookup"><span data-stu-id="f543c-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="f543c-149">Wählen Sie für Visual Basic-Projekten **Service.Program** aus der **Startobjekt** Liste.</span><span class="sxs-lookup"><span data-stu-id="f543c-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="f543c-150">Von der **Datei** , wählen Sie im Menü **Alles speichern**.</span><span class="sxs-lookup"><span data-stu-id="f543c-150">From the **File** menu, select **Save All**.</span></span>


## <a name="verify-the-service-is-working"></a><span data-ttu-id="f543c-151">Stellen Sie sicher, dass der Dienst funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f543c-151">Verify the service is working</span></span>

1. <span data-ttu-id="f543c-152">Erstellen Sie die Projektmappe, und führen Sie die **GettingStartedHost** Console Application "aus" in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f543c-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span> 

    <span data-ttu-id="f543c-153">Der Dienst muss mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f543c-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="f543c-154">Da Sie beim Ausführen von Visual Studio mit Administratorrechten geöffnet **GettingStartedHost** in Visual Studio mit Administratorrechten sowie die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f543c-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="f543c-155">Als Alternative können Sie eine neue Eingabeaufforderung als Administrator öffnen (Wählen Sie **weitere** > **als Administrator ausführen** aus dem Kontextmenü), und führen Sie **GettingStartedHost.exe**  darin.</span><span class="sxs-lookup"><span data-stu-id="f543c-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="f543c-156">Öffnen Sie einen Webbrowser und navigieren Sie zur Seite des Diensts `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="f543c-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>
   
   > [!NOTE]
   > <span data-ttu-id="f543c-157">Dienste wie dieser erfordern der erforderliche Berechtigung zum Registrieren von HTTP-Adressen auf dem Computer, für die Überwachung.</span><span class="sxs-lookup"><span data-stu-id="f543c-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="f543c-158">Administratorkonten verfügen über diese Berechtigung, anderen Konten muss jedoch die Berechtigung für HTTP-Namespaces erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="f543c-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="f543c-159">Weitere Informationen zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS (Konfigurieren von HTTP und HTTPS)](feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="f543c-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span> 


## <a name="service-hosting-program-steps"></a><span data-ttu-id="f543c-160">Service hosting Programm Schritte</span><span class="sxs-lookup"><span data-stu-id="f543c-160">Service hosting program steps</span></span>

<span data-ttu-id="f543c-161">Die Schritte in den Code, zum Hosten des Diensts werden beschrieben hinzufügen, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f543c-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="f543c-162">**Schritt 1**: Erstellen Sie eine Instanz von der `Uri` Klasse, die die Basisadresse des Diensts enthält.</span><span class="sxs-lookup"><span data-stu-id="f543c-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="f543c-163">Eine URL, eine Basisadresse enthält, verfügt über einen optionalen URI, der einen Dienst kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f543c-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="f543c-164">Die Basisadresse ist wie folgt formatiert: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span><span class="sxs-lookup"><span data-stu-id="f543c-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="f543c-165">Die Basisadresse für den rechnerdienst verwendet den HTTP-Transport, Localhost, Port 8000 und das URI-Segment, GettingStarted.</span><span class="sxs-lookup"><span data-stu-id="f543c-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="f543c-166">**Schritt 2**: Erstellen Sie eine Instanz von der <xref:System.ServiceModel.ServiceHost> -Klasse, die Sie verwenden, um den Dienst zu hosten.</span><span class="sxs-lookup"><span data-stu-id="f543c-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="f543c-167">Der Konstruktor akzeptiert zwei Parameter: den Typ der Klasse, die den Dienstvertrag und die Basisadresse des Diensts implementiert.</span><span class="sxs-lookup"><span data-stu-id="f543c-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="f543c-168">**Schritt 3**: Erstellen Sie eine <xref:System.ServiceModel.Description.ServiceEndpoint>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="f543c-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="f543c-169">Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen.</span><span class="sxs-lookup"><span data-stu-id="f543c-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="f543c-170">Die <xref:System.ServiceModel.Description.ServiceEndpoint> Konstruktor besteht aus den Schnittstellentyp des Dienstvertrags, eine Bindung und eine Adresse.</span><span class="sxs-lookup"><span data-stu-id="f543c-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="f543c-171">Der Dienstvertrag ist `ICalculator`, den Sie definiert haben und im Diensttyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="f543c-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="f543c-172">Die Bindung für dieses Beispiel ist <xref:System.ServiceModel.WSHttpBinding>, das ist eine integrierte Bindung und eine Verbindung mit Endpunkten, die die WS - entsprechen \* Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="f543c-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="f543c-173">Weitere Informationen zu WCF-Bindungen finden Sie unter [WCF-bindungsübersicht](bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f543c-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="f543c-174">Sie fügen die Adresse, an der Basisadresse, um den Endpunkt zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f543c-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="f543c-175">Der Code gibt die Adresse als CalculatorService und die vollqualifizierte Adresse für den Endpunkt als `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="f543c-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f543c-176">Für .NET Framework Version 4 und höher, ist das Hinzufügen eines Dienstendpunkts optional.</span><span class="sxs-lookup"><span data-stu-id="f543c-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="f543c-177">Wenn Sie nicht Ihr Code oder Konfiguration hinzufügen, fügt WCF für diesen Versionen ein Standardendpunkt für jede Kombination aus Basisadresse und vom Dienst implementierten Vertrag.</span><span class="sxs-lookup"><span data-stu-id="f543c-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="f543c-178">Weitere Informationen zu Standardendpunkten, finden Sie unter [angeben einer Endpunktadresse](specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="f543c-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="f543c-179">Weitere Informationen zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Dank vereinfachter Konfiguration](simplified-configuration.md) und [Dank vereinfachter Konfiguration für WCF-Dienste](samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f543c-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="f543c-180">**Schritt 4**: Aktivieren des Metadatenaustauschs</span><span class="sxs-lookup"><span data-stu-id="f543c-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="f543c-181">Clients verwenden Metadatenaustausch, um Proxys zu generieren, für die Dienstvorgänge aufruft.</span><span class="sxs-lookup"><span data-stu-id="f543c-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="f543c-182">Zum Aktivieren von Metadatenaustausch erstellen eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior> Instanz, legen die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> Eigenschaft `true`, und fügen die `ServiceMetadataBehavior` -Objekt der <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> Auflistung von der <xref:System.ServiceModel.ServiceHost> Instanz.</span><span class="sxs-lookup"><span data-stu-id="f543c-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="f543c-183">**Schritt 5**: Open <xref:System.ServiceModel.ServiceHost> zum Lauschen auf eingehender Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f543c-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="f543c-184">Die Anwendung wartet, bis Sie drücken **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="f543c-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="f543c-185">Nachdem die Anwendung instanziiert <xref:System.ServiceModel.ServiceHost>, es wird einen Try/Catch-Block ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f543c-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="f543c-186">Weitere Informationen zum sicheren Abfangen von Ausnahmen durch <xref:System.ServiceModel.ServiceHost>, finden Sie unter [verwenden schließen "und" Abort, um WCF-Client-Ressourcen freizugeben](samples/use-close-abort-release-wcf-client-resources.md).</span><span class="sxs-lookup"><span data-stu-id="f543c-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f543c-187">Wenn Sie eine WCF-Dienstbibliothek hinzufügen, hostet Visual Studio es für Sie, wenn Sie es Debuggen, indem Sie ein Diensthost ab.</span><span class="sxs-lookup"><span data-stu-id="f543c-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="f543c-188">Um Konflikte zu vermeiden, können Sie verhindern, dass Visual Studio Hosten von WCF-Dienstbibliothek.</span><span class="sxs-lookup"><span data-stu-id="f543c-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span> 
> 1. <span data-ttu-id="f543c-189">Wählen Sie die **GettingStartedLib** Projekt **Projektmappen-Explorer** , und wählen Sie **Eigenschaften** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="f543c-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="f543c-190">Wählen Sie **WCF-Optionen** , und deaktivieren Sie **starten WCF-Diensthost beim Debuggen von einem anderen Projekt in der gleichen Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="f543c-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>


## <a name="next-steps"></a><span data-ttu-id="f543c-191">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f543c-191">Next steps</span></span>

<span data-ttu-id="f543c-192">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="f543c-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="f543c-193">Erstellen Sie und konfigurieren Sie ein Konsolenanwendungsprojekt für das Hosten eines WCF-Diensts.</span><span class="sxs-lookup"><span data-stu-id="f543c-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="f543c-194">Fügen Sie Code zum Hosten des WCF-Diensts.</span><span class="sxs-lookup"><span data-stu-id="f543c-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="f543c-195">Aktualisieren Sie die Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="f543c-195">Update the configuration file.</span></span>
> - <span data-ttu-id="f543c-196">Starten Sie den WCF-Dienst, und überprüfen Sie, ob er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f543c-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="f543c-197">Fahren Sie fort mit dem nächsten Tutorial erfahren, wie beim Erstellen eines WCF-Clients.</span><span class="sxs-lookup"><span data-stu-id="f543c-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f543c-198">Tutorial: Erstellen Sie einen WCF-client</span><span class="sxs-lookup"><span data-stu-id="f543c-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
