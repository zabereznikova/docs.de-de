---
title: 'Gewusst wie: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: e2bf16bd07c7ac9d918a4ae95d7f4aa185d436ec
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44227180"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="9aba4-102">Gewusst wie: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts</span><span class="sxs-lookup"><span data-stu-id="9aba4-102">How to: Host and Run a Basic Windows Communication Foundation Service</span></span>
<span data-ttu-id="9aba4-103">Dies ist die Dritte von sechs Aufgaben, die zum Erstellen einer WCF-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9aba4-103">This is the third of six tasks required to create a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="9aba4-104">Eine Übersicht über alle sechs Aufgaben finden Sie im Artikel [Getting Started Tutorial (Tutorial: Erste Schritte)](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="9aba4-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="9aba4-105">In diesem Artikel wird beschrieben, wie ein WCF-Dienst in einer Konsolenanwendung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="9aba4-105">This topic describes how to host a Windows Communication Foundation (WCF) service in a console application.</span></span> <span data-ttu-id="9aba4-106">Dieses Verfahren umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="9aba4-106">This procedure consists of the following steps:</span></span>  
  
-   <span data-ttu-id="9aba4-107">Erstellen eines Konsolenanwendungsprojekts zum Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="9aba4-107">Create a console application project to host the service.</span></span>  
  
-   <span data-ttu-id="9aba4-108">Erstellen eines Diensthosts für den Dienst</span><span class="sxs-lookup"><span data-stu-id="9aba4-108">Create a service host for the service.</span></span>  
  
-   <span data-ttu-id="9aba4-109">Aktivieren des Metadatenaustauschs</span><span class="sxs-lookup"><span data-stu-id="9aba4-109">Enable metadata exchange.</span></span>  
  
-   <span data-ttu-id="9aba4-110">Öffnen des Diensthosts</span><span class="sxs-lookup"><span data-stu-id="9aba4-110">Open the service host.</span></span>  
  
 <span data-ttu-id="9aba4-111">Eine vollständige Liste des für diese Aufgabe geschriebenen Codes wird in einem Beispiel im Anschluss an das Verfahren bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9aba4-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="9aba4-112">So erstellen Sie eine neue Konsolenanwendung zum Hosten des Diensts</span><span class="sxs-lookup"><span data-stu-id="9aba4-112">To create a new console application to host the service</span></span>  
  
1.  <span data-ttu-id="9aba4-113">Erstellen Sie ein neues Konsolenanwendungsprojekt, indem Sie mit der rechten Maustaste auf die Projektmappe „Erste Schritte“ klicken und dann **Hinzufügen** und **Neues Projekt** auswählen.</span><span class="sxs-lookup"><span data-stu-id="9aba4-113">Create a new Console Application project by right-clicking on the Getting Started solution, selecting, **Add**, **New Project**.</span></span> <span data-ttu-id="9aba4-114">Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** auf der linken Seite des Dialogfelds unter **C#** oder **VB** die Option **Windows** aus.</span><span class="sxs-lookup"><span data-stu-id="9aba4-114">In the **Add New Project** dialog on the left hand side of the dialog select **Windows** under **C#** or **VB**.</span></span> <span data-ttu-id="9aba4-115">Wählen Sie im mittleren Abschnitt des Dialogfelds **Konsolenanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="9aba4-115">In the center section of the dialog select **Console Application**.</span></span> <span data-ttu-id="9aba4-116">Nennen Sie das Projekt GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="9aba4-116">Name the project GettingStartedHost.</span></span>  
  
