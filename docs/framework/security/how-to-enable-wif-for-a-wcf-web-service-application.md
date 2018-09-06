---
title: 'Gewusst wie: Aktivieren von WIF für eine WCF-Webdienstanwendung'
ms.date: 03/30/2017
ms.assetid: bfc64b3d-64e9-4093-a6a4-72e933917af7
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 71897299d68c2f0e43def8e70730ea456d6e9e24
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43739489"
---
# <a name="how-to-enable-wif-for-a-wcf-web-service-application"></a><span data-ttu-id="9d6c9-102">Gewusst wie: Aktivieren von WIF für eine WCF-Webdienstanwendung</span><span class="sxs-lookup"><span data-stu-id="9d6c9-102">How To: Enable WIF for a WCF Web Service Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="9d6c9-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="9d6c9-103">Applies To</span></span>  
  
-   <span data-ttu-id="9d6c9-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="9d6c9-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="9d6c9-105">Microsoft® Windows® Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="9d6c9-105">Microsoft® Windows® Communication Foundation (WCF)</span></span>  
  
## <a name="summary"></a><span data-ttu-id="9d6c9-106">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="9d6c9-106">Summary</span></span>  
 <span data-ttu-id="9d6c9-107">In dieser Vorgehensweise werden ausführliche schrittweise Prozeduren zum Aktivieren von WIF in einem WCF-Webdienst vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-107">This How-To provides detailed step-by-step procedures for enabling WIF in a WCF web service.</span></span> <span data-ttu-id="9d6c9-108">Sie enthält auch Anweisungen für Tests der Anwendung, mit denen überprüft werden kann, ob der Webdienst Ansprüche ordnungsgemäß darstellt, wenn die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-108">It also provides instructions for how to test the application to verify that the web service is correctly presenting claims when the application is run.</span></span> <span data-ttu-id="9d6c9-109">Diese Vorgehensweise enthält keine ausführlichen Anweisungen zum Erstellen eines Sicherheitstokendiensts (STS). Stattdessen wird der Entwicklungs-STS verwendet, der aus dem Identitäts- und Zugriffstool stammt.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="9d6c9-110">Der Entwicklungs-STS führt keine echte Authentifizierung durch und ist nur für Testzwecke vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="9d6c9-111">Sie müssen das Identitäts- und Zugriffs-Tool installieren, um diese Vorgehensweise nachzuvollziehen.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="9d6c9-112">Es kann auf der folgenden Seite heruntergeladen werden: [Identity and Access Tool (Identitäts- und Zugriffstool)](https://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="9d6c9-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="9d6c9-113">Inhalt</span><span class="sxs-lookup"><span data-stu-id="9d6c9-113">Contents</span></span>  
  
-   <span data-ttu-id="9d6c9-114">Ziele</span><span class="sxs-lookup"><span data-stu-id="9d6c9-114">Objectives</span></span>  
  
-   <span data-ttu-id="9d6c9-115">Übersicht</span><span class="sxs-lookup"><span data-stu-id="9d6c9-115">Overview</span></span>  
  
-   <span data-ttu-id="9d6c9-116">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="9d6c9-116">Summary of Steps</span></span>  
  
-   <span data-ttu-id="9d6c9-117">Schritt 1 – Erstellen eines einfachen WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="9d6c9-117">Step 1 – Create a Simple WCF Service</span></span>  
  
-   <span data-ttu-id="9d6c9-118">Schritt 2 – Erstellen einer Clientanwendung für den WCF-Dienst</span><span class="sxs-lookup"><span data-stu-id="9d6c9-118">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
-   <span data-ttu-id="9d6c9-119">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="9d6c9-119">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="9d6c9-120">Ziele</span><span class="sxs-lookup"><span data-stu-id="9d6c9-120">Objectives</span></span>  
  
-   <span data-ttu-id="9d6c9-121">Erstellen eines WCF-Diensts, für den Token ausgestellt werden müssen</span><span class="sxs-lookup"><span data-stu-id="9d6c9-121">Create a WCF service that requires issued tokens</span></span>  
  
-   <span data-ttu-id="9d6c9-122">Erstellen eines WCF-Clients, für den ein Token aus einem STS erforderlich ist, der an den WCF-Dienst weitergeleitet wird</span><span class="sxs-lookup"><span data-stu-id="9d6c9-122">Create a WCF client that requests a token from an STS and passes it to the WCF service</span></span>  
  
## <a name="overview"></a><span data-ttu-id="9d6c9-123">Übersicht</span><span class="sxs-lookup"><span data-stu-id="9d6c9-123">Overview</span></span>  
 <span data-ttu-id="9d6c9-124">In dieser Vorgehensweise wird veranschaulicht, wie ein Entwickler Verbundauthentifizierung bei der Entwicklung eines WCF-Diensts verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-124">This How-To is intended to demonstrate how a developer can use federated authentication when developing WCF services.</span></span> <span data-ttu-id="9d6c9-125">Die Verwendung eines Verbunds in WCF-Diensten hat folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="9d6c9-125">Some of the benefits of using federation in WCF services include:</span></span>  
  
1.  <span data-ttu-id="9d6c9-126">Ausklammern der Authentifizierungslogik aus dem WCF-Dienstcode</span><span class="sxs-lookup"><span data-stu-id="9d6c9-126">Factoring authentication logic out of WCF service code</span></span>  
  
2.  <span data-ttu-id="9d6c9-127">Wiederverwenden vorhandener Projektmappen für die Identitätsverwaltung</span><span class="sxs-lookup"><span data-stu-id="9d6c9-127">Re-using existing identity management solutions</span></span>  
  
3.  <span data-ttu-id="9d6c9-128">Interoperabilität mit anderen Identitätsprojektmappen</span><span class="sxs-lookup"><span data-stu-id="9d6c9-128">Interoperability with other identity solutions</span></span>  
  
4.  <span data-ttu-id="9d6c9-129">Flexibilität und Agilität für zukünftige Änderungen</span><span class="sxs-lookup"><span data-stu-id="9d6c9-129">Flexibility and resilience to future changes</span></span>  
  
 <span data-ttu-id="9d6c9-130">Mit WIF und dem zugeordneten Identitäts- und Zugriffs-Tool kann ein WCF-Dienst einfacher mit Verbundauthentifizierung entwickelt und getestet werden. Die ist in den folgenden Schritten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-130">WIF and the associated Identity and Access tool make it easier to develop and test a WCF service using federated authentication, as the following steps demonstrate.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="9d6c9-131">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="9d6c9-131">Summary of Steps</span></span>  
  
-   <span data-ttu-id="9d6c9-132">Schritt 1 – Erstellen eines einfachen WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="9d6c9-132">Step 1 – Create a Simple WCF Service</span></span>  
  
-   <span data-ttu-id="9d6c9-133">Schritt 2 – Erstellen einer Clientanwendung für den WCF-Dienst</span><span class="sxs-lookup"><span data-stu-id="9d6c9-133">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
-   <span data-ttu-id="9d6c9-134">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="9d6c9-134">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-wcf-service"></a><span data-ttu-id="9d6c9-135">Schritt 1 – Erstellen eines einfachen WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="9d6c9-135">Step 1 – Create a Simple WCF Service</span></span>  
 <span data-ttu-id="9d6c9-136">In diesem Schritt erstellen Sie einen neuen WCF-Dienst, für den der im Identitäts- und Zugriffs-Tool enthaltene Entwicklungs-STS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-136">In this step, you will create a new WCF service that uses the Development STS that is included with the Identity and Access tool.</span></span>  
  
#### <a name="to-create-a-simple-wcf-service"></a><span data-ttu-id="9d6c9-137">So erstellen Sie einen einfachen WCF-Dienst</span><span class="sxs-lookup"><span data-stu-id="9d6c9-137">To create a simple WCF service</span></span>  
  
1.  <span data-ttu-id="9d6c9-138">Starten Sie Visual Studio im erweiterten Modus als Administrator.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-138">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2.  <span data-ttu-id="9d6c9-139">Klicken Sie in Visual Studio auf **Datei**, **Neu** und anschließend auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-139">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="9d6c9-140">Klicken Sie im Fenster **Neues Projekt** auf **WCF-Dienstanwendung**.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-140">In the **New Project** window, click **WCF Service Application**.</span></span>  
  
4.  <span data-ttu-id="9d6c9-141">Geben Sie im Feld **Name** die Zeichenfolge `TestService` ein, und drücken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-141">In **Name**, enter `TestService` and press **OK**.</span></span>  
  
5.  <span data-ttu-id="9d6c9-142">Klicken Sie mit der rechten Maustaste unter **Projektmappen-Explorer** auf das Projekt **TestService**, und klicken Sie dann auf **Identität und Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-142">Right-click the **TestService** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6.  <span data-ttu-id="9d6c9-143">Das Fenster **Identität und Zugriff** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-143">The **Identity and Access** window appears.</span></span> <span data-ttu-id="9d6c9-144">Klicken Sie unter **Anbieter** auf **Anwendung mit dem lokalen Entwicklungs-STS testen**, und klicken Sie auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-144">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span> <span data-ttu-id="9d6c9-145">Mit dem Identitäts- und Zugriffs-Tool wird der Dienst so konfiguriert, dass WIF verwendet wird und die Authentifizierung in den lokalen Entwicklungs-STS (**LocalSTS**) ausgelagert wird. Dazu werden der Datei *Web.config* Konfigurationselemente hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-145">The Identity and Access Tool configures the service to use WIF and to outsource authentication to the local development STS (**LocalSTS**) by adding configuration elements to the *Web.config* file.</span></span>  
  
7.  <span data-ttu-id="9d6c9-146">Fügen Sie in der Datei *Service1.svc.cs* eine `using`-Anweisung für den Namespace **System.Security.Claims** hinzu, und ersetzen Sie den vorhandenen Code durch folgenden Code. Speichern Sie die Datei anschließend:</span><span class="sxs-lookup"><span data-stu-id="9d6c9-146">In the *Service1.svc.cs* file, add a `using` directive for the **System.Security.Claims** namespace and replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    public class Service1 : IService1  
    {  
        public string ComputeResponse(string input)  
        {  
            // Get the caller's identity from ClaimsPrincipal.Current  
            ClaimsPrincipal claimsPrincipal = OperationContext.Current.ClaimsPrincipal;  
  
            // Start generating the output  
            StringBuilder builder = new StringBuilder();  
            builder.AppendLine("Computed by ClaimsAwareWebService");  
            builder.AppendLine("Input received from client:" + input);  
  
            if (claimsPrincipal != null)  
            {  
                // Display the claims from the caller. Do not use this code in a production application.  
                ClaimsIdentity identity = claimsPrincipal.Identity as ClaimsIdentity;  
                builder.AppendLine("Client Name:" + identity.Name);  
                builder.AppendLine("IsAuthenticated:" + identity.IsAuthenticated);  
                builder.AppendLine("The service received the following issued claims of the client:");  
  
                // Iterate over the caller’s claims and append to the output  
                foreach (Claim claim in claimsPrincipal.Claims)  
                {  
                    builder.AppendLine("ClaimType :" + claim.Type + "   ClaimValue:" + claim.Value);  
                }  
            }  
  
            return builder.ToString();  
        }  
    }  
    ```  
  
     <span data-ttu-id="9d6c9-147">Die `ComputeResponse`-Methode zeigt die Eigenschaften verschiedener Ansprüche an, die von **LocalSTS** ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-147">The `ComputeResponse` method displays the properties of various claims that are issued by **LocalSTS**.</span></span>  
  
8.  <span data-ttu-id="9d6c9-148">Ersetzen Sie in der Datei *IService1.cs* den vorhandenen Code durch folgenden Code. Speichern Sie die Datei anschließend:</span><span class="sxs-lookup"><span data-stu-id="9d6c9-148">In the *IService1.cs* file, replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    [ServiceContract]  
    public interface IService1  
    {  
        [OperationContract]  
        string ComputeResponse(string input);  
    }  
    ```  
  
9. <span data-ttu-id="9d6c9-149">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-149">Build the project.</span></span>  
  
10. <span data-ttu-id="9d6c9-150">Drücken Sie **STRG+F5**, um den Dienst auszuführen, ohne den Debugger zu starten.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-150">Press **Ctrl-F5** to run the service without starting the debugger.</span></span> <span data-ttu-id="9d6c9-151">Eine Webseite für den Dienst wird geöffnet. Hier können Sie im Infobereich (Taskleiste) überprüfen, ob **LocalSTS** ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-151">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9d6c9-152">Sowohl **TestService** als auch **LocalSTS** müssen ausgeführt werden, wenn Sie im nächsten Schritt der Clientanwendung den Dienstverweis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-152">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client application in the next step.</span></span>  
  
## <a name="step-2--create-a-client-application-for-the-wcf-service"></a><span data-ttu-id="9d6c9-153">Schritt 2 – Erstellen einer Clientanwendung für den WCF-Dienst</span><span class="sxs-lookup"><span data-stu-id="9d6c9-153">Step 2 – Create a Client Application for the WCF Service</span></span>  
 <span data-ttu-id="9d6c9-154">In diesem Schritt erstellen Sie eine Konsolenanwendung, in der der Entwicklungs-STS für die Authentifizierung des WCF-Diensts verwendet wird, den Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-154">In this step, you will create a console application that uses the Development STS to authenticate with the WCF service you created in the previous step.</span></span>  
  
#### <a name="to-create-a-client-application"></a><span data-ttu-id="9d6c9-155">So erstellen Sie eine Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="9d6c9-155">To create a client application</span></span>  
  
1.  <span data-ttu-id="9d6c9-156">Klicken Sie in Visual Studio mit der rechten Maustaste auf die Projektmappe, und klicken Sie dann auf **Hinzufügen** und **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-156">In Visual Studio, right-click on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="9d6c9-157">Wählen Sie im Fenster **Neues Projekt hinzufügen** aus der Vorlagenliste **Visual C#** den Eintrag **Konsolenanwendung** aus, geben Sie `Client` ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-157">In the **Add New Project** window, select **Console Application** from the **Visual C#** templates list, enter `Client`, and then press **OK**.</span></span> <span data-ttu-id="9d6c9-158">Das neue Projekt wird im Projektmappenordner erstellt.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-158">The new project will be created in your solution folder.</span></span>  
  
3.  <span data-ttu-id="9d6c9-159">Klicken Sie mit der rechten Maustaste unter dem Projekt **Client** auf **Verweise**, und klicken Sie dann auf **Dienstverweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-159">Right-click on **References** under the **Client** project, and then click **Add Service Reference**.</span></span>  
  
4.  <span data-ttu-id="9d6c9-160">Klicken Sie im Fenster **Dienstverweis hinzufügen** auf den Dropdownpfeil der Schaltfläche **Ermitteln**, und klicken Sie auf **Dienste in der Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-160">In the **Add Service Reference** window, click the drop-down arrow on the **Discover** button and click **Services in Solution**.</span></span> <span data-ttu-id="9d6c9-161">Die **Adresse** wird automatisch mit dem WCF-Dienst aufgefüllt, den Sie zuvor erstellt haben, und der **Namespace** wird auf **ServiceReference1** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-161">The **Address** will automatically populate with the WCF service you created earlier, and the **Namespace** will be set to **ServiceReference1**.</span></span> <span data-ttu-id="9d6c9-162">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-162">Click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9d6c9-163">Sowohl **TestService** als auch **LocalSTS** müssen ausgeführt werden, wenn Sie dem Client den Dienstverweis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-163">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client.</span></span>  
  
5.  <span data-ttu-id="9d6c9-164">Visual Studio generiert Proxyklassen für den WCF-Dienst und fügt alle erforderlichen Referenzinformationen hinzu.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-164">Visual Studio will generate proxy classes for the WCF service, and add all of the necessary reference information.</span></span> <span data-ttu-id="9d6c9-165">Auch werden der Datei *App.config* Elemente hinzugefügt, mit denen der Client so konfiguriert wird, dass für die Authentifizierung im Dienst ein Token aus dem STS abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-165">It will also add elements to the *App.config* file to configure the client to get a token from the STS to authenticate with the service.</span></span> <span data-ttu-id="9d6c9-166">Wenn dieser Prozess abgeschlossen ist, wird die Datei **Program.cs** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-166">When this process is finished, the **Program.cs** file will open.</span></span> <span data-ttu-id="9d6c9-167">Fügen Sie eine `using`-Anweisung für **System.ServiceModel** und eine weitere für **Client.ServiceReference1** hinzu. Ersetzen Sie dann die **Main**-Methode durch folgenden Code, und speichern Sie die Datei anschließend:</span><span class="sxs-lookup"><span data-stu-id="9d6c9-167">Add a `using` directive for **System.ServiceModel** and another for **Client.ServiceReference1**, replace the **Main** method with the following code, then save the file:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        // Create the client for the service  
        Service1Client client = new Service1Client();  
        Console.WriteLine("-------------WCF Client Application--------------\n");  
  
        while (!ShouldQuitApplication())  
        {  
            try  
            {  
                Console.WriteLine(client.ComputeResponse("Hello World"));  
            }  
            catch (CommunicationException e)  
            {  
                Console.WriteLine(e.Message);  
                Console.WriteLine(e.StackTrace);  
                Exception ex = e.InnerException;  
                while (ex != null)  
                {  
                    Console.WriteLine("===========================");  
                    Console.WriteLine(ex.Message);  
                    Console.WriteLine(ex.StackTrace);  
                    ex = ex.InnerException;  
                }  
            }  
            catch (TimeoutException)  
            {  
                Console.WriteLine("Timed out...");  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("An unexpected exception occurred.");  
                Console.WriteLine(e.StackTrace);  
            }  
        }  
  
        client.Close();  
  
        if (client != null)  
        {  
            client.Abort();  
        }  
    }  
  
    static bool ShouldQuitApplication()  
    {  
        Console.WriteLine("---------------------------------------------------------------------");  
        Console.WriteLine("Press Enter key to invoke service, any other key to quit application:");  
        Console.WriteLine("----------------------------------------------------------------------");  
  
        ConsoleKeyInfo keyInfo = Console.ReadKey();  
        if (keyInfo.Key == ConsoleKey.Enter)  
            return false;  
        return true;  
    }  
    ```  
  
6.  <span data-ttu-id="9d6c9-168">Öffnen Sie die Datei *App.config*, fügen Sie folgenden XML-Code als erstes untergeordnetes Element unter dem `<system.serviceModel>`-Element hinzu, und speichern Sie die Datei anschließend:</span><span class="sxs-lookup"><span data-stu-id="9d6c9-168">Open the *App.config* file and add the following XML as the first child element under the `<system.serviceModel>` element, then save the file:</span></span>  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
         <behavior>  
           <clientCredentials>  
             <serviceCertificate>  
               <authentication certificateValidationMode="None"/>  
             </serviceCertificate>  
           </clientCredentials>  
         </behavior>  
       </endpointBehaviors>  
     </behaviors>  
    ```  
  
     <span data-ttu-id="9d6c9-169">Damit wird die Zertifikatsvalidierung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-169">This disables certificate validation.</span></span>  
  
7.  <span data-ttu-id="9d6c9-170">Klicken Sie mit der rechten Maustaste auf die Projektmappe **TestService**, und klicken Sie auf **Startprojekte festlegen...**.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-170">Right-click the **TestService** solution and click on **Set StartUp Projects**.</span></span> <span data-ttu-id="9d6c9-171">Die Eigenschaftenseite **Startprojekt** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-171">The **Startup Project** property page opens.</span></span> <span data-ttu-id="9d6c9-172">Wählen Sie auf der Eigenschaftenseite **Startprojekt** die Option **Mehrere Startprojekte** aus, klicken Sie dann für jedes Projekt in das Feld **Aktion**, und wählen Sie im Dropdownmenü **Starten** aus.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-172">In the **Startup Project** property page, select **Multiple startup projects** then click in the **Action** field for each project and select **Start** from the drop-down menu.</span></span> <span data-ttu-id="9d6c9-173">Klicken Sie auf **OK**, um die Einstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-173">Click **OK** to save the settings.</span></span>  
  
8.  <span data-ttu-id="9d6c9-174">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-174">Build the solution.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="9d6c9-175">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="9d6c9-175">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="9d6c9-176">In diesem Schritt testen Sie die für WIF aktivierte WCF-Anwendung und überprüfen, ob Ansprüche dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-176">In this step you will test your WIF-enabled WCF application and verify that claims are presented.</span></span>  
  
#### <a name="to-test-your-wif-enabled-wcf-application-for-claims"></a><span data-ttu-id="9d6c9-177">So testen Sie die für WIF aktivierte WCF-Anwendung auf Ansprüche</span><span class="sxs-lookup"><span data-stu-id="9d6c9-177">To test your WIF-enabled WCF application for claims</span></span>  
  
1.  <span data-ttu-id="9d6c9-178">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-178">Press **F5** to build and run the application.</span></span> <span data-ttu-id="9d6c9-179">Ein Konsolenfenster mit folgendem Text wird angezeigt: **Press Enter key to invoke service, any other key to quit application:** (EINGABETASTE drücken, um den Dienst aufzurufen. Drücken Sie eine andere Taste, um die Anwendung zu beenden:)</span><span class="sxs-lookup"><span data-stu-id="9d6c9-179">You should be presented with a console window, and the following text: **Press Enter key to invoke service, any other key to quit application:**</span></span>  
  
2.  <span data-ttu-id="9d6c9-180">Drücken Sie die **EINGABETASTE**. Folgende Anspruchsinformationen sollten in der Konsole angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="9d6c9-180">Press **Enter**, and the following claims information should appear in the console:</span></span>  
  
    ```  
    Computed by Service1  
    Input received from client: Hello World  
    Client Name: Terry  
    IsAuthenticated: True  
    The service received the following issued claims of the client:  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name    ClaimValue:Terry  
    ClaimType :http://schema.xmlsoap.org/ws/2005/05/identity/claims/surname    ClaimValue:Adams  
    ClaimType :http://schemas.microsoft.com/ws/2008/06/identity/claims/role    ClaimValue:developer  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress    ClaimValue:terry@contoso.com  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9d6c9-181">Sowohl **TestService** als auch **LocalSTS** müssen ausgeführt werden, bevor Sie die **EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-181">Both **TestService** and **LocalSTS** must be running before you press **Enter**.</span></span> <span data-ttu-id="9d6c9-182">Eine Webseite für den Dienst wird geöffnet. Hier können Sie im Infobereich (Taskleiste) überprüfen, ob **LocalSTS** ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-182">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
3.  <span data-ttu-id="9d6c9-183">Wenn diese Ansprüche in der Konsole angezeigt werden, wurde die Authentifizierung im STS erfolgreich durchgeführt, und es werden Ansprüche vom WCF-Dienst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9d6c9-183">If these claims appear in the console, you have successfully authenticated with the STS to display claims from the WCF service.</span></span>
