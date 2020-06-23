---
title: 'Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung'
description: Erfahren Sie, wie Sie einen WCF-Dienst in einer verwalteten Anwendung hosten, indem Sie einen selbst gehosteten Dienst erstellen und testen.
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 7d1d61b683f60a6c643d2a2f03d367a6ae6c6c15
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246167"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="406b0-103">Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten App</span><span class="sxs-lookup"><span data-stu-id="406b0-103">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="406b0-104">Wenn ein Dienst in einer verwalteten Anwendung gehostet werden soll, betten Sie den Code für den Dienst in den verwalteten Anwendungscode ein, definieren Sie entweder imperativ im Code, deklarativ über die Konfiguration oder mithilfe der Standardendpunkte einen Endpunkt für den Dienst, und erstellen Sie dann eine Instanz von <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="406b0-104">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="406b0-105">Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz auf, um den Empfang von Nachrichten zu starten.</span><span class="sxs-lookup"><span data-stu-id="406b0-105">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="406b0-106">Damit wird ein Listener für den Dienst erstellt und geöffnet</span><span class="sxs-lookup"><span data-stu-id="406b0-106">This creates and opens the listener for the service.</span></span> <span data-ttu-id="406b0-107">Diese Art des Hostings wird häufig auch als "Selbsthosting" bezeichnet, weil die verwaltete Anwendung selbst die für das Hosting erforderlichen Vorgänge ausführt.</span><span class="sxs-lookup"><span data-stu-id="406b0-107">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="406b0-108">Um den Dienst zu schließen, rufen Sie die <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="406b0-108">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="406b0-109">Ein Dienst kann auch in einem verwalteten Windows-Dienst in Internetinformationsdienste (IIS) oder in Windows Process Activation Service (WAS) gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="406b0-109">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="406b0-110">Weitere Informationen zu [Hostingoptionen](hosting-services.md)für einen Dienst finden Sie unter Hosting-Dienste.</span><span class="sxs-lookup"><span data-stu-id="406b0-110">For more information about hosting options for a service, see [Hosting Services](hosting-services.md).</span></span>

<span data-ttu-id="406b0-111">Dienste in einer verwalteten Anwendung zu hosten ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt.</span><span class="sxs-lookup"><span data-stu-id="406b0-111">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="406b0-112">Weitere Informationen zum Hosting von Diensten in verwalteten Anwendungen finden Sie unter [Hosting in einer verwalteten Anwendung](./feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="406b0-112">For more information about hosting services in managed applications, see [Hosting in a Managed Application](./feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="406b0-113">Im folgenden Verfahren wird das Implementieren eines selbst gehosteten Diensts in einer Konsolenanwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="406b0-113">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="406b0-114">Erstellen eines selbst gehosteten Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="406b0-114">Create a self-hosted service</span></span>

1. <span data-ttu-id="406b0-115">Erstellen Sie eine neue Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="406b0-115">Create a new console application:</span></span>

   1. <span data-ttu-id="406b0-116">Öffnen Sie Visual Studio, **New**und wählen Sie  >  im Menü **Datei** die Option neues**Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="406b0-116">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="406b0-117">Wählen Sie in der Liste **installierte Vorlagen** die Option **Visual c#** oder **Visual Basic**aus, und wählen Sie dann **Windows-Desktop**aus.</span><span class="sxs-lookup"><span data-stu-id="406b0-117">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="406b0-118">Wählen Sie die **Konsolen-App** -Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="406b0-118">Select the **Console App** template.</span></span> <span data-ttu-id="406b0-119">Geben `SelfHost` Sie in das Feld **Name** ein, und **Klicken**Sie dann auf OK.</span><span class="sxs-lookup"><span data-stu-id="406b0-119">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="406b0-120">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **SelfHost** , und wählen Sie **Verweis hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="406b0-120">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="406b0-121">Wählen Sie **System. Service Model** auf der Registerkarte **.net** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="406b0-121">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="406b0-122">Wenn das **Projektmappen-Explorer** Fenster nicht sichtbar ist, wählen Sie im Menü **Ansicht** die Option **Projektmappen-Explorer** aus.</span><span class="sxs-lookup"><span data-stu-id="406b0-122">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="406b0-123">Doppelklicken Sie in **Projektmappen-Explorer** auf **Program.cs** oder **Module1. vb** , um die Datei im Code Fenster zu öffnen, wenn Sie nicht bereits geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="406b0-123">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="406b0-124">Fügen Sie am Anfang der Datei die folgenden-Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="406b0-124">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="406b0-125">Definieren und implementieren Sie einen Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="406b0-125">Define and implement a service contract.</span></span> <span data-ttu-id="406b0-126">In diesem Beispiel wird ein `HelloWorldService`-Element definiert, das auf Grundlage der Eingabe in den Dienst eine Nachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="406b0-126">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="406b0-127">Weitere Informationen zum Definieren und Implementieren einer Dienst Schnittstelle finden Sie unter Gewusst [wie: Definieren eines Dienstvertrags](how-to-define-a-wcf-service-contract.md) und Gewusst [wie: Implementieren eines Dienstvertrags](how-to-implement-a-wcf-contract.md).</span><span class="sxs-lookup"><span data-stu-id="406b0-127">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="406b0-128">Erstellen Sie am Beginn der `Main`-Methode eine Instanz der <xref:System.Uri>-Klasse mit der Basisadresse des Diensts.</span><span class="sxs-lookup"><span data-stu-id="406b0-128">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="406b0-129">Erstellen Sie eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse, wobei Sie ein <xref:System.Type>-Objekt, das den Diensttyp darstellt, und den URI (Uniform Resource Identifier) der Basisadresse <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29> übergeben.</span><span class="sxs-lookup"><span data-stu-id="406b0-129">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="406b0-130">Aktivieren Sie die Veröffentlichung von Metadaten, und rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode für das <xref:System.ServiceModel.ServiceHost>-Objekt auf, um den Dienst zu initialisieren und auf den Empfang von Nachrichten vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="406b0-130">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="406b0-131">In diesem Beispiel werden Standardendpunkte verwendet. Für diesen Dienst ist keine Konfigurationsdatei erforderlich.</span><span class="sxs-lookup"><span data-stu-id="406b0-131">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="406b0-132">Wenn keine Endpunkte konfiguriert sind, wird von der Laufzeit ein Standardendpunkt für alle Basisadressen in jedem Dienstvertrag hinzugefügt, der vom Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="406b0-132">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="406b0-133">Weitere Informationen zu Standard Endpunkten finden Sie unter [vereinfachte Konfiguration](simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](./samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="406b0-133">For more information about default endpoints, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="406b0-134">Drücken Sie **STRG** + **UMSCHALT** + **B** , um die Projekt Mappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="406b0-134">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="406b0-135">Testen des Diensts</span><span class="sxs-lookup"><span data-stu-id="406b0-135">Test the service</span></span>

1. <span data-ttu-id="406b0-136">Drücken Sie **STRG** + **F5** , um den Dienst auszuführen.</span><span class="sxs-lookup"><span data-stu-id="406b0-136">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="406b0-137">Öffnen Sie den **WCF-Test Client**.</span><span class="sxs-lookup"><span data-stu-id="406b0-137">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="406b0-138">Öffnen Sie zum Öffnen des **WCF-Test Clients**Developer-Eingabeaufforderung für Visual Studio, und führen Sie **WcfTestClient.exe**aus.</span><span class="sxs-lookup"><span data-stu-id="406b0-138">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="406b0-139">Wählen Sie im Menü **Datei** die Option **Dienst hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="406b0-139">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="406b0-140">Geben `http://localhost:8080/hello` Sie in das Feld Adresse ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="406b0-140">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="406b0-141">Stellen Sie sicher, dass der Dienst ausgeführt wird, oder ein Fehler tritt bei diesem Schritt auf.</span><span class="sxs-lookup"><span data-stu-id="406b0-141">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="406b0-142">Haben Sie die Basisadresse im Code geändert, verwenden Sie in diesem Schritt die geänderte Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="406b0-142">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="406b0-143">Doppelklicken Sie unter dem Knoten **meine Dienstprojekte** auf " **sayHello** ".</span><span class="sxs-lookup"><span data-stu-id="406b0-143">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="406b0-144">Geben Sie den Namen in die Spalte **Wert** in der Liste **Anforderung** ein, und klicken Sie auf **aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="406b0-144">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="406b0-145">In der **Antwort** Liste wird eine Antwortnachricht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="406b0-145">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="406b0-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="406b0-146">Example</span></span>

<span data-ttu-id="406b0-147">Im folgenden Beispiel wird ein <xref:System.ServiceModel.ServiceHost>-Objekt als Host für einen Dienst des Typs `HelloWorldService` erstellt, und dann wird die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="406b0-147">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="406b0-148">Im Code wird eine Basisadresse bereitgestellt, die Metadatenveröffentlichung ist aktiviert, und Standardendpunkte werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="406b0-148">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="406b0-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="406b0-149">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="406b0-150">Vorgehensweise: Hosten eines WCF-Diensts in IIS</span><span class="sxs-lookup"><span data-stu-id="406b0-150">How to: Host a WCF Service in IIS</span></span>](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="406b0-151">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="406b0-151">Self-Host</span></span>](./samples/self-host.md)
- [<span data-ttu-id="406b0-152">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="406b0-152">Hosting Services</span></span>](hosting-services.md)
- [<span data-ttu-id="406b0-153">Vorgehensweise: Definieren eines Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="406b0-153">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="406b0-154">Vorgehensweise: Implementieren eines WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="406b0-154">How to: Implement a Service Contract</span></span>](how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="406b0-155">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="406b0-155">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="406b0-156">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="406b0-156">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="406b0-157">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="406b0-157">System-Provided Bindings</span></span>](system-provided-bindings.md)
