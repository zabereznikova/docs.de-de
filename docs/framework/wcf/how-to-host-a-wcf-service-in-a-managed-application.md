---
title: 'Gewusst wie: Hosten eines WCF-Diensts in einer verwalteten Anwendung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
caps.latest.revision: "42"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ca834c097f7e8cea14337fece651b2b3059d06b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-host-a-wcf-service-in-a-managed-application"></a><span data-ttu-id="2bb7d-102">Gewusst wie: Hosten eines WCF-Diensts in einer verwalteten Anwendung</span><span class="sxs-lookup"><span data-stu-id="2bb7d-102">How to: Host a WCF Service in a Managed Application</span></span>
<span data-ttu-id="2bb7d-103">Wenn ein Dienst in einer verwalteten Anwendung gehostet werden soll, betten Sie den Code für den Dienst in den verwalteten Anwendungscode ein, definieren Sie entweder imperativ im Code, deklarativ über die Konfiguration oder mithilfe der Standardendpunkte einen Endpunkt für den Dienst, und erstellen Sie dann eine Instanz von <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="2bb7d-104">Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz auf, um den Empfang von Nachrichten zu starten.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="2bb7d-105">Damit wird ein Listener für den Dienst erstellt und geöffnet</span><span class="sxs-lookup"><span data-stu-id="2bb7d-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="2bb7d-106">Diese Art des Hostings wird häufig auch als "Selbsthosting" bezeichnet, weil die verwaltete Anwendung selbst die für das Hosting erforderlichen Vorgänge ausführt.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="2bb7d-107">Um den Dienst zu schließen, rufen Sie die <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="2bb7d-108">Ein Dienst kann auch in einem verwalteten Windows-Dienst in Internetinformationsdienste (IIS) oder in Windows Process Activation Service (WAS) gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="2bb7d-109">Optionen für einen Dienst zum Hosten, finden Sie unter [Hostingdienste](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="2bb7d-109"> hosting options for a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
 <span data-ttu-id="2bb7d-110">Dienste in einer verwalteten Anwendung zu hosten ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="2bb7d-111">Hosten von Diensten in verwalteten Anwendungen, finden Sie unter [Hosten in einer verwalteten Anwendung](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="2bb7d-111"> hosting services in managed applications, see [Hosting in a Managed Application](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>  
  
 <span data-ttu-id="2bb7d-112">Im folgenden Verfahren wird das Implementieren eines selbst gehosteten Diensts in einer Konsolenanwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>  
  
### <a name="to-create-a-self-hosted-service"></a><span data-ttu-id="2bb7d-113">So erstellen Sie einen selbst gehosteten Dienst</span><span class="sxs-lookup"><span data-stu-id="2bb7d-113">To create a self-hosted service</span></span>  
  
1.  <span data-ttu-id="2bb7d-114">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] , und wählen Sie **neu**, **Projekt...**  aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-114">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and select **New**, **Project...** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="2bb7d-115">In der **installierte Vorlagen** Liste **Visual C#-**, **Windows** oder **Visual Basic**, **Windows**.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-115">In the **Installed Templates** list, select **Visual C#**, **Windows** or **Visual Basic**, **Windows**.</span></span> <span data-ttu-id="2bb7d-116">Je nach Ihrer [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] Einstellungen, eine oder beide Optionen möglicherweise nicht unter die **andere Sprachen** Knoten in der **installierte Vorlagen** Liste.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-116">Depending on your [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] settings, one or both of these may be under the **Other Languages** node in the **Installed Templates** list.</span></span>  
  
3.  <span data-ttu-id="2bb7d-117">Wählen Sie **Konsolenanwendung** aus der **Windows** Liste.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-117">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="2bb7d-118">Typ `SelfHost` in der **Namen** Feld, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-118">Type `SelfHost` in the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="2bb7d-119">Mit der rechten Maustaste **SelfHost** in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen...** . Wählen Sie **System.ServiceModel** aus der **.NET** Registerkarte, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference...**. Select **System.ServiceModel** from the **.NET** tab and click **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="2bb7d-120">Wenn die **Projektmappen-Explorer** Fenster ist nicht sichtbar ist, wählen **Projektmappen-Explorer** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-120">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="2bb7d-121">Doppelklicken Sie auf **"Program.cs"** oder **"Module1.vb"** in **Projektmappen-Explorer** im Codefenster zu öffnen, wenn er nicht bereits geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-121">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window if it is not already open.</span></span> <span data-ttu-id="2bb7d-122">Fügen Sie am Anfang der Datei die folgenden Anweisungen ein.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-122">Add the following statements at the top of the file.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]  
  
6.  <span data-ttu-id="2bb7d-123">Definieren und implementieren Sie einen Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-123">Define and implement a service contract.</span></span> <span data-ttu-id="2bb7d-124">In diesem Beispiel wird ein `HelloWorldService`-Element definiert, das auf Grundlage der Eingabe in den Dienst eine Nachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-124">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]  
  
    > [!NOTE]
    >  [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="2bb7d-125">zum Definieren und implementieren eine Dienstschnittstelle finden Sie unter [wie: Definieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) und [Vorgehensweise: Implementieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span><span class="sxs-lookup"><span data-stu-id="2bb7d-125"> how to define and implement a service interface, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span></span>  
  
7.  <span data-ttu-id="2bb7d-126">Erstellen Sie am Beginn der `Main`-Methode eine Instanz der <xref:System.Uri>-Klasse mit der Basisadresse des Diensts.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-126">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]  
  
8.  <span data-ttu-id="2bb7d-127">Erstellen Sie eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse, wobei Sie ein <xref:System.Type>-Objekt, das den Diensttyp darstellt, und den URI (Uniform Resource Identifier) der Basisadresse <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29> übergeben.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-127">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="2bb7d-128">Aktivieren Sie die Veröffentlichung von Metadaten, und rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode für das <xref:System.ServiceModel.ServiceHost>-Objekt auf, um den Dienst zu initialisieren und auf den Empfang von Nachrichten vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-128">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]       
  
    > [!NOTE]
    >  <span data-ttu-id="2bb7d-129">In diesem Beispiel werden Standardendpunkte verwendet. Für diesen Dienst ist keine Konfigurationsdatei erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-129">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="2bb7d-130">Wenn keine Endpunkte konfiguriert sind, wird von der Laufzeit ein Standardendpunkt für alle Basisadressen in jedem Dienstvertrag hinzugefügt, der vom Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-130">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="2bb7d-131">Standardendpunkte, finden Sie unter [vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="2bb7d-131"> default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
9. <span data-ttu-id="2bb7d-132">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-132">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
### <a name="to-test-the-service"></a><span data-ttu-id="2bb7d-133">So testen Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="2bb7d-133">To test the service</span></span>  
  
1.  <span data-ttu-id="2bb7d-134">Drücken Sie STRG+F5, um den Dienst auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-134">Press Ctrl + F5 to run the service.</span></span>  
  
2.  <span data-ttu-id="2bb7d-135">Open **WCF-Testclient**.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-135">Open **WCF Test Client**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="2bb7d-136">So öffnen **WCF-Testclient**Öffnen einer [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] -Eingabeaufforderung, und führen Sie **WcfTestClient.exe**.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-136">To open **WCF Test Client**, open a [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] command prompt and execute **WcfTestClient.exe**.</span></span>  
  
3.  <span data-ttu-id="2bb7d-137">Wählen Sie **Dienst hinzufügen...**  aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-137">Select **Add Service...** from the **File** menu.</span></span>  
  
4.  <span data-ttu-id="2bb7d-138">Typ `http://localhost:8080/hello` in das Adressfeld, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-138">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="2bb7d-139">Stellen Sie sicher, dass der Dienst ausgeführt wird, oder ein Fehler tritt bei diesem Schritt auf.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-139">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="2bb7d-140">Haben Sie die Basisadresse im Code geändert, verwenden Sie in diesem Schritt die geänderte Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-140">If you have changed the base address in the code, then use the modified base address in this step.</span></span>  
  
5.  <span data-ttu-id="2bb7d-141">Doppelklicken Sie auf **SayHello** unter der **Meine Dienstprojekte** Knoten.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-141">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="2bb7d-142">Geben Sie Ihren Namen in der **Wert** Spalte in der **anfordern** aus, und klicken Sie auf **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-142">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span> <span data-ttu-id="2bb7d-143">Erscheint nun eine Antwortnachricht die **Antwort** Liste.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-143">A reply message appears in the **Response** list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bb7d-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2bb7d-144">Example</span></span>  
 <span data-ttu-id="2bb7d-145">Im folgenden Beispiel wird ein <xref:System.ServiceModel.ServiceHost>-Objekt als Host für einen Dienst des Typs `HelloWorldService` erstellt, und dann wird die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-145">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="2bb7d-146">Im Code wird eine Basisadresse bereitgestellt, die Metadatenveröffentlichung ist aktiviert, und Standardendpunkte werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="2bb7d-146">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>  
  
 [!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
 [!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="2bb7d-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2bb7d-147">See Also</span></span>  
 <xref:System.Uri>  
 <xref:System.Configuration.ConfigurationManager.AppSettings%2A>  
 <xref:System.Configuration.ConfigurationManager>  
 [<span data-ttu-id="2bb7d-148">How to: Host a WCF Service in IIS (Vorgehensweise: Hosten eines WCF-Diensts in IIS)</span><span class="sxs-lookup"><span data-stu-id="2bb7d-148">How to: Host a WCF Service in IIS</span></span>](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)  
 [<span data-ttu-id="2bb7d-149">Selbsthosting</span><span class="sxs-lookup"><span data-stu-id="2bb7d-149">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)  
 [<span data-ttu-id="2bb7d-150">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="2bb7d-150">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="2bb7d-151">Vorgehensweise: Definieren eines Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="2bb7d-151">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 [<span data-ttu-id="2bb7d-152">Vorgehensweise: Implementieren eines WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="2bb7d-152">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [<span data-ttu-id="2bb7d-153">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="2bb7d-153">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="2bb7d-154">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="2bb7d-154">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="2bb7d-155">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="2bb7d-155">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)