2.  <span data-ttu-id="9aba4-117">Legen Sie das Zielframework des GettingStartedHost-Projekts auf .NET Framework 4.5 fest, indem Sie im Projektmappen-Explorer mit der rechten Maustaste auf **GettingStartedHost** klicken und **Eigenschaften** auswählen.</span><span class="sxs-lookup"><span data-stu-id="9aba4-117">Set the target framework of the GettingStartedHost project to .NET Framework 4.5 by right clicking on **GettingStartedHost** in the Solution Explorer and selecting **Properties**.</span></span> <span data-ttu-id="9aba4-118">Wählen Sie im Dropdownfeld **Zielframework** **.NET Framework 4.5** aus.</span><span class="sxs-lookup"><span data-stu-id="9aba4-118">In the dropdown box labeled **Target Framework** select **.NET Framework 4.5**.</span></span> <span data-ttu-id="9aba4-119">Das Festlegen des Zielframeworks für ein VB-Projekt weicht etwas davon ab. Klicken Sie im Eigenschaftendialogfeld des GettingStartedHost-Projekts links im Bildschirm auf die Registerkarte **Kompilieren**, und klicken Sie dann unten links im Dialogfeld auf die Schaltfläche **Erweiterte Kompilierungsoptionen**.</span><span class="sxs-lookup"><span data-stu-id="9aba4-119">Setting the target framework for a VB project is a little different, in the GettingStartedHost project properties dialog, click the **Compile** tab on the left-hand side of the screen, and then click the **Advanced Compile Options** button at the lower left-hand corner of the dialog.</span></span> <span data-ttu-id="9aba4-120">Wählen Sie dann **.NET Framework 4.5** im Dropdownfeld **Zielframework** aus.</span><span class="sxs-lookup"><span data-stu-id="9aba4-120">Then select **.NET Framework 4.5** in the dropdown box labeled **Target Framework**.</span></span>  
  
     <span data-ttu-id="9aba4-121">Das Festlegen des Zielframeworks führt dazu, dass die Projektmappe von [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] neu geladen wird. Klicken Sie auf **OK**, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="9aba4-121">Setting the target framework will cause [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] to reload the solution, press **OK** when prompted.</span></span>  
  
3.  <span data-ttu-id="9aba4-122">Fügen Sie dem GettingStartedHost-Projekt einen Verweis auf das GettingStartedLib-Projekt hinzu, indem Sie im Projektmappen-Explorer unterhalb des GettingStartedHost-Projekts mit der rechten Maustaste auf den Ordner **Verweise** klicken und **Verweis hinzufügen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="9aba4-122">Add a reference to the GettingStartedLib project to the GettingStartedHost project by right clicking on the **References** folder under the GettingStartedHost project in the solution explorer and select **Add Reference**.</span></span> <span data-ttu-id="9aba4-123">Wählen Sie links im Dialogfeld **Verweis hinzufügen** **Projektmappe** und im mittleren Abschnitt „GettingStartedLib“ aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9aba4-123">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog and select GettingStartedLib in the center section of the dialog and click **Add**.</span></span> <span data-ttu-id="9aba4-124">Dadurch werden die in GettingStartedLib definierten Typen für das GettingStartedHost-Projekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9aba4-124">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>  
  
4.  <span data-ttu-id="9aba4-125">Fügen Sie dem GettingStartedHost-Projekt einen Verweis auf System.ServiceModel hinzu, indem Sie im Projektmappen-Explorer unter dem GettingStartedHost-Projekt mit der rechten Maustaste auf den Ordner **Verweis** klicken und **Verweis hinzufügen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="9aba4-125">Add a reference to System.ServiceModel to the GettingStartedHost project by right-clicking the **Reference** folder under the GettingStartedHost project in Solution Explorer and select **Add** Reference.</span></span> <span data-ttu-id="9aba4-126">Wählen Sie links im Dialogfeld **Verweis hinzufügen** **Framework** aus.</span><span class="sxs-lookup"><span data-stu-id="9aba4-126">In the **Add Reference** dialog select **Framework** on the left-hand side of the dialog.</span></span> <span data-ttu-id="9aba4-127">Geben Sie im Textfeld Assemblys suchen`System.ServiceModel` ein.</span><span class="sxs-lookup"><span data-stu-id="9aba4-127">In the Search Assemblies textbox, type in `System.ServiceModel`.</span></span> <span data-ttu-id="9aba4-128">Wählen Sie im mittleren Abschnitt des Dialogfelds **System.ServiceModel** aus, klicken Sie auf die Schaltfläche **Hinzufügen** und dann auf die Schaltfläche **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9aba4-128">In the center section of the dialog select **System.ServiceModel**, click the **Add** button, and click the **Close** button.</span></span> <span data-ttu-id="9aba4-129">Speichern Sie die Projektmappe, indem Sie unterhalb des Hauptmenüs auf die Schaltfläche Alle speichern klicken.</span><span class="sxs-lookup"><span data-stu-id="9aba4-129">Save the solution by clicking the Save All button below the main menu.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="9aba4-130">So hosten Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="9aba4-130">To host the service</span></span>  
  
