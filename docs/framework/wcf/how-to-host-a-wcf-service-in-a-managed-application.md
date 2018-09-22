---
title: 'Gewusst wie: Hosten eines WCF-Diensts in einer verwalteten Anwendung'
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 131d99457427e0818f78076d987f550a99ad7cf0
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46696287"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="4e1af-102">Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten app</span><span class="sxs-lookup"><span data-stu-id="4e1af-102">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="4e1af-103">Wenn ein Dienst in einer verwalteten Anwendung gehostet werden soll, betten Sie den Code für den Dienst in den verwalteten Anwendungscode ein, definieren Sie entweder imperativ im Code, deklarativ über die Konfiguration oder mithilfe der Standardendpunkte einen Endpunkt für den Dienst, und erstellen Sie dann eine Instanz von <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="4e1af-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="4e1af-104">Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz auf, um den Empfang von Nachrichten zu starten.</span><span class="sxs-lookup"><span data-stu-id="4e1af-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="4e1af-105">Damit wird ein Listener für den Dienst erstellt und geöffnet</span><span class="sxs-lookup"><span data-stu-id="4e1af-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="4e1af-106">Diese Art des Hostings wird häufig auch als "Selbsthosting" bezeichnet, weil die verwaltete Anwendung selbst die für das Hosting erforderlichen Vorgänge ausführt.</span><span class="sxs-lookup"><span data-stu-id="4e1af-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="4e1af-107">Um den Dienst zu schließen, rufen Sie die <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="4e1af-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="4e1af-108">Ein Dienst kann auch in einem verwalteten Windows-Dienst in Internetinformationsdienste (IIS) oder in Windows Process Activation Service (WAS) gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="4e1af-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="4e1af-109">Weitere Informationen zu den Hostoptionen für einen Dienst, finden Sie unter [Hostingdienste](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="4e1af-109">For more information about hosting options for a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>

<span data-ttu-id="4e1af-110">Dienste in einer verwalteten Anwendung zu hosten ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt.</span><span class="sxs-lookup"><span data-stu-id="4e1af-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="4e1af-111">Weitere Informationen zum Hosten von Diensten in verwalteten Anwendungen finden Sie unter [Hosten in einer verwalteten Anwendung](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="4e1af-111">For more information about hosting services in managed applications, see [Hosting in a Managed Application](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="4e1af-112">Im folgenden Verfahren wird das Implementieren eines selbst gehosteten Diensts in einer Konsolenanwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4e1af-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="4e1af-113">Erstellen Sie einen selbst gehosteten Dienst</span><span class="sxs-lookup"><span data-stu-id="4e1af-113">Create a self-hosted service</span></span>

1. <span data-ttu-id="4e1af-114">Erstellen Sie eine neue Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="4e1af-114">Create a new console application:</span></span>

   1. <span data-ttu-id="4e1af-115">Öffnen Sie Visual Studio, und wählen Sie **neu** > **Projekt** aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="4e1af-115">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="4e1af-116">In der **installierte Vorlagen** Liste **Visual C#-** oder **Visual Basic**, und wählen Sie dann **Windows Desktop**.</span><span class="sxs-lookup"><span data-stu-id="4e1af-116">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="4e1af-117">Wählen Sie die **Konsolen-App** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="4e1af-117">Select the **Console App** template.</span></span> <span data-ttu-id="4e1af-118">Typ `SelfHost` in die **Namen** Feld, und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e1af-118">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="4e1af-119">Mit der rechten Maustaste **SelfHost** in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4e1af-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="4e1af-120">Wählen Sie **System.ServiceModel** aus der **.NET** Registerkarte, und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e1af-120">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4e1af-121">Wenn die **Projektmappen-Explorer** Fenster ist nicht sichtbar ist, wählen **Projektmappen-Explorer** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="4e1af-121">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="4e1af-122">Doppelklicken Sie auf **"Program.cs"** oder **"Module1.vb"** in **Projektmappen-Explorer** , die sie im Codefenster zu öffnen, wenn es nicht bereits geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="4e1af-122">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="4e1af-123">Fügen Sie die folgenden Anweisungen am Anfang der Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="4e1af-123">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="4e1af-124">Definieren und implementieren Sie einen Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="4e1af-124">Define and implement a service contract.</span></span> <span data-ttu-id="4e1af-125">In diesem Beispiel wird ein `HelloWorldService`-Element definiert, das auf Grundlage der Eingabe in den Dienst eine Nachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4e1af-125">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="4e1af-126">Weitere Informationen zum Definieren und Implementieren einer Dienstschnittstelle finden Sie unter [wie: Definieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) und [Vorgehensweise: Implementieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span><span class="sxs-lookup"><span data-stu-id="4e1af-126">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="4e1af-127">Erstellen Sie am Beginn der `Main`-Methode eine Instanz der <xref:System.Uri>-Klasse mit der Basisadresse des Diensts.</span><span class="sxs-lookup"><span data-stu-id="4e1af-127">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="4e1af-128">Erstellen Sie eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse, wobei Sie ein <xref:System.Type>-Objekt, das den Diensttyp darstellt, und den URI (Uniform Resource Identifier) der Basisadresse <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29> übergeben.</span><span class="sxs-lookup"><span data-stu-id="4e1af-128">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="4e1af-129">Aktivieren Sie die Veröffentlichung von Metadaten, und rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode für das <xref:System.ServiceModel.ServiceHost>-Objekt auf, um den Dienst zu initialisieren und auf den Empfang von Nachrichten vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="4e1af-129">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="4e1af-130">In diesem Beispiel werden Standardendpunkte verwendet. Für diesen Dienst ist keine Konfigurationsdatei erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4e1af-130">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="4e1af-131">Wenn keine Endpunkte konfiguriert sind, wird von der Laufzeit ein Standardendpunkt für alle Basisadressen in jedem Dienstvertrag hinzugefügt, der vom Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="4e1af-131">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="4e1af-132">Weitere Informationen zu Standardendpunkten, finden Sie unter [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="4e1af-132">For more information about default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="4e1af-133">Drücken Sie **STRG**+**UMSCHALT**+**B** zum Erstellen der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="4e1af-133">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="4e1af-134">Testen Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="4e1af-134">Test the service</span></span>

