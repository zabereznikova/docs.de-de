---
title: 'Vorgehensweise: Hosten Sie und führen Sie einer grundlegenden Windows Communication Foundation-Diensts aus'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 710ccd69d7b0f8cd8cd3e04729fd952308a3fb4a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129375"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="2ff85-102">Vorgehensweise: Hosten Sie und führen Sie einer grundlegenden Windows Communication Foundation-Diensts aus</span><span class="sxs-lookup"><span data-stu-id="2ff85-102">How to: Host and Run a Basic Windows Communication Foundation Service</span></span>

<span data-ttu-id="2ff85-103">Dies ist die Dritte von sechs Aufgaben, die zum Erstellen einer WCF-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2ff85-103">This is the third of six tasks required to create a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="2ff85-104">Eine Übersicht über alle sechs Aufgaben finden Sie im Artikel [Getting Started Tutorial (Tutorial: Erste Schritte)](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="2ff85-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="2ff85-105">In diesem Artikel wird beschrieben, wie ein WCF-Dienst in einer Konsolenanwendung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="2ff85-105">This topic describes how to host a Windows Communication Foundation (WCF) service in a console application.</span></span> <span data-ttu-id="2ff85-106">Dieses Verfahren umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="2ff85-106">This procedure consists of the following steps:</span></span>

- <span data-ttu-id="2ff85-107">Erstellen eines Konsolenanwendungsprojekts zum Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="2ff85-107">Create a console application project to host the service.</span></span>

- <span data-ttu-id="2ff85-108">Erstellen eines Diensthosts für den Dienst</span><span class="sxs-lookup"><span data-stu-id="2ff85-108">Create a service host for the service.</span></span>

- <span data-ttu-id="2ff85-109">Aktivieren des Metadatenaustauschs</span><span class="sxs-lookup"><span data-stu-id="2ff85-109">Enable metadata exchange.</span></span>

- <span data-ttu-id="2ff85-110">Öffnen des Diensthosts</span><span class="sxs-lookup"><span data-stu-id="2ff85-110">Open the service host.</span></span>

<span data-ttu-id="2ff85-111">Eine vollständige Liste des für diese Aufgabe geschriebenen Codes wird in einem Beispiel im Anschluss an das Verfahren bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2ff85-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>

## <a name="create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="2ff85-112">Erstellen Sie eine neue Konsolenanwendung zum Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="2ff85-112">Create a new console application to host the service</span></span>

1. <span data-ttu-id="2ff85-113">Erstellen Sie ein neues Konsolenanwendungsprojekt in Visual Studio, indem Sie mit der rechten Maustaste auf die Projektmappe mit ersten Schritten und auswählen **hinzufügen** > **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="2ff85-113">Create a new Console Application project in Visual Studio by right-clicking on the Getting Started solution and selecting **Add** > **New Project**.</span></span> <span data-ttu-id="2ff85-114">In der **neues Projekt hinzufügen** im Dialogfeld auf der linken Seite, und wählen die **Windows Desktop** unter Kategorie **Visual C#-** oder **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="2ff85-114">In the **Add New Project** dialog, on the left-hand side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> <span data-ttu-id="2ff85-115">Wählen Sie die **Konsolen-App ((.NET Framework)** Vorlage, und nennen Sie das Projekt **GettingStartedHost**.</span><span class="sxs-lookup"><span data-stu-id="2ff85-115">Select the **Console App (.NET Framework)** template, and then name the project **GettingStartedHost**.</span></span>