-   <span data-ttu-id="9aba4-131">Öffnen Sie die Datei Program.cs oder Module.vb, und geben Sie den folgenden Code ein:</span><span class="sxs-lookup"><span data-stu-id="9aba4-131">Open the Program.cs or Module.vb file and enter the following code:</span></span>  
  
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
  
    1.  <span data-ttu-id="9aba4-132">Schritt 1: Erstellt eine Instanz der URI-Klasse, die die Basisadresse des Diensts enthält.</span><span class="sxs-lookup"><span data-stu-id="9aba4-132">Step 1 - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="9aba4-133">Dienste werden über eine URL identifiziert, die eine Basisadresse und einen optionalen URI enthält.</span><span class="sxs-lookup"><span data-stu-id="9aba4-133">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="9aba4-134">Die Basisadresse ist wie folgt formatiert: [Transport]://[Computername oder Domäne][:optionaler Port #]/[optionales URI-Segment]. Für die Basisadresse des Rechnerdiensts werden HTTP-Transport, localhost, Port 8000 und das URI-Segment „GettingStarted“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="9aba4-134">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>  
  
    2.  <span data-ttu-id="9aba4-135">Schritt 2: Erstellt eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse zum Hosten des Diensts.</span><span class="sxs-lookup"><span data-stu-id="9aba4-135">Step 2 – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="9aba4-136">Der Konstruktor akzeptiert zwei Parameter: den Typ der Klasse, die den Dienstvertrag implementiert, und die Basisadresse des Diensts.</span><span class="sxs-lookup"><span data-stu-id="9aba4-136">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>  
  
    3.  <span data-ttu-id="9aba4-137">Schritt 3: Erstellt eine neue <xref:System.ServiceModel.Description.ServiceEndpoint>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="9aba4-137">Step 3 – Creates a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="9aba4-138">Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen.</span><span class="sxs-lookup"><span data-stu-id="9aba4-138">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="9aba4-139">Der <xref:System.ServiceModel.Description.ServiceEndpoint>-Konstruktor akzeptiert daher den Schnittstellentyp des Dienstvertrags, eine Bindung und eine Adresse.</span><span class="sxs-lookup"><span data-stu-id="9aba4-139">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="9aba4-140">Der Dienstvertrag ist `ICalculator`, den Sie definiert haben und im Diensttyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="9aba4-140">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="9aba4-141">Die in diesem Beispiel verwendete Bindung ist <xref:System.ServiceModel.WSHttpBinding>. Dies ist eine integrierte Bindung, die für die Verbindung mit Endpunkten verwendet wird, die den WS-\*-Spezifikationen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9aba4-141">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="9aba4-142">Weitere Informationen zu WCF-Bindungen finden Sie unter [WCF Bindings Overview (Übersicht über WCF-Bindungen)](../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9aba4-142">For more information about WCF bindings, see [WCF Bindings Overview](../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="9aba4-143">Die Adresse wird an die Basisadresse angefügt, um den Endpunkt zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="9aba4-143">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="9aba4-144">In diesem Code angegebene Adresse ist "CalculatorService", daher ist die vollqualifizierte Adresse für den Endpunkt `"http://localhost:8000/GettingStarted/CalculatorService"`.</span><span class="sxs-lookup"><span data-stu-id="9aba4-144">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"`.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="9aba4-145">Das Hinzufügen eines Dienstendpunkts ist optional, wenn .NET Framework 4 oder höher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9aba4-145">Adding a service endpoint is optional when using .NET Framework 4 or later.</span></span> <span data-ttu-id="9aba4-146">Wenn im Code oder in der Konfiguration keine Endpunkte hinzugefügt wurden, fügt WCF in diesen Versionen einen Standardendpunkt für jede Kombination aus Basisadresse und Vertrag hinzu, die vom Dienst implementiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9aba4-146">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="9aba4-147">Weitere Informationen zu Standardendpunkten finden Sie unter [Specifying an Endpoint Address (Angeben einer Endpunktadresse)](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="9aba4-147">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="9aba4-148">Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9aba4-148">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
    4.  <span data-ttu-id="9aba4-149">Schritt 4: Aktiviert den Metadatenaustausch.</span><span class="sxs-lookup"><span data-stu-id="9aba4-149">Step 4 – Enable metadata exchange.</span></span> <span data-ttu-id="9aba4-150">Clients verwenden den Metadatenaustausch, um Proxys zu generieren, die zum Aufrufen von Dienstvorgängen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9aba4-150">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="9aba4-151">Erstellen Sie zum Aktivieren von Metadatenaustausch eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Instanz, legen Sie ihre <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf `true` fest, und fügen Sie das Verhalten der <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A`-Auflistung der <xref:System.ServiceModel.ServiceHost>-Instanz hinzu.</span><span class="sxs-lookup"><span data-stu-id="9aba4-151">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>  
  
    5.  <span data-ttu-id="9aba4-152">Schritt 5: Öffnet den <xref:System.ServiceModel.ServiceHost>, um auf eingehende Nachrichten zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="9aba4-152">Step 5 – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="9aba4-153">Der Code wartet darauf, dass der Benutzer die EINGABETASTE drückt.</span><span class="sxs-lookup"><span data-stu-id="9aba4-153">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="9aba4-154">Wenn dies nicht erfolgt, wird die App sofort geschlossen und der Dienst heruntergefahren. Beachten Sie auch, dass ein try/catch-Block verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9aba4-154">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="9aba4-155">Nachdem der <xref:System.ServiceModel.ServiceHost> instanziiert wurde, wird der gesamte sonstige Code in einen try/catch-Block eingefügt.</span><span class="sxs-lookup"><span data-stu-id="9aba4-155">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="9aba4-156">Weitere Informationen zum sicheren Abfangen von Ausnahmen, die von <xref:System.ServiceModel.ServiceHost> ausgelöst werden, finden Sie unter [Avoiding Problems with the Using Statement (Umgehen von Problemen mit der Using-Anweisung)](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9aba4-156">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9aba4-157">Bearbeiten Sie die Datei "App.config" im GettingStartedLib entsprechend die Änderungen im Code vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="9aba4-157">Edit App.config in GettingStartedLib to reflect the changes made in code:</span></span> 
> 1. <span data-ttu-id="9aba4-158">Ändern Sie Zeile 14 `<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="9aba4-158">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
> 2. <span data-ttu-id="9aba4-159">Ändern Sie Zeile 17 in `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="9aba4-159">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
> 3. <span data-ttu-id="9aba4-160">Ändern Sie Zeile 22 in `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="9aba4-160">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>
        
### <a name="to-verify-the-service-is-working"></a><span data-ttu-id="9aba4-161">So überprüfen Sie, ob der Dienst funktioniert</span><span class="sxs-lookup"><span data-stu-id="9aba4-161">To verify the service is working</span></span>  
  
1.  <span data-ttu-id="9aba4-162">Führen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] die GettingStartedHost-Konsolenanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="9aba4-162">Run the GettingStartedHost console application from inside [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span> <span data-ttu-id="9aba4-163">Beim Ausführen unter [!INCLUDE[wv](../../../includes/wv-md.md)] und höher muss der Dienst mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9aba4-163">When running on [!INCLUDE[wv](../../../includes/wv-md.md)] and later operating systems, the service must be run with administrator privileges.</span></span> <span data-ttu-id="9aba4-164">Da Visual Studio mit Administratorrechten ausgeführt wurde, wird auch GettingStartedHost mit Administratorrechten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9aba4-164">Because Visual Studio was run with Administrator privileges, GettingStartedHost is also run with Administrator privileges.</span></span> <span data-ttu-id="9aba4-165">Sie können auch eine neue Eingabeaufforderung mit Administratorrechten starten und "service.exe" damit ausführen.</span><span class="sxs-lookup"><span data-stu-id="9aba4-165">You can also start a new command prompt running it with Administrator privileges and run service.exe within it.</span></span>  
  
2.  <span data-ttu-id="9aba4-166">Öffnen Sie Internet Explorer, und navigieren Sie unter `http://localhost:8000/GettingStarted/CalculatorService` zur Debuggingseite des Diensts.</span><span class="sxs-lookup"><span data-stu-id="9aba4-166">Open Internet Explorer and browse to the service's debug page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9aba4-167">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9aba4-167">Example</span></span>  
 <span data-ttu-id="9aba4-168">Das folgende Beispiel enthält den Dienstvertrag und die Implementierung aus den vorangegangenen Schritten im Lernprogramm und hostet den Dienst in einer Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="9aba4-168">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>  
  
 <span data-ttu-id="9aba4-169">Zum Kompilieren mit einem Befehlszeilencompiler kompilieren Sie IService1.cs und Service1.cs in eine Klassenbibliothek, die auf `System.ServiceModel.dll` verweist.</span><span class="sxs-lookup"><span data-stu-id="9aba4-169">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library referencing `System.ServiceModel.dll`.</span></span> <span data-ttu-id="9aba4-170">Und kompilieren Sie Program.cs in eine Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="9aba4-170">And compile Program.cs to a console application.</span></span>  
  
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
>  <span data-ttu-id="9aba4-171">Dienste wie dieser müssen dazu berechtigt sein, HTTP-Adressen auf dem Computer zum Überwachen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="9aba4-171">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="9aba4-172">Administratorkonten verfügen über diese Berechtigung, anderen Konten muss jedoch die Berechtigung für HTTP-Namespaces erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="9aba4-172">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="9aba4-173">Weitere Informationen zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS (Konfigurieren von HTTP und HTTPS)](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="9aba4-173">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="9aba4-174">Wird der Dienst unter Visual Studio ausgeführt, muss „service.exe“ mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9aba4-174">When running under Visual Studio, the service.exe must be run with administrator privileges.</span></span>  
  
 <span data-ttu-id="9aba4-175">Der Dienst wird nun ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9aba4-175">Now the service is running.</span></span> <span data-ttu-id="9aba4-176">Fahren Sie mit [How to: Create a Client (Vorgehensweise: Erstellen eines Clients)](../../../docs/framework/wcf/how-to-create-a-wcf-client.md) fort.</span><span class="sxs-lookup"><span data-stu-id="9aba4-176">Proceed to [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="9aba4-177">Informationen zur Problembehandlung finden Sie unter [Troubleshooting the Getting Started Tutorial (Problembehandlung für das Tutorial „Erste Schritte“)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="9aba4-177">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aba4-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9aba4-178">See Also</span></span>  
 [<span data-ttu-id="9aba4-179">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="9aba4-179">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="9aba4-180">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="9aba4-180">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
