---
title: "Gewusst wie: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 92aa512a12911913c1d4d7ca1587bb04df0a501d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="743a5-102">Gewusst wie: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts</span><span class="sxs-lookup"><span data-stu-id="743a5-102">How to: Host and Run a Basic Windows Communication Foundation Service</span></span>
<span data-ttu-id="743a5-103">Dies ist die dritte von sechs Aufgaben, die zum Erstellen einer grundlegenden [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="743a5-103">This is the third of six tasks required to create a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="743a5-104">Einen Überblick über alle sechs Aufgaben finden Sie unter der [Lernprogramm für erste Schritte](../../../docs/framework/wcf/getting-started-tutorial.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="743a5-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="743a5-105">In diesem Thema wird beschrieben, wie ein [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Dienst in einer Konsolenanwendung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="743a5-105">This topic describes how to host a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service in a console application.</span></span> <span data-ttu-id="743a5-106">Dieses Verfahren umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="743a5-106">This procedure consists of the following steps:</span></span>  
  
-   <span data-ttu-id="743a5-107">Erstellen eines Konsolenanwendungsprojekts zum Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="743a5-107">Create a console application project to host the service.</span></span>  
  
-   <span data-ttu-id="743a5-108">Erstellen eines Diensthosts für den Dienst</span><span class="sxs-lookup"><span data-stu-id="743a5-108">Create a service host for the service.</span></span>  
  
-   <span data-ttu-id="743a5-109">Aktivieren des Metadatenaustauschs</span><span class="sxs-lookup"><span data-stu-id="743a5-109">Enable metadata exchange.</span></span>  
  
-   <span data-ttu-id="743a5-110">Öffnen des Diensthosts</span><span class="sxs-lookup"><span data-stu-id="743a5-110">Open the service host.</span></span>  
  
 <span data-ttu-id="743a5-111">Eine vollständige Liste des für diese Aufgabe geschriebenen Codes wird in einem Beispiel im Anschluss an das Verfahren bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="743a5-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="743a5-112">So erstellen Sie eine neue Konsolenanwendung zum Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="743a5-112">To create a new console application to host the service</span></span>  
  
1.  <span data-ttu-id="743a5-113">Erstellen Sie ein neues Konsolenanwendungsprojekt mit der rechten Maustaste auf die erste Schritte-Projektmappe, wenn Sie auswählen, **hinzufügen**, **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="743a5-113">Create a new Console Application project by right-clicking on the Getting Started solution, selecting, **Add**, **New Project**.</span></span> <span data-ttu-id="743a5-114">In der **neues Projekt hinzufügen** -Dialogfeld auf der linken Seite der Dialogfeld Select **Windows** unter **c#** oder **VB**.</span><span class="sxs-lookup"><span data-stu-id="743a5-114">In the **Add New Project** dialog on the left hand side of the dialog select **Windows** under **C#** or **VB**.</span></span> <span data-ttu-id="743a5-115">Wählen Sie im mittleren Abschnitt des Dialogfelds **Konsolenanwendung**.</span><span class="sxs-lookup"><span data-stu-id="743a5-115">In the center section of the dialog select **Console Application**.</span></span> <span data-ttu-id="743a5-116">Nennen Sie das Projekt GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="743a5-116">Name the project GettingStartedHost.</span></span>  
  
2.  <span data-ttu-id="743a5-117">Legen Sie das Zielframework des GettingStartedHost-Projekts auf .NET Framework 4.5 per Rechtsklick auf **"gettingstartedhost"** im Projektmappen-Explorer auswählen und **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="743a5-117">Set the target framework of the GettingStartedHost project to .NET Framework 4.5 by right clicking on **GettingStartedHost** in the Solution Explorer and selecting **Properties**.</span></span> <span data-ttu-id="743a5-118">Im Dropdownfeld mit der Bezeichnung **Zielframework** wählen **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="743a5-118">In the dropdown box labeled **Target Framework** select **.NET Framework 4.5**.</span></span> <span data-ttu-id="743a5-119">Festlegen des Zielframeworks für ein VB-Projekt weicht etwas im Eigenschaftendialogfeld GettingStartedHost-Projekts klicken Sie auf die **Kompilieren** Registerkarte auf der linken Seite des Bildschirms, und klicken Sie dann auf die **erweiterte kompilieren Optionen** Schaltfläche auf der unteren linken Ecke des Dialogfelds.</span><span class="sxs-lookup"><span data-stu-id="743a5-119">Setting the target framework for a VB project is a little different, in the GettingStartedHost project properties dialog, click the **Compile** tab on the left-hand side of the screen, and then click the **Advanced Compile Options** button at the lower left-hand corner of the dialog.</span></span> <span data-ttu-id="743a5-120">Wählen Sie dann **.NET Framework 4.5** im Dropdownfeld mit der Bezeichnung **Zielframework**.</span><span class="sxs-lookup"><span data-stu-id="743a5-120">Then select **.NET Framework 4.5** in the dropdown box labeled **Target Framework**.</span></span>  
  
     <span data-ttu-id="743a5-121">Festlegen des Zielframeworks führt dazu, dass [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] um die Projektmappe erneut zu laden, drücken Sie die **OK** Aufforderung.</span><span class="sxs-lookup"><span data-stu-id="743a5-121">Setting the target framework will cause [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] to reload the solution, press **OK** when prompted.</span></span>  
  
3.  <span data-ttu-id="743a5-122">GettingStartedHost-Projekts einen Verweis auf das GettingStartedLib-Projekt hinzugefügt, indem Sie mit der mit der rechten Maustaste auf die **Verweise** Ordner unter dem GettingStartedHost-Projekt im Projektmappen-Explorer und wählen **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="743a5-122">Add a reference to the GettingStartedLib project to the GettingStartedHost project by right clicking on the **References** folder under the GettingStartedHost project in the solution explorer and select **Add Reference**.</span></span> <span data-ttu-id="743a5-123">In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Lösung** auf der linken Seite des Dialogfeld und wählen GettingStartedLib im mittleren Abschnitt des Dialogfeld und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="743a5-123">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog and select GettingStartedLib in the center section of the dialog and click **Add**.</span></span> <span data-ttu-id="743a5-124">Dadurch werden die in GettingStartedLib definierten Typen für das GettingStartedHost-Projekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="743a5-124">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>  
  
4.  <span data-ttu-id="743a5-125">Fügen Sie einen Verweis auf System.ServiceModel dem GettingStartedHost-Projekt, indem Sie mit der rechten Maustaste die **Verweis** Ordner unter dem GettingStartedHost-Projekt im Projektmappen-Explorer und wählen **hinzufügen** Verweis.</span><span class="sxs-lookup"><span data-stu-id="743a5-125">Add a reference to System.ServiceModel to the GettingStartedHost project by right-clicking the **Reference** folder under the GettingStartedHost project in Solution Explorer and select **Add** Reference.</span></span> <span data-ttu-id="743a5-126">In der **Verweis hinzufügen** Dialogfeld wählen **Framework** auf der linken Seite des Dialogfelds.</span><span class="sxs-lookup"><span data-stu-id="743a5-126">In the **Add Reference** dialog select **Framework** on the left-hand side of the dialog.</span></span> <span data-ttu-id="743a5-127">Geben Sie im Textfeld Assemblys suchen`System.ServiceModel` ein.</span><span class="sxs-lookup"><span data-stu-id="743a5-127">In the Search Assemblies textbox, type in `System.ServiceModel`.</span></span> <span data-ttu-id="743a5-128">Wählen Sie im mittleren Abschnitt des Dialogfelds **System.ServiceModel**, klicken Sie auf die **hinzufügen** aus, und klicken Sie auf die **schließen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="743a5-128">In the center section of the dialog select **System.ServiceModel**, click the **Add** button, and click the **Close** button.</span></span> <span data-ttu-id="743a5-129">Speichern Sie die Projektmappe, indem Sie unterhalb des Hauptmenüs auf die Schaltfläche Alle speichern klicken.</span><span class="sxs-lookup"><span data-stu-id="743a5-129">Save the solution by clicking the Save All button below the main menu.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="743a5-130">So hosten Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="743a5-130">To host the service</span></span>  
  
-   <span data-ttu-id="743a5-131">Öffnen Sie die Datei Program.cs oder Module.vb, und geben Sie den folgenden Code ein:</span><span class="sxs-lookup"><span data-stu-id="743a5-131">Open the Program.cs or Module.vb file and enter the following code:</span></span>  
  
    ```csharp
    // program.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
    using GettingStartedLib;  
    using System.ServiceModel.Description;   
  
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
    'Module1.vb  
    Imports System  
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
  
    1.  <span data-ttu-id="743a5-132">Schritt 1: Erstellt eine Instanz der URI-Klasse, die die Basisadresse des Diensts enthält.</span><span class="sxs-lookup"><span data-stu-id="743a5-132">Step 1 - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="743a5-133">Dienste werden über eine URL identifiziert, die eine Basisadresse und einen optionalen URI enthält.</span><span class="sxs-lookup"><span data-stu-id="743a5-133">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="743a5-134">Die Basisadresse weist das folgende Format: [transport] :// [-Computernamen oder die Domäne] [: optionale # port] / [optionale URI-Segment] die Basisadresse für den rechnerdienst verwendet den HTTP-Transport, "localhost", Port 8000 und der URI-segment "Erste Schritte"</span><span class="sxs-lookup"><span data-stu-id="743a5-134">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>  
  
    2.  <span data-ttu-id="743a5-135">Schritt 2: Erstellt eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse zum Hosten des Diensts.</span><span class="sxs-lookup"><span data-stu-id="743a5-135">Step 2 – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="743a5-136">Der Konstruktor akzeptiert zwei Parameter: den Typ der Klasse, die den Dienstvertrag implementiert, und die Basisadresse des Diensts.</span><span class="sxs-lookup"><span data-stu-id="743a5-136">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>  
  
    3.  <span data-ttu-id="743a5-137">Schritt 3: erstellt eine <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` Instanz.</span><span class="sxs-lookup"><span data-stu-id="743a5-137">Step 3 – Creates a <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` instance.</span></span> <span data-ttu-id="743a5-138">Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen.</span><span class="sxs-lookup"><span data-stu-id="743a5-138">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="743a5-139">Die <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` Konstruktor akzeptiert daher den Schnittstellentyp des Dienstvertrags, einer Bindung und eine Adresse.</span><span class="sxs-lookup"><span data-stu-id="743a5-139">The <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint`  constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="743a5-140">Der Dienstvertrag ist `ICalculator`, den Sie definiert haben und im Diensttyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="743a5-140">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="743a5-141">Die in diesem Beispiel verwendete Bindung ist <xref:System.ServiceModel.WSHttpBinding>. Dies ist eine integrierte Bindung, die für die Verbindung mit Endpunkten verwendet wird, die den WS-*-Spezifikationen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="743a5-141">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-* specifications.</span></span> <span data-ttu-id="743a5-142">Weitere Informationen zu WCF-Bindungen, finden Sie unter [WCF-Bindungsübersicht](../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-142">For more information about WCF bindings, see [WCF Bindings Overview](../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="743a5-143">Die Adresse wird an die Basisadresse angefügt, um den Endpunkt zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="743a5-143">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="743a5-144">In diesem Code die angegebene Adresse ist "CalculatorService" aus, damit die vollqualifizierte Adresse für den Endpunkt ist `"http://localhost:8000/GettingStarted/CalculatorService"` Hinzufügen eines Dienstendpunkts ist optional, wenn mithilfe von .NET Framework 4.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="743a5-144">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"` Adding a service endpoint is optional when using .NET Framework 4.0 or later.</span></span> <span data-ttu-id="743a5-145">Wenn im Code oder in der Konfiguration keine Endpunkte hinzugefügt wurden, fügt WCF in diesen Versionen einen Standardendpunkt für jede Kombination aus Basisadresse und Vertrag hinzu, die vom Dienst implementiert wurden.</span><span class="sxs-lookup"><span data-stu-id="743a5-145">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="743a5-146">Weitere Informationen zu Endpunkten finden Sie unter [angeben einer Endpunktadresse](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-146">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="743a5-147"> zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-147"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="743a5-148">Das Hinzufügen eines Dienstendpunkts ist optional, wenn .NET Framework 4 oder höher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="743a5-148">Adding a service endpoint is optional when using .NET Framework 4 or later.</span></span> <span data-ttu-id="743a5-149">Wenn im Code oder in der Konfiguration keine Endpunkte hinzugefügt wurden, fügt WCF in diesen Versionen einen Standardendpunkt für jede Kombination aus Basisadresse und Vertrag hinzu, die vom Dienst implementiert wurden.</span><span class="sxs-lookup"><span data-stu-id="743a5-149">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="743a5-150">Weitere Informationen zu Endpunkten finden Sie unter [angeben einer Endpunktadresse](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-150">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="743a5-151"> zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-151"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
    4.  <span data-ttu-id="743a5-152">Schritt 4: Aktiviert den Metadatenaustausch.</span><span class="sxs-lookup"><span data-stu-id="743a5-152">Step 4 – Enable metadata exchange.</span></span> <span data-ttu-id="743a5-153">Clients verwenden den Metadatenaustausch, um Proxys zu generieren, die zum Aufrufen von Dienstvorgängen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="743a5-153">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="743a5-154">Zum Aktivieren von Metadatenaustausch erstellen eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior> Instanz, legen Sie es des <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> Eigenschaft `true`, und Hinzufügen des Verhaltens zur der <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  --> `System.ServiceModel.ServiceHost.Behaviors%2A` Auflistung von der <xref:System.ServiceModel.ServiceHost> Instanz.</span><span class="sxs-lookup"><span data-stu-id="743a5-154">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>  
  
    5.  <span data-ttu-id="743a5-155">Schritt 5: Öffnet den <xref:System.ServiceModel.ServiceHost>, um auf eingehende Nachrichten zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="743a5-155">Step 5 – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="743a5-156">Der Code wartet darauf, dass der Benutzer die EINGABETASTE drückt.</span><span class="sxs-lookup"><span data-stu-id="743a5-156">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="743a5-157">Wenn dies nicht erfolgt, wird die App sofort geschlossen und der Dienst heruntergefahren. Beachten Sie auch, dass ein try/catch-Block verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="743a5-157">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="743a5-158">Nachdem der <xref:System.ServiceModel.ServiceHost> instanziiert wurde, wird der gesamte sonstige Code in einen try/catch-Block eingefügt.</span><span class="sxs-lookup"><span data-stu-id="743a5-158">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="743a5-159">Weitere Informationen zu sicher ausgelöste Ausnahmen abfangen <xref:System.ServiceModel.ServiceHost>, finden Sie unter [Vermeiden von Problemen mit der Using-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span><span class="sxs-lookup"><span data-stu-id="743a5-159">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span></span>  
  
### <a name="to-verify-the-service-is-working"></a><span data-ttu-id="743a5-160">So überprüfen Sie, ob der Dienst funktioniert</span><span class="sxs-lookup"><span data-stu-id="743a5-160">To verify the service is working</span></span>  
  
1.  <span data-ttu-id="743a5-161">Führen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] die GettingStartedHost-Konsolenanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="743a5-161">Run the GettingStartedHost console application from inside [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span> <span data-ttu-id="743a5-162">Beim Ausführen unter [!INCLUDE[wv](../../../includes/wv-md.md)] und höher muss der Dienst mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="743a5-162">When running on [!INCLUDE[wv](../../../includes/wv-md.md)] and later operating systems, the service must be run with administrator privileges.</span></span> <span data-ttu-id="743a5-163">Da [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] mit Administratorrechten ausgeführt wurde, wird auch GettingStartedHost mit Administratorrechten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="743a5-163">Because [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] was run with Administrator privileges, GettingStartedHost is also run with Administrator privileges.</span></span> <span data-ttu-id="743a5-164">Sie können auch eine neue Eingabeaufforderung mit Administratorrechten starten und "service.exe" damit ausführen.</span><span class="sxs-lookup"><span data-stu-id="743a5-164">You can also start a new command prompt running it with Administrator privileges and run service.exe within it.</span></span>  
  
2.  <span data-ttu-id="743a5-165">Öffnen Sie Internet Explorer, und navigieren Sie unter `http://localhost:8000/GettingStarted/CalculatorService` zur Debuggingseite des Diensts.</span><span class="sxs-lookup"><span data-stu-id="743a5-165">Open Internet Explorer and browse to the service's debug page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="743a5-166">Beispiel</span><span class="sxs-lookup"><span data-stu-id="743a5-166">Example</span></span>  
 <span data-ttu-id="743a5-167">Das folgende Beispiel enthält den Dienstvertrag und die Implementierung aus den vorangegangenen Schritten im Lernprogramm und hostet den Dienst in einer Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="743a5-167">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>  
  
 <span data-ttu-id="743a5-168">Um dies mit einem Befehlszeilen-Compiler kompilieren, kompilieren Sie "IService1.cs" und "Service1.cs" in einer Klasse Bibliothek verweisen auf `System.ServiceModel.dll`.</span><span class="sxs-lookup"><span data-stu-id="743a5-168">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library referencing `System.ServiceModel.dll`.</span></span> <span data-ttu-id="743a5-169">Und kompilieren Sie Program.cs in eine Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="743a5-169">And compile Program.cs to a console application.</span></span>  
  
```csharp
// IService1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
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
// Service1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
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
//Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
using GettingStartedLib;  
using System.ServiceModel.Description;   
  
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
'IService1.vb  
Imports System  
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
'Service1.vb  
Imports System  
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
'Module1.vb  
Imports System  
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
>  <span data-ttu-id="743a5-170">Dienste wie dieser müssen dazu berechtigt sein, HTTP-Adressen auf dem Computer zum Überwachen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="743a5-170">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="743a5-171">Administratorkonten verfügen über diese Berechtigung, anderen Konten muss jedoch die Berechtigung für HTTP-Namespaces erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="743a5-171">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="743a5-172">zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-172"> how to configure namespace reservations, see [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="743a5-173">Wird der Dienst unter [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] ausgeführt, muss "service.exe" über Administratorrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="743a5-173">When running under [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], the service.exe must be run with administrator privileges.</span></span>  
  
 <span data-ttu-id="743a5-174">Der Dienst wird nun ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="743a5-174">Now the service is running.</span></span> <span data-ttu-id="743a5-175">Fahren Sie mit [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-175">Proceed to [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="743a5-176">Informationen zur Problembehandlung finden Sie unter [Problembehandlung für das Lernprogramm für erste Schritte](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-176">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="743a5-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="743a5-177">See Also</span></span>  
 [<span data-ttu-id="743a5-178">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="743a5-178">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="743a5-179">Selbsthosting</span><span class="sxs-lookup"><span data-stu-id="743a5-179">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