2. <span data-ttu-id="2ff85-116">Fügen Sie dem GettingStartedHost-Projekt einen Verweis auf das GettingStartedLib-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="2ff85-116">Add a reference to the GettingStartedLib project to the GettingStartedHost project.</span></span> <span data-ttu-id="2ff85-117">Mit der rechten Maustaste auf die **Verweise** Ordner unterhalb des GettingStartedHost-Projekts in **Projektmappen-Explorer**, und wählen Sie dann **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2ff85-117">Right-click on the **References** folder under the GettingStartedHost project in **Solution Explorer**, and then select **Add Reference**.</span></span> <span data-ttu-id="2ff85-118">In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Lösung** klicken Sie auf der linken Seite des Dialogfelds, wählen Sie im mittleren Abschnitt des Dialogfelds GettingStartedLib, und wählen Sie dann **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2ff85-118">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog, select GettingStartedLib in the center section of the dialog, and then choose **Add**.</span></span> <span data-ttu-id="2ff85-119">Dadurch werden die in GettingStartedLib definierten Typen für das GettingStartedHost-Projekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2ff85-119">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>

3. <span data-ttu-id="2ff85-120">Fügen Sie dem GettingStartedHost-Projekt einen Verweis auf den System.ServiceModel hinzu.</span><span class="sxs-lookup"><span data-stu-id="2ff85-120">Add a reference to System.ServiceModel to the GettingStartedHost project.</span></span> <span data-ttu-id="2ff85-121">Mit der rechten Maustaste die **Verweise** Ordner unterhalb des GettingStartedHost-Projekts in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2ff85-121">Right-click the **References** folder under the GettingStartedHost project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="2ff85-122">In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Framework** auf der linken Seite des Dialogfelds unter **Assemblys**.</span><span class="sxs-lookup"><span data-stu-id="2ff85-122">In the **Add Reference** dialog, select **Framework** on the left-hand side of the dialog under **Assemblies**.</span></span> <span data-ttu-id="2ff85-123">Suchen und auswählen **System.ServiceModel**, und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ff85-123">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> <span data-ttu-id="2ff85-124">Speichern Sie die Projektmappe durch Auswahl **Datei** > **Alles speichern**.</span><span class="sxs-lookup"><span data-stu-id="2ff85-124">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="host-the-service"></a><span data-ttu-id="2ff85-125">Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="2ff85-125">Host the service</span></span>

<span data-ttu-id="2ff85-126">Öffnen Sie die Datei Program.cs oder Module.vb, und geben Sie den folgenden Code ein:</span><span class="sxs-lookup"><span data-stu-id="2ff85-126">Open the Program.cs or Module.vb file and enter the following code:</span></span>

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
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")

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

<span data-ttu-id="2ff85-127">**Schritt 1** -erstellt eine Instanz der Uri-Klasse, die die Basisadresse des Diensts enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="2ff85-127">**Step 1** - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="2ff85-128">Dienste werden über eine URL identifiziert, die eine Basisadresse und einen optionalen URI enthält.</span><span class="sxs-lookup"><span data-stu-id="2ff85-128">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="2ff85-129">Die Basisadresse ist wie folgt formatiert: [Transport]://[Computername oder Domäne][:optionaler Port #]/[optionales URI-Segment]. Für die Basisadresse des Rechnerdiensts werden HTTP-Transport, localhost, Port 8000 und das URI-Segment „GettingStarted“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ff85-129">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>

<span data-ttu-id="2ff85-130">**Schritt 2** – erstellt eine Instanz der <xref:System.ServiceModel.ServiceHost> Klasse, um den Dienst zu hosten.</span><span class="sxs-lookup"><span data-stu-id="2ff85-130">**Step 2** – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="2ff85-131">Der Konstruktor akzeptiert zwei Parameter: den Typ der Klasse, die den Dienstvertrag implementiert, und die Basisadresse des Diensts.</span><span class="sxs-lookup"><span data-stu-id="2ff85-131">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>

<span data-ttu-id="2ff85-132">**Schritt 3** – erstellt eine <xref:System.ServiceModel.Description.ServiceEndpoint> Instanz.</span><span class="sxs-lookup"><span data-stu-id="2ff85-132">**Step 3** – Creates a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="2ff85-133">Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen.</span><span class="sxs-lookup"><span data-stu-id="2ff85-133">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="2ff85-134">Der <xref:System.ServiceModel.Description.ServiceEndpoint>-Konstruktor akzeptiert daher den Schnittstellentyp des Dienstvertrags, eine Bindung und eine Adresse.</span><span class="sxs-lookup"><span data-stu-id="2ff85-134">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="2ff85-135">Der Dienstvertrag ist `ICalculator`, den Sie definiert haben und im Diensttyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="2ff85-135">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="2ff85-136">Die in diesem Beispiel verwendete Bindung ist <xref:System.ServiceModel.WSHttpBinding>. Dies ist eine integrierte Bindung, die für die Verbindung mit Endpunkten verwendet wird, die den WS-\*-Spezifikationen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2ff85-136">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="2ff85-137">Weitere Informationen zu WCF-Bindungen finden Sie unter [WCF Bindings Overview (Übersicht über WCF-Bindungen)](../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2ff85-137">For more information about WCF bindings, see [WCF Bindings Overview](../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="2ff85-138">Die Adresse wird an die Basisadresse angefügt, um den Endpunkt zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2ff85-138">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="2ff85-139">In diesem Code angegebene Adresse ist "CalculatorService", daher ist die vollqualifizierte Adresse für den Endpunkt `"http://localhost:8000/GettingStarted/CalculatorService"`.</span><span class="sxs-lookup"><span data-stu-id="2ff85-139">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"`.</span></span>

    > [!IMPORTANT]
    > Adding a service endpoint is optional when using .NET Framework 4 or later. In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service. For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md). For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).

<span data-ttu-id="2ff85-140">**Schritt 4** – Aktivieren des Metadatenaustauschs.</span><span class="sxs-lookup"><span data-stu-id="2ff85-140">**Step 4** – Enable metadata exchange.</span></span> <span data-ttu-id="2ff85-141">Clients verwenden den Metadatenaustausch, um Proxys zu generieren, die zum Aufrufen von Dienstvorgängen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ff85-141">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="2ff85-142">Erstellen Sie zum Aktivieren von Metadatenaustausch eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Instanz, legen Sie ihre <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf `true` fest, und fügen Sie das Verhalten der <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A`-Auflistung der <xref:System.ServiceModel.ServiceHost>-Instanz hinzu.</span><span class="sxs-lookup"><span data-stu-id="2ff85-142">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

<span data-ttu-id="2ff85-143">**Schritt 5** : Öffnen der <xref:System.ServiceModel.ServiceHost> zum Lauschen auf eingehender Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="2ff85-143">**Step 5** – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="2ff85-144">Der Code wartet darauf, dass der Benutzer die EINGABETASTE drückt.</span><span class="sxs-lookup"><span data-stu-id="2ff85-144">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="2ff85-145">Wenn dies nicht erfolgt, wird die App sofort geschlossen und der Dienst heruntergefahren. Beachten Sie auch, dass ein try/catch-Block verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ff85-145">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="2ff85-146">Nachdem der <xref:System.ServiceModel.ServiceHost> instanziiert wurde, wird der gesamte sonstige Code in einen try/catch-Block eingefügt.</span><span class="sxs-lookup"><span data-stu-id="2ff85-146">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="2ff85-147">Weitere Informationen zum sicheren Abfangen von Ausnahmen durch <xref:System.ServiceModel.ServiceHost>, finden Sie unter [verwenden schließen "und" Abort, WCF-Client-Ressourcen freizugeben.](../../../docs/framework/wcf/samples/use-close-abort-release-wcf-client-resources.md)</span><span class="sxs-lookup"><span data-stu-id="2ff85-147">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](../../../docs/framework/wcf/samples/use-close-abort-release-wcf-client-resources.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ff85-148">Bearbeiten Sie die Datei "App.config" im GettingStartedLib entsprechend die Änderungen im Code vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="2ff85-148">Edit App.config in GettingStartedLib to reflect the changes made in code:</span></span>
> 1. <span data-ttu-id="2ff85-149">Ändern Sie Zeile 14 `<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="2ff85-149">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
> 2. <span data-ttu-id="2ff85-150">Ändern Sie Zeile 17 in `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="2ff85-150">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
> 3. <span data-ttu-id="2ff85-151">Ändern Sie Zeile 22 in `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="2ff85-151">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="2ff85-152">Stellen Sie sicher, dass der Dienst funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2ff85-152">Verify the service is working</span></span>

1. <span data-ttu-id="2ff85-153">Führen Sie die GettingStartedHost-Konsole Anwendung von innerhalb von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2ff85-153">Run the GettingStartedHost console application from inside Visual Studio.</span></span>

   <span data-ttu-id="2ff85-154">Der Dienst muss mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2ff85-154">The service must be run with administrator privileges.</span></span> <span data-ttu-id="2ff85-155">Da Visual Studio mit Administratorrechten geöffnet wurde, wird die GettingStartedHost auch mit Administratorrechten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2ff85-155">Because Visual Studio was opened with administrator privileges, GettingStartedHost is also run with administrator privileges.</span></span> <span data-ttu-id="2ff85-156">Sie können auch öffnen, eine neue Eingabeaufforderung mit **als Administrator ausführen** und führen Sie service.exe darin.</span><span class="sxs-lookup"><span data-stu-id="2ff85-156">You can also open a new command prompt using **Run as administrator** and run service.exe within it.</span></span>

2. <span data-ttu-id="2ff85-157">Öffnen Sie einen Webbrowser, und navigieren Sie zu den Dienst Debuggen-Seite unter `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="2ff85-157">Open a web browser and browse to the service's debug page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

## <a name="example"></a><span data-ttu-id="2ff85-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ff85-158">Example</span></span>

<span data-ttu-id="2ff85-159">Das folgende Beispiel enthält den Dienstvertrag und die Implementierung aus den vorangegangenen Schritten im Lernprogramm und hostet den Dienst in einer Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="2ff85-159">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>

<span data-ttu-id="2ff85-160">Um dies mit einem Befehlszeilencompiler kompilieren, kompilieren Sie IService1.cs und Service1.cs in eine Klassenbibliothek, die verweist `System.ServiceModel.dll`.</span><span class="sxs-lookup"><span data-stu-id="2ff85-160">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library that references `System.ServiceModel.dll`.</span></span> <span data-ttu-id="2ff85-161">Kompilieren Sie "Program.cs", als eine Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="2ff85-161">Compile Program.cs as a console application.</span></span>

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
            Uri baseAddress = new Uri("http://localhost:8000/ServiceModelSamples/Service");

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
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")

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
> <span data-ttu-id="2ff85-162">Dienste wie dieser müssen dazu berechtigt sein, HTTP-Adressen auf dem Computer zum Überwachen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="2ff85-162">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="2ff85-163">Administratorkonten verfügen über diese Berechtigung, anderen Konten muss jedoch die Berechtigung für HTTP-Namespaces erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="2ff85-163">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="2ff85-164">Weitere Informationen zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS (Konfigurieren von HTTP und HTTPS)](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="2ff85-164">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="2ff85-165">Wird der Dienst unter Visual Studio ausgeführt, muss „service.exe“ mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2ff85-165">When running under Visual Studio, the service.exe must be run with administrator privileges.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2ff85-166">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2ff85-166">Next steps</span></span>

<span data-ttu-id="2ff85-167">Der Dienst wird nun ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2ff85-167">Now the service is running.</span></span> <span data-ttu-id="2ff85-168">In der nächsten Aufgabe erstellen Sie einen WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="2ff85-168">In the next task, you create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2ff85-169">So wird es gemacht: Erstellen Sie einen WCF-client</span><span class="sxs-lookup"><span data-stu-id="2ff85-169">How to: Create a WCF client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)

<span data-ttu-id="2ff85-170">Informationen zur Problembehandlung finden Sie unter [Troubleshooting the Getting Started Tutorial (Problembehandlung für das Tutorial „Erste Schritte“)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="2ff85-170">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ff85-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ff85-171">See also</span></span>

- [<span data-ttu-id="2ff85-172">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="2ff85-172">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="2ff85-173">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="2ff85-173">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)