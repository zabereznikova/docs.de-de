---
title: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 73633c2c6119204f2fb608b32ae794a2e07b27d0
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747073"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="530f0-102">Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts</span><span class="sxs-lookup"><span data-stu-id="530f0-102">How to host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="530f0-103">Dies ist die Dritte von sechs Aufgaben, die zum Erstellen einer WCF-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="530f0-103">This is the third of six tasks required to create a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="530f0-104">Eine Übersicht über alle sechs Aufgaben finden Sie im Artikel [Getting Started Tutorial (Tutorial: Erste Schritte)](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="530f0-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="530f0-105">In diesem Artikel wird beschrieben, wie ein WCF-Dienst in einer Konsolenanwendung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="530f0-105">This topic describes how to host a Windows Communication Foundation (WCF) service in a console application.</span></span> <span data-ttu-id="530f0-106">Dieses Verfahren umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="530f0-106">This procedure consists of the following steps:</span></span>

- <span data-ttu-id="530f0-107">Erstellen eines Konsolenanwendungsprojekts zum Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="530f0-107">Create a console application project to host the service.</span></span>

- <span data-ttu-id="530f0-108">Erstellen eines Diensthosts für den Dienst</span><span class="sxs-lookup"><span data-stu-id="530f0-108">Create a service host for the service.</span></span>

- <span data-ttu-id="530f0-109">Aktivieren des Metadatenaustauschs</span><span class="sxs-lookup"><span data-stu-id="530f0-109">Enable metadata exchange.</span></span>

- <span data-ttu-id="530f0-110">Öffnen des Diensthosts</span><span class="sxs-lookup"><span data-stu-id="530f0-110">Open the service host.</span></span>

<span data-ttu-id="530f0-111">Eine vollständige Liste des für diese Aufgabe geschriebenen Codes wird in einem Beispiel im Anschluss an das Verfahren bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="530f0-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>

## <a name="create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="530f0-112">Erstellen Sie eine neue Konsolenanwendung zum Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="530f0-112">Create a new console application to host the service</span></span>

1. <span data-ttu-id="530f0-113">Erstellen Sie ein neues Konsolenanwendungsprojekt in Visual Studio, indem Sie mit der rechten Maustaste auf die Projektmappe mit ersten Schritten und auswählen **hinzufügen** > **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="530f0-113">Create a new Console Application project in Visual Studio by right-clicking on the Getting Started solution and selecting **Add** > **New Project**.</span></span> <span data-ttu-id="530f0-114">In der **neues Projekt hinzufügen** im Dialogfeld auf der linken Seite, und wählen die **Windows Desktop** unter Kategorie **Visual C#-** oder **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="530f0-114">In the **Add New Project** dialog, on the left-hand side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> <span data-ttu-id="530f0-115">Wählen Sie die **Konsolen-App ((.NET Framework)** Vorlage, und nennen Sie das Projekt **GettingStartedHost**.</span><span class="sxs-lookup"><span data-stu-id="530f0-115">Select the **Console App (.NET Framework)** template, and then name the project **GettingStartedHost**.</span></span>

2. <span data-ttu-id="530f0-116">Fügen Sie dem GettingStartedHost-Projekt einen Verweis auf das GettingStartedLib-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="530f0-116">Add a reference to the GettingStartedLib project to the GettingStartedHost project.</span></span> <span data-ttu-id="530f0-117">Mit der rechten Maustaste auf die **Verweise** Ordner unterhalb des GettingStartedHost-Projekts in **Projektmappen-Explorer**, und wählen Sie dann **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="530f0-117">Right-click on the **References** folder under the GettingStartedHost project in **Solution Explorer**, and then select **Add Reference**.</span></span> <span data-ttu-id="530f0-118">In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Lösung** klicken Sie auf der linken Seite des Dialogfelds, wählen Sie im mittleren Abschnitt des Dialogfelds GettingStartedLib, und wählen Sie dann **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="530f0-118">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog, select GettingStartedLib in the center section of the dialog, and then choose **Add**.</span></span> <span data-ttu-id="530f0-119">Dadurch werden die in GettingStartedLib definierten Typen für das GettingStartedHost-Projekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="530f0-119">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>

3. <span data-ttu-id="530f0-120">Fügen Sie dem GettingStartedHost-Projekt einen Verweis auf den System.ServiceModel hinzu.</span><span class="sxs-lookup"><span data-stu-id="530f0-120">Add a reference to System.ServiceModel to the GettingStartedHost project.</span></span> <span data-ttu-id="530f0-121">Mit der rechten Maustaste die **Verweise** Ordner unterhalb des GettingStartedHost-Projekts in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="530f0-121">Right-click the **References** folder under the GettingStartedHost project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="530f0-122">In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Framework** auf der linken Seite des Dialogfelds unter **Assemblys**.</span><span class="sxs-lookup"><span data-stu-id="530f0-122">In the **Add Reference** dialog, select **Framework** on the left-hand side of the dialog under **Assemblies**.</span></span> <span data-ttu-id="530f0-123">Suchen und auswählen **System.ServiceModel**, und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="530f0-123">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> <span data-ttu-id="530f0-124">Speichern Sie die Projektmappe durch Auswahl **Datei** > **Alles speichern**.</span><span class="sxs-lookup"><span data-stu-id="530f0-124">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="host-the-service"></a><span data-ttu-id="530f0-125">Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="530f0-125">Host the service</span></span>

<span data-ttu-id="530f0-126">Öffnen Sie die Datei Program.cs oder Module.vb, und geben Sie den folgenden Code ein:</span><span class="sxs-lookup"><span data-stu-id="530f0-126">Open the Program.cs or Module.vb file and enter the following code:</span></span>

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
            // Step 1 Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 Create a ServiceHost instance
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 Start the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
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
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 Create a URI to serve as the base address
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted")

            ' Step 2 Create a ServiceHost instance
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
           Try

                ' Step 3 Add a service endpoint
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 Enable metadata exchange.
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 Start the service
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

<span data-ttu-id="530f0-127">**Schritt 1** -erstellt eine Instanz der Uri-Klasse, die die Basisadresse des Diensts enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="530f0-127">**Step 1** - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="530f0-128">Dienste werden über eine URL identifiziert, die eine Basisadresse und einen optionalen URI enthält.</span><span class="sxs-lookup"><span data-stu-id="530f0-128">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="530f0-129">Die Basisadresse ist wie folgt formatiert: [Transport]://[Computername oder Domäne][:optionaler Port #]/[optionales URI-Segment]. Für die Basisadresse des Rechnerdiensts werden HTTP-Transport, localhost, Port 8000 und das URI-Segment „GettingStarted“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="530f0-129">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>

<span data-ttu-id="530f0-130">**Schritt 2** – erstellt eine Instanz der <xref:System.ServiceModel.ServiceHost> Klasse, um den Dienst zu hosten.</span><span class="sxs-lookup"><span data-stu-id="530f0-130">**Step 2** – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="530f0-131">Der Konstruktor akzeptiert zwei Parameter: den Typ der Klasse, die den Dienstvertrag implementiert, und die Basisadresse des Diensts.</span><span class="sxs-lookup"><span data-stu-id="530f0-131">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>

<span data-ttu-id="530f0-132">**Schritt 3** – erstellt eine <xref:System.ServiceModel.Description.ServiceEndpoint> Instanz.</span><span class="sxs-lookup"><span data-stu-id="530f0-132">**Step 3** – Creates a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="530f0-133">Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen.</span><span class="sxs-lookup"><span data-stu-id="530f0-133">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="530f0-134">Der <xref:System.ServiceModel.Description.ServiceEndpoint>-Konstruktor akzeptiert daher den Schnittstellentyp des Dienstvertrags, eine Bindung und eine Adresse.</span><span class="sxs-lookup"><span data-stu-id="530f0-134">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="530f0-135">Der Dienstvertrag ist `ICalculator`, den Sie definiert haben und im Diensttyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="530f0-135">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="530f0-136">Die in diesem Beispiel verwendete Bindung ist <xref:System.ServiceModel.WSHttpBinding>. Dies ist eine integrierte Bindung, die für die Verbindung mit Endpunkten verwendet wird, die den WS-\*-Spezifikationen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="530f0-136">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="530f0-137">Weitere Informationen zu WCF-Bindungen finden Sie unter [WCF Bindings Overview (Übersicht über WCF-Bindungen)](bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="530f0-137">For more information about WCF bindings, see [WCF Bindings Overview](bindings-overview.md).</span></span> <span data-ttu-id="530f0-138">Die Adresse wird an die Basisadresse angefügt, um den Endpunkt zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="530f0-138">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="530f0-139">In diesem Code angegebene Adresse ist "CalculatorService", daher ist die vollqualifizierte Adresse für den Endpunkt `"http://localhost:8000/GettingStarted/CalculatorService"`.</span><span class="sxs-lookup"><span data-stu-id="530f0-139">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="530f0-140">Das Hinzufügen eines Dienstendpunkts ist optional, wenn .NET Framework 4 oder höher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="530f0-140">Adding a service endpoint is optional when using .NET Framework 4 or later.</span></span> <span data-ttu-id="530f0-141">Wenn im Code oder in der Konfiguration keine Endpunkte hinzugefügt wurden, fügt WCF in diesen Versionen einen Standardendpunkt für jede Kombination aus Basisadresse und Vertrag hinzu, die vom Dienst implementiert wurden.</span><span class="sxs-lookup"><span data-stu-id="530f0-141">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="530f0-142">Weitere Informationen zu Standardendpunkten finden Sie unter [Specifying an Endpoint Address (Angeben einer Endpunktadresse)](specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="530f0-142">For more information about default endpoints see [Specifying an Endpoint Address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="530f0-143">Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](./samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="530f0-143">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

<span data-ttu-id="530f0-144">**Schritt 4** – Aktivieren des Metadatenaustauschs.</span><span class="sxs-lookup"><span data-stu-id="530f0-144">**Step 4** – Enable metadata exchange.</span></span> <span data-ttu-id="530f0-145">Clients verwenden den Metadatenaustausch, um Proxys zu generieren, die zum Aufrufen von Dienstvorgängen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="530f0-145">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="530f0-146">Zum Aktivieren von Metadatenaustausch erstellen Sie eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Instanz, legen ihre <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf `true` fest und fügen der <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>-Instanz das Verhalten der <xref:System.ServiceModel.ServiceHost>-Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="530f0-146">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

<span data-ttu-id="530f0-147">**Schritt 5** : Öffnen der <xref:System.ServiceModel.ServiceHost> zum Lauschen auf eingehender Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="530f0-147">**Step 5** – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="530f0-148">Der Code wartet darauf, dass der Benutzer die EINGABETASTE drückt.</span><span class="sxs-lookup"><span data-stu-id="530f0-148">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="530f0-149">Wenn dies nicht erfolgt, wird die App sofort geschlossen und der Dienst heruntergefahren. Beachten Sie auch, dass ein try/catch-Block verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="530f0-149">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="530f0-150">Nachdem der <xref:System.ServiceModel.ServiceHost> instanziiert wurde, wird der gesamte sonstige Code in einen try/catch-Block eingefügt.</span><span class="sxs-lookup"><span data-stu-id="530f0-150">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="530f0-151">Weitere Informationen zum sicheren Abfangen von Ausnahmen durch <xref:System.ServiceModel.ServiceHost>, finden Sie unter [verwenden schließen "und" Abort, WCF-Client-Ressourcen freizugeben.](samples/use-close-abort-release-wcf-client-resources.md)</span><span class="sxs-lookup"><span data-stu-id="530f0-151">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="530f0-152">Wenn Sie einen WCF-Dienstbibliothek hinzufügen, kann Visual Studio hostet es für Sie beim Debuggen von einem Diensthost ab.</span><span class="sxs-lookup"><span data-stu-id="530f0-152">When you add a WCF Service Library, Visual Studio can host it for you when you debug by starting a service host.</span></span> <span data-ttu-id="530f0-153">Um Konflikte zu vermeiden, können Sie diese deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="530f0-153">To avoid conflicts you can disable this.</span></span> 
> 1. <span data-ttu-id="530f0-154">Öffnen der Projekteigenschaften für GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="530f0-154">Open Project Properties for GettingStartedLib.</span></span>
> 2. <span data-ttu-id="530f0-155">Wechseln Sie zu **WCF-Optionen** , und deaktivieren Sie **starten WCF-Diensthost beim Debuggen**.</span><span class="sxs-lookup"><span data-stu-id="530f0-155">Go to **WCF Options** and uncheck **Start WCF Service Host when debugging**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="530f0-156">Stellen Sie sicher, dass der Dienst funktioniert.</span><span class="sxs-lookup"><span data-stu-id="530f0-156">Verify the service is working</span></span>

1. <span data-ttu-id="530f0-157">Führen Sie die GettingStartedHost-Konsole Anwendung von innerhalb von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="530f0-157">Run the GettingStartedHost console application from inside Visual Studio.</span></span>

   <span data-ttu-id="530f0-158">Der Dienst muss mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="530f0-158">The service must be run with administrator privileges.</span></span> <span data-ttu-id="530f0-159">Da Visual Studio mit Administratorrechten geöffnet wurde, wird die GettingStartedHost auch mit Administratorrechten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="530f0-159">Because Visual Studio was opened with administrator privileges, GettingStartedHost is also run with administrator privileges.</span></span> <span data-ttu-id="530f0-160">Sie können auch öffnen, eine neue Eingabeaufforderung mit **als Administrator ausführen** und führen Sie service.exe darin.</span><span class="sxs-lookup"><span data-stu-id="530f0-160">You can also open a new command prompt using **Run as administrator** and run service.exe within it.</span></span>

2. <span data-ttu-id="530f0-161">Öffnen Sie einen Webbrowser, und navigieren Sie zu den Dienst Debuggen-Seite unter `http://localhost:8000/GettingStarted/`.</span><span class="sxs-lookup"><span data-stu-id="530f0-161">Open a web browser and browse to the service's debug page at `http://localhost:8000/GettingStarted/`.</span></span> <span data-ttu-id="530f0-162">**Hinweis! Es ist wichtig, Schrägstrich enden.**</span><span class="sxs-lookup"><span data-stu-id="530f0-162">**Note! Ending slash is significant.**</span></span>

## <a name="example"></a><span data-ttu-id="530f0-163">Beispiel</span><span class="sxs-lookup"><span data-stu-id="530f0-163">Example</span></span>

<span data-ttu-id="530f0-164">Das folgende Beispiel enthält den Dienstvertrag und die Implementierung aus den vorangegangenen Schritten im Lernprogramm und hostet den Dienst in einer Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="530f0-164">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>

<span data-ttu-id="530f0-165">Um dies mit einem Befehlszeilencompiler kompilieren, kompilieren Sie IService1.cs und Service1.cs in eine Klassenbibliothek, die verweist `System.ServiceModel.dll`.</span><span class="sxs-lookup"><span data-stu-id="530f0-165">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library that references `System.ServiceModel.dll`.</span></span> <span data-ttu-id="530f0-166">Kompilieren Sie "Program.cs", als eine Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="530f0-166">Compile Program.cs as a console application.</span></span>

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
        [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
        public interface ICalculator
        {
            [OperationContract]
            double Add(double n1, double n2);
            [OperationContract]
            double Subtract(double n1, double n2);
            [OperationContract]
            double Multiply(double n1, double n2);
            [OperationContract]
            double Divide(double n1, double n2);
        }
}
```

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

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
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 of the hosting procedure: Create ServiceHost
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 of the hosting procedure: Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 of the hosting procedure: Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
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

Namespace GettingStartedLib

    <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
    Public Interface ICalculator

        <OperationContract()> _
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
End Namespace
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

```vb
Imports System.ServiceModel
Imports System.ServiceModel.Description
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

            ' Step 2 of the hosting procedure: Create ServiceHost
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
            Try

                ' Step 3 of the hosting procedure: Add a service endpoint.
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 of the hosting procedure: Enable metadata exchange.
                ' Enable metadata exchange
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

> [!NOTE]
> <span data-ttu-id="530f0-167">Dienste wie dieser müssen dazu berechtigt sein, HTTP-Adressen auf dem Computer zum Überwachen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="530f0-167">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="530f0-168">Administratorkonten verfügen über diese Berechtigung, anderen Konten muss jedoch die Berechtigung für HTTP-Namespaces erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="530f0-168">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="530f0-169">Weitere Informationen zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS (Konfigurieren von HTTP und HTTPS)](feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="530f0-169">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="530f0-170">Wird der Dienst unter Visual Studio ausgeführt, muss „service.exe“ mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="530f0-170">When running under Visual Studio, the service.exe must be run with administrator privileges.</span></span>

## <a name="next-steps"></a><span data-ttu-id="530f0-171">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="530f0-171">Next steps</span></span>

<span data-ttu-id="530f0-172">Der Dienst wird nun ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="530f0-172">Now the service is running.</span></span> <span data-ttu-id="530f0-173">In der nächsten Aufgabe erstellen Sie einen WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="530f0-173">In the next task, you create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="530f0-174">Vorgehensweise: Erstellen Sie einen WCF-client</span><span class="sxs-lookup"><span data-stu-id="530f0-174">How to: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)

<span data-ttu-id="530f0-175">Informationen zur Problembehandlung finden Sie unter [Troubleshooting the Getting Started Tutorial (Problembehandlung für das Tutorial „Erste Schritte“)](troubleshooting-the-getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="530f0-175">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](troubleshooting-the-getting-started-tutorial.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="530f0-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="530f0-176">See also</span></span>

- [<span data-ttu-id="530f0-177">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="530f0-177">Getting Started</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="530f0-178">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="530f0-178">Self-Host</span></span>](samples/self-host.md)
- [<span data-ttu-id="530f0-179">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="530f0-179">Hosting Services</span></span>](hosting-services.md)