1. <span data-ttu-id="4e1af-135">Drücken Sie **STRG**+**F5** zum Ausführen des Diensts.</span><span class="sxs-lookup"><span data-stu-id="4e1af-135">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="4e1af-136">Open **WCF-Testclient**.</span><span class="sxs-lookup"><span data-stu-id="4e1af-136">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4e1af-137">Zum Öffnen **WCF-Testclient**, öffnen Sie die Developer-Eingabeaufforderung für Visual Studio, und führen Sie **WcfTestClient.exe**.</span><span class="sxs-lookup"><span data-stu-id="4e1af-137">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="4e1af-138">Wählen Sie **Dienst hinzufügen** aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="4e1af-138">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="4e1af-139">Typ `http://localhost:8080/hello` in das Feld Adresse ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e1af-139">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4e1af-140">Stellen Sie sicher, dass der Dienst ausgeführt wird, oder ein Fehler tritt bei diesem Schritt auf.</span><span class="sxs-lookup"><span data-stu-id="4e1af-140">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="4e1af-141">Haben Sie die Basisadresse im Code geändert, verwenden Sie in diesem Schritt die geänderte Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="4e1af-141">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="4e1af-142">Doppelklicken Sie auf **SayHello** unter der **Meine Dienstprojekte** Knoten.</span><span class="sxs-lookup"><span data-stu-id="4e1af-142">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="4e1af-143">Geben Sie Ihren Namen in der **Wert** -Spalte in der **anfordern** aus, und klicken Sie auf **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="4e1af-143">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="4e1af-144">Eine Reply-Nachricht wird angezeigt, der **Antwort** Liste.</span><span class="sxs-lookup"><span data-stu-id="4e1af-144">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="4e1af-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4e1af-145">Example</span></span>

<span data-ttu-id="4e1af-146">Im folgenden Beispiel wird ein <xref:System.ServiceModel.ServiceHost>-Objekt als Host für einen Dienst des Typs `HelloWorldService` erstellt, und dann wird die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4e1af-146">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="4e1af-147">Im Code wird eine Basisadresse bereitgestellt, die Metadatenveröffentlichung ist aktiviert, und Standardendpunkte werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e1af-147">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="4e1af-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e1af-148">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="4e1af-149">Vorgehensweise: Hosten eines WCF-Diensts in IIS</span><span class="sxs-lookup"><span data-stu-id="4e1af-149">How to: Host a WCF Service in IIS</span></span>](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="4e1af-150">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="4e1af-150">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="4e1af-151">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="4e1af-151">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="4e1af-152">Vorgehensweise: Definieren eines Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="4e1af-152">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="4e1af-153">Vorgehensweise: Implementieren eines WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="4e1af-153">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="4e1af-154">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="4e1af-154">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="4e1af-155">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4e1af-155">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4e1af-156">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="4e1af-156">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)