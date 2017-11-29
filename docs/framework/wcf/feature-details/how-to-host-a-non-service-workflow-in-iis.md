---
title: 'Vorgehensweise: Hosten eines Nicht-Dienstworkflows in IIS'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f362562c-767d-401b-8257-916616568fd4
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 892875fb8340220dc152f91ab2239257c7b96fb8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-host-a-non-service-workflow-in-iis"></a><span data-ttu-id="84d8b-102">Vorgehensweise: Hosten eines Nicht-Dienstworkflows in IIS</span><span class="sxs-lookup"><span data-stu-id="84d8b-102">How to: Host a non-service workflow in IIS</span></span>
<span data-ttu-id="84d8b-103">Workflows, die keine Workflowdienste darstellen, können unter IIS/WAS gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="84d8b-103">Workflows that are not workflow services can be hosted under IIS/WAS.</span></span> <span data-ttu-id="84d8b-104">Dies ist hilfreich, wenn ein Workflow gehostet werden muss, der von einem anderen Benutzer geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="84d8b-104">This is useful when you need to host a workflow written by somebody else.</span></span> <span data-ttu-id="84d8b-105">Beispiel: Der Workflow-Designer wird erneut gehostet, und Benutzer können eigene Workflows erstellen.</span><span class="sxs-lookup"><span data-stu-id="84d8b-105">For example, if you rehost the workflow designer and allow users to create their own workflows.</span></span>  <span data-ttu-id="84d8b-106">Durch das Hosten eines Workflows in IIS, bei dem es sich nicht um einen Dienstworkflow handelt, wird Unterstützung für Funktionen wie die Prozesswiederverwendung, das Herunterfahren der Anwendung und ihrer Dienste bei Leerlauf, die Prozessüberwachung und die meldungsbasierte Aktivierung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="84d8b-106">Hosting non-service workflows in IIS provides support for features like process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="84d8b-107">Workflowdienste, die in IIS gehostet werden, enthalten <xref:System.ServiceModel.Activities.Receive>-Aktivitäten und werden beim Empfang einer Meldung durch IIS aktiviert.</span><span class="sxs-lookup"><span data-stu-id="84d8b-107">Workflow services hosted in IIS contain <xref:System.ServiceModel.Activities.Receive> activities and are activated when a message is received by IIS.</span></span> <span data-ttu-id="84d8b-108">Workflows, die keine Dienstworkflows sind, enthalten keine Messagingaktivitäten und können standardmäßig nicht durch Senden einer Meldung aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="84d8b-108">Non-service workflows do not contain messaging activities, and by default cannot be activated by sending a message.</span></span>  <span data-ttu-id="84d8b-109">Um eine Instanz des Workflows zu erstellen, müssen Sie eine Klasse von <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> ableiten und einen Dienstvertrag mit Vorgängen erstellen.</span><span class="sxs-lookup"><span data-stu-id="84d8b-109">You must derive a class from <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> and define a service contract that contains operations to create an instance of the workflow.</span></span> <span data-ttu-id="84d8b-110">Dieses Thema führt Sie durch das Erstellen eines einfachen Workflows, definieren einen Dienstvertrag, ein Client verwenden kann, um den Workflow zu aktivieren, und Ableiten einer Klasse von <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> verwendet den Dienstvertrag für Workflow Erstellen von Anforderungen zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="84d8b-110">This topic will walk you through creating a simple workflow, defining a service contract a client can use to activate the workflow, and deriving a class from <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> which uses the service contract to listen for workflow creating requests.</span></span>  
  
### <a name="create-a-simple-workflow"></a><span data-ttu-id="84d8b-111">Erstellen eines einfachen Workflows</span><span class="sxs-lookup"><span data-stu-id="84d8b-111">Create a simple workflow</span></span>  
  
1.  <span data-ttu-id="84d8b-112">Erstellen Sie eine neue leere [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Projektmappe mit dem Namen `CreationEndpointTest`.</span><span class="sxs-lookup"><span data-stu-id="84d8b-112">Create a new [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] empty solution called `CreationEndpointTest`.</span></span>  
  
2.  <span data-ttu-id="84d8b-113">Fügen Sie der Projektmappe ein neues Projekt für eine WCF-Workflowdienstanwendung mit dem Namen `SimpleWorkflow` hinzu.</span><span class="sxs-lookup"><span data-stu-id="84d8b-113">Add a new WCF Workflow Service Application project called `SimpleWorkflow` to the solution.</span></span> <span data-ttu-id="84d8b-114">Der Workflow-Designer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="84d8b-114">The workflow designer will open.</span></span>  
  
3.  <span data-ttu-id="84d8b-115">Löschen Sie die ReceiveRequest-Aktivität und die SendResponse-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="84d8b-115">Delete the ReceiveRequest and SendResponse activities.</span></span> <span data-ttu-id="84d8b-116">Durch diese Aktivitäten wird aus einem Workflow ein Workflowdienst.</span><span class="sxs-lookup"><span data-stu-id="84d8b-116">These activities are what makes a workflow a workflow service.</span></span> <span data-ttu-id="84d8b-117">Da im vorliegenden Fall nicht mit einem Workflowdienst gearbeitet wird, sind sie nicht länger erforderlich.</span><span class="sxs-lookup"><span data-stu-id="84d8b-117">Since we are not working with a workflow service, we no longer need them.</span></span>  
  
4.  <span data-ttu-id="84d8b-118">Legen Sie den DisplayName für die Sequenzaktivität auf "Sequenzieller Workflow".</span><span class="sxs-lookup"><span data-stu-id="84d8b-118">Set the DisplayName for the sequence activity to "Sequential Workflow".</span></span>  
  
5.  <span data-ttu-id="84d8b-119">Benennen Sie Service1.xamlx in Workflow1.xamlx um.</span><span class="sxs-lookup"><span data-stu-id="84d8b-119">Rename Service1.xamlx to Workflow1.xamlx.</span></span>  
  
6.  <span data-ttu-id="84d8b-120">Klicken Sie auf den Designer außerhalb der Sequenzaktivität, und legen Sie die Eigenschaften "Name" und "ConfigurationName" auf "Workflow1"fest.</span><span class="sxs-lookup"><span data-stu-id="84d8b-120">Click the designer outside of the sequence activity, and set the Name and ConfigurationName properties to "Workflow1"</span></span>  
  
7.  <span data-ttu-id="84d8b-121">Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität in die <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="84d8b-121">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence>.</span></span> <span data-ttu-id="84d8b-122">Die <xref:System.Activities.Statements.WriteLine> -Aktivität befindet sich der **primitive** Abschnitt der Toolbox.</span><span class="sxs-lookup"><span data-stu-id="84d8b-122">The <xref:System.Activities.Statements.WriteLine> activity can be found in the **Primitives** section of the toolbox.</span></span> <span data-ttu-id="84d8b-123">Festlegen der <xref:System.Activities.Statements.WriteLine.Text%2A> Eigenschaft von der <xref:System.Activities.Statements.WriteLine> Aktivität "Hello, World".</span><span class="sxs-lookup"><span data-stu-id="84d8b-123">Set the <xref:System.Activities.Statements.WriteLine.Text%2A> property of the <xref:System.Activities.Statements.WriteLine> activity to "Hello, world".</span></span>  
  
     <span data-ttu-id="84d8b-124">Der Workflow sollte jetzt wie das folgende Diagramm aussehen.</span><span class="sxs-lookup"><span data-stu-id="84d8b-124">The workflow should now look like the following diagram.</span></span>  
  
     <span data-ttu-id="84d8b-125">![Ein einfacher Workflow](../../../../docs/framework/wcf/feature-details/media/simpleworkflow.png "SimpleWorkflow")</span><span class="sxs-lookup"><span data-stu-id="84d8b-125">![A simple workflow](../../../../docs/framework/wcf/feature-details/media/simpleworkflow.png "SimpleWorkflow")</span></span>  
  
### <a name="create-the-workflow-creation-service-contract"></a><span data-ttu-id="84d8b-126">Erstellen des Dienstvertrags für die Workflowerstellung</span><span class="sxs-lookup"><span data-stu-id="84d8b-126">Create the workflow creation service contract</span></span>  
  
1.  <span data-ttu-id="84d8b-127">Fügen Sie der Projektmappe `Shared` das neue Klassenbibliotheksprojekt `CreationEndpointTest` hinzu.</span><span class="sxs-lookup"><span data-stu-id="84d8b-127">Add a new class library project called `Shared` to the `CreationEndpointTest` solution.</span></span>  
  
2.  <span data-ttu-id="84d8b-128">Fügen Sie dem Projekt `Shared` Verweise auf System.ServiceModel.dll, System.Configuration und System.ServiceModel.Activities hinzu.</span><span class="sxs-lookup"><span data-stu-id="84d8b-128">Add a reference to System.ServiceModel.dll, System.Configuration, and System.ServiceModel.Activities to the `Shared` project.</span></span>  
  
3.  <span data-ttu-id="84d8b-129">Benennen Sie die Datei Class1.cs in IWorkflowCreation.cs um, und fügen Sie der Datei folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="84d8b-129">Rename the Class1.cs file to IWorkflowCreation.cs and the following code to the file.</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
  
    namespace Shared  
    {  
        //service contract exposed from the endpoint  
        [ServiceContract(Name = "IWorkflowCreation")]  
        public interface IWorkflowCreation  
        {  
            [OperationContract(Name = "Create")]  
            Guid Create(IDictionary<string, object> inputs);  
  
            [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
            void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
        }  
    }  
    ```  
  
     <span data-ttu-id="84d8b-130">Mit diesem Vertrag werden zwei Vorgänge definiert, mit denen jeweils eine neue Instanz des soeben erstellten Workflows erstellt wird, der kein Dienstworkflow ist.</span><span class="sxs-lookup"><span data-stu-id="84d8b-130">This contract defines two operations both create a new instance of the non-service workflow you just created.</span></span> <span data-ttu-id="84d8b-131">Während in dem einem Vorgang eine neue Instanz mit einer generierten Instanz-ID erstellt wird, können Sie die Instanz-ID für die neue Workflowinstanz in dem anderen Vorgang selbst angeben.</span><span class="sxs-lookup"><span data-stu-id="84d8b-131">One creates a new instance with a generated instance ID and the other allows you to specify the instance ID for the new workflow instance.</span></span>  <span data-ttu-id="84d8b-132">Beide Methoden ermöglichen das Übergeben von Parametern an die neue Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="84d8b-132">Both methods allow you to pass in parameters to the new workflow instance.</span></span> <span data-ttu-id="84d8b-133">Dieser Vertrag wird verfügbar gemacht werden, indem die <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> damit Clients neue Instanzen eines nicht-Workflows erstellen können.</span><span class="sxs-lookup"><span data-stu-id="84d8b-133">This contract will be exposed by the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to allow clients to create new instances of a non-service workflow.</span></span>  
  
### <a name="derive-a-class-from-workflowhostingendpoint"></a><span data-ttu-id="84d8b-134">Ableiten einer Klasse von WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="84d8b-134">Derive a class from WorkflowHostingEndpoint</span></span>  
  
1.  <span data-ttu-id="84d8b-135">Fügen Sie eine neue Klasse namens `CreationEndpoint` abgeleitet <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> auf die `Shared` Projekt.</span><span class="sxs-lookup"><span data-stu-id="84d8b-135">Add a new class called `CreationEndpoint` derived from <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to the `Shared` project.</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Globalization;  
    using System.ServiceModel;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Channels;  
  
    namespace Shared  
    {  
        public class CreationEndpoint : WorkflowHostingEndpoint  
        {  
        }  
    }  
    ```  
  
2.  <span data-ttu-id="84d8b-136">Fügen Sie der <xref:System.Uri>-Klasse die lokale statische `defaultBaseUri`-Variable mit dem Namen `CreationEndpoint` hinzu.</span><span class="sxs-lookup"><span data-stu-id="84d8b-136">Add a local static <xref:System.Uri> variable called `defaultBaseUri` to the `CreationEndpoint` class.</span></span>  
  
    ```  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
    }  
    ```  
  
3.  <span data-ttu-id="84d8b-137">Fügen Sie der `CreationEndpoint`-Klasse den folgenden Konstruktor hinzu.</span><span class="sxs-lookup"><span data-stu-id="84d8b-137">Add the following constructor to the `CreationEndpoint` class.</span></span> <span data-ttu-id="84d8b-138">Beachten Sie, dass der `IWorkflowCreation`-Dienstvertrag im Aufruf des Basiskonstruktors angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="84d8b-138">Notice we specify the `IWorkflowCreation` service contract in the call to the base constructor.</span></span>  
  
    ```  
    public CreationEndpoint(Binding binding, EndpointAddress address)  
       : base(typeof(IWorkflowCreation), binding, address)  
       {  
       }  
    ```  
  
4.  <span data-ttu-id="84d8b-139">Fügen Sie der `CreationEndpoint`-Klasse den folgenden Standardkonstruktor hinzu.</span><span class="sxs-lookup"><span data-stu-id="84d8b-139">Add the following default constructor to the `CreationEndpoint` class.</span></span>  
  
    ```  
    public CreationEndpoint()  
       : this(GetDefaultBinding(),  
       new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative))))  
       {  
       }  
    ```  
  
5.  <span data-ttu-id="84d8b-140">Fügen Sie der `DefaultBaseUri`-Klasse eine statische `CreationEndpoint`-Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="84d8b-140">Add a static `DefaultBaseUri` property to the `CreationEndpoint` class.</span></span> <span data-ttu-id="84d8b-141">Diese Eigenschaft enthält einen standardmäßigen Basis-URI, sofern keiner angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="84d8b-141">This property will be used to hold a default base URI if one is not provided.</span></span>  
  
    ```  
    static Uri DefaultBaseUri  
    {  
       get  
       {  
          if (defaultBaseUri == null)  
          {  
             defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                Process.GetCurrentProcess().Id,  
                AppDomain.CurrentDomain.Id));  
          }  
          return defaultBaseUri;  
       }  
     }  
    ```  
  
6.  <span data-ttu-id="84d8b-142">Erstellen Sie die folgende Methode, um die Standardbindung für den Erstellungsendpunkt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="84d8b-142">Create the following method to get the default binding to use for the creation endpoint.</span></span>  
  
    ```  
    //defaults to NetNamedPipeBinding  
    public static Binding GetDefaultBinding()  
    {  
       return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
    }  
    ```  
  
7.  <span data-ttu-id="84d8b-143">Überschreiben Sie die <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A>-Methode, um die Instanz-ID für den Workflow zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="84d8b-143">Override the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A> method to return the workflow instance ID.</span></span> <span data-ttu-id="84d8b-144">Wenn die `Action` Header endet mit "Create" eine leere GUID zurück, wenn die `Action` Header mit die GUID, die an die Methode übergebenen "CreateWithInstanceId" endet.</span><span class="sxs-lookup"><span data-stu-id="84d8b-144">If the `Action` header ends with "Create" return an empty GUID, if the `Action` header ends with "CreateWithInstanceId" return the GUID passed into the method.</span></span> <span data-ttu-id="84d8b-145">Andernfalls wird eine <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="84d8b-145">Otherwise, throw an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="84d8b-146">Diese `Action`-Header entsprechen den beiden Vorgängen, die im `IWorkflowCreation`-Dienstvertrag definiert sind.</span><span class="sxs-lookup"><span data-stu-id="84d8b-146">These `Action` headers correspond to the two operations defined in the `IWorkflowCreation` service contract.</span></span>  
  
    ```  
    protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
    {  
       //Create was called by client  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
       {  
          return Guid.Empty;  
       }  
       //CreateWithInstanceId was called by client  
       else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
       {  
          return (Guid)inputs[1];  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
    }  
    ```  
  
8.  <span data-ttu-id="84d8b-147">Überschreiben Sie die <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A>-Methode, um einen <xref:System.ServiceModel.Activities.WorkflowCreationContext> zu erstellen. Fügen Sie Argumente für den Workflow hinzu, senden Sie die Instanz-ID an den Client, und geben Sie den <xref:System.ServiceModel.Activities.WorkflowCreationContext> zurück.</span><span class="sxs-lookup"><span data-stu-id="84d8b-147">Override the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A> method to create a <xref:System.ServiceModel.Activities.WorkflowCreationContext> and add any arguments for the workflow, send the instance ID to the client, and then return the <xref:System.ServiceModel.Activities.WorkflowCreationContext>.</span></span>  
  
    ```  
    protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
    {  
       WorkflowCreationContext creationContext = new WorkflowCreationContext();  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create") || (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId")))  
       {  
          Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
          if (arguments != null && arguments.Count > 0)  
          {  
             foreach (KeyValuePair<string, object> pair in arguments)  
             {  
                //arguments to pass to the workflow  
                creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
             }  
          }  
          //reply to client with instanceId  
          responseContext.SendResponse(instanceId, null);  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
       return creationContext;  
    }  
    ```  
  
### <a name="create-a-standard-endpoint-element-to-allow-you-to-configure-the-workflowcreationendpoint"></a><span data-ttu-id="84d8b-148">Erstellen eines Standardendpunktelements zum Konfigurieren des WorkflowCreationEndpoint</span><span class="sxs-lookup"><span data-stu-id="84d8b-148">Create a standard endpoint element to allow you to configure the WorkflowCreationEndpoint</span></span>  
  
1.  <span data-ttu-id="84d8b-149">Fügen Sie dem Projekt `CreationEndpoint` einen Verweis auf Shared hinzu.</span><span class="sxs-lookup"><span data-stu-id="84d8b-149">Add a reference to Shared in the `CreationEndpoint` project</span></span>  
  
2.  <span data-ttu-id="84d8b-150">Fügen Sie dem Projekt `CreationEndpointElement` die neue <xref:System.ServiceModel.Configuration.StandardEndpointElement>-Klasse hinzu, die von `CreationEndpoint` abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="84d8b-150">Add a new class called `CreationEndpointElement`, derived from <xref:System.ServiceModel.Configuration.StandardEndpointElement> to the `CreationEndpoint` project.</span></span> <span data-ttu-id="84d8b-151">Diese Klasse stellt einen `CreationEndpoint` in einer web.config-Datei dar.</span><span class="sxs-lookup"><span data-stu-id="84d8b-151">This class will represent a `CreationEndpoint` in a web.config file.</span></span>  
  
    ```  
    using System;  
    using System.Configuration;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Configuration;  
    using System.ServiceModel.Description;  
    using Shared;  
  
    namespace CreationEndpointTest  
    {  
        //config element for CreationEndpoint  
        public class CreationEndpointElement : StandardEndpointElement  
        {  
       }  
    ```  
  
3.  <span data-ttu-id="84d8b-152">Fügen Sie die `EndpointType`-Eigenschaft hinzu, um den Typ des Endpunkts zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="84d8b-152">Add a property called `EndpointType` to return the type of the endpoint.</span></span>  
  
    ```  
    protected override Type EndpointType  
    {  
       get { return typeof(CreationEndpoint); }  
    }  
    ```  
  
4.  <span data-ttu-id="84d8b-153">Überschreiben Sie die <xref:System.ServiceModel.Configuration.StandardEndpointElement.CreateServiceEndpoint%2A>-Methode, und geben Sie einen neuen `CreationEndpoint` zurück.</span><span class="sxs-lookup"><span data-stu-id="84d8b-153">Override the <xref:System.ServiceModel.Configuration.StandardEndpointElement.CreateServiceEndpoint%2A> method and return a new `CreationEndpoint`.</span></span>  
  
    ```  
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
    {  
       return new CreationEndpoint();  
    }  
    ```  
  
5.  <span data-ttu-id="84d8b-154">Überladen Sie die folgenden Methoden: <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A> und <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A>.</span><span class="sxs-lookup"><span data-stu-id="84d8b-154">Overload the <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A>, and <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A> methods.</span></span> <span data-ttu-id="84d8b-155">Diese Methoden müssen lediglich definiert werden; es ist nicht erforderlich, Code hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="84d8b-155">These methods just need to be defined, you do not need to add any code to them.</span></span>  
  
    ```  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
    ```  
  
6.  <span data-ttu-id="84d8b-156">Fügen Sie der Datei CreationEndpointElement.cs im Projekt `CreationEndpoint` die Auflistungsklasse für `CreationEndpoint` hinzu.</span><span class="sxs-lookup"><span data-stu-id="84d8b-156">Add the collection class for `CreationEndpoint` to the CreationEndpointElement.cs file in the `CreationEndpoint` project.</span></span> <span data-ttu-id="84d8b-157">Diese Klasse wird von der Konfiguration für eine Reihe von `CreationEndpoint`-Instanzen in einer web.config-Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="84d8b-157">This class is used by configuration to hold a number of `CreationEndpoint` instances in a web.config file.</span></span>  
  
    ```  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
    ```  
  
7.  <span data-ttu-id="84d8b-158">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="84d8b-158">Build the solution.</span></span>  
  
### <a name="host-the-workflow-in-iis"></a><span data-ttu-id="84d8b-159">Hosten des Workflows in IIS</span><span class="sxs-lookup"><span data-stu-id="84d8b-159">Host the workflow in IIS</span></span>  
  
1.  <span data-ttu-id="84d8b-160">Erstellen Sie in IIS die neue Anwendung `MyCreationEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="84d8b-160">Create a new application called `MyCreationEndpoint` in IIS.</span></span>  
  
2.  <span data-ttu-id="84d8b-161">Kopieren Sie die Datei workflow1.xaml, die vom Workflow-Designer generiert wurde, in das Anwendungsverzeichnis, und benennen Sie sie in workflow1.xamlx um.</span><span class="sxs-lookup"><span data-stu-id="84d8b-161">Copy the workflow1.xaml file generated by the workflow designer to the application directory and rename it to workflow1.xamlx.</span></span>  
  
3.  <span data-ttu-id="84d8b-162">Kopieren Sie die Datei shared.dll und die Datei CreationEndpoint.dll in das BIN-Verzeichnis der Anwendung (ggf. müssen Sie das Verzeichnis zunächst erstellen).</span><span class="sxs-lookup"><span data-stu-id="84d8b-162">Copy the shared.dll and CreationEndpoint.dll files to the application’s bin directory (create the bin directory if it is not present).</span></span>  
  
4.  <span data-ttu-id="84d8b-163">Ersetzen Sie den Inhalt der web.config-Datei im Projekt `CreationEndpoint` durch folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="84d8b-163">Replace the contents of the Web.config file in the `CreationEndpoint` project with the following code.</span></span>  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.web>  
        <compilation debug="true" targetFramework="4.0" />  
      </system.web>   
    </configuration>  
    ```  
  
5.  <span data-ttu-id="84d8b-164">Registrieren Sie den `<system.web>` nach dem `CreationEndpoint`-Element durch Hinzufügen des folgenden Konfigurationscodes.</span><span class="sxs-lookup"><span data-stu-id="84d8b-164">After the `<system.web>` element, register `CreationEndpoint` by adding the following configuration code.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <!--register CreationEndpoint-->  
        <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
        <extensions>  
          <endpointExtensions>  
            <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, CreationEndpoint, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </endpointExtensions>  
        </extensions>  
    </system.serviceModel>  
    ```  
  
     <span data-ttu-id="84d8b-165">Dadurch wird die `CreationEndpointCollection`-Klasse registriert, und Sie können einen `CreationEndpoint` in einer web.config-Datei konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="84d8b-165">This registers the `CreationEndpointCollection` class so you can configure a `CreationEndpoint` in a web.config file.</span></span>  
  
6.  <span data-ttu-id="84d8b-166">Hinzufügen einer `<service>` Element (nach der \</extensions > Tag) mit einem `CreationEndpoint` , um eingehende Nachrichten zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="84d8b-166">Add a `<service>` element (after the \</extensions> tag) with a `CreationEndpoint` which will listen for incoming messages.</span></span>  
  
    ```xml  
    <services>  
          <!-- add endpoint to service-->  
          <service name="Workflow1" behaviorConfiguration="basicConfig" >  
            <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
          </service>  
        </services>  
    ```  
  
7.  <span data-ttu-id="84d8b-167">Hinzufügen einer \<Verhalten > Element (nach der  \< /services > Tag) um Dienstmetadaten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="84d8b-167">Add a \<behaviors> element (after the \</services> tag) to enable service metadata.</span></span>  
  
    ```xml  
    <behaviors>  
          <serviceBehaviors>  
            <behavior name="basicConfig">  
              <serviceMetadata httpGetEnabled="true" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
    ```  
  
8.  <span data-ttu-id="84d8b-168">Kopieren Sie die web.config-Datei in Ihr IIS-Anwendungsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="84d8b-168">Copy the web.config to your IIS application directory.</span></span>  
  
9. <span data-ttu-id="84d8b-169">Überprüfen Sie die Funktion des Erstellungsendpunkts, indem Sie Internet Explorer starten und zu http://localhost/MyCreationEndpoint/Workflow1.xamlx navigieren.</span><span class="sxs-lookup"><span data-stu-id="84d8b-169">Test to see if the creation endpoint is working by starting Internet Explorer and browsing to http://localhost/MyCreationEndpoint/Workflow1.xamlx.</span></span> <span data-ttu-id="84d8b-170">Internet Explorer sollte nun folgenden Bildschirm anzeigen:</span><span class="sxs-lookup"><span data-stu-id="84d8b-170">Internet Explorer should display the following screen:</span></span>  
  
     <span data-ttu-id="84d8b-171">![Testen des Diensts](../../../../docs/framework/wcf/feature-details/media/testservice.gif "TestService")</span><span class="sxs-lookup"><span data-stu-id="84d8b-171">![Testing the service](../../../../docs/framework/wcf/feature-details/media/testservice.gif "TestService")</span></span>  
  
### <a name="create-a-client-that-will-call-the-creationendpoint"></a><span data-ttu-id="84d8b-172">Erstellen Sie einen Client, mit dem der CreationEndpoint aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="84d8b-172">Create a client that will call the CreationEndpoint.</span></span>  
  
1.  <span data-ttu-id="84d8b-173">Fügen Sie der Projektmappe `CreationEndpointTest` eine neue Konsolenanwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="84d8b-173">Add a new Console application to the `CreationEndpointTest` solution.</span></span>  
  
2.  <span data-ttu-id="84d8b-174">Fügen Sie Verweise auf System.ServiceModel.dll und System.ServiceModel.Activities sowie das Projekt `Shared` hinzu.</span><span class="sxs-lookup"><span data-stu-id="84d8b-174">Add references to System.ServiceModel.dll, System.ServiceModel.Activities, and the `Shared` project.</span></span>  
  
3.  <span data-ttu-id="84d8b-175">In der `Main` Methode erstellt eine <xref:System.ServiceModel.ChannelFactory%601> des Typs `IWorkflowCreation` , und rufen Sie <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>.</span><span class="sxs-lookup"><span data-stu-id="84d8b-175">In the `Main` method create a <xref:System.ServiceModel.ChannelFactory%601> of type `IWorkflowCreation` and call <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>.</span></span> <span data-ttu-id="84d8b-176">Dadurch wird ein Proxy zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="84d8b-176">This will return a proxy.</span></span> <span data-ttu-id="84d8b-177">Anschließend können Sie `Create` für den Proxy aufrufen, um die Workflowinstanz zu erstellen, die unter IIS gehostet wird:</span><span class="sxs-lookup"><span data-stu-id="84d8b-177">You can then call `Create` on that proxy to create the workflow instance hosted under IIS:</span></span>  
  
    ```  
    using System.Text;  
    using Shared;  
    using System.ServiceModel;  
  
    namespace CreationEndpointClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                try  
                {  
                    //client using BasicHttpBinding  
                    IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/CreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                    Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                    Console.WriteLine("Press return to exit ...");  
                    Console.ReadLine();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine(ex);  
                    Console.ReadLine();  
                }  
            }  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="84d8b-178">Führen Sie den CreationEndpointClient aus.</span><span class="sxs-lookup"><span data-stu-id="84d8b-178">Run the CreationEndpointClient.</span></span> <span data-ttu-id="84d8b-179">Die Ausgabe sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="84d8b-179">The output should look like the following:</span></span>  
  
    ```Output  
    Workflow Instance created using CreationEndpoint added in config. Instance Id: 0875dac0-2b8b-473e-b3cc-abcb235e9693Press return to exit ...  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="84d8b-180">Die Ausgabe des Workflows wird nicht angezeigt, da IIS nicht über eine Konsolenausgabe verfügt.</span><span class="sxs-lookup"><span data-stu-id="84d8b-180">You will not see the output of the workflow because it is running under IIS which has no console output.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84d8b-181">Beispiel</span><span class="sxs-lookup"><span data-stu-id="84d8b-181">Example</span></span>  
 <span data-ttu-id="84d8b-182">Nachfolgend ist der vollständige Code für dieses Beispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="84d8b-182">The following is the complete code for this sample.</span></span>  
  
```xaml  
<!-— workflow1.xamlx -->  
<WorkflowService mc:Ignorable="sap"   
                 ConfigurationName="Workflow1"   
                 sap:VirtualizedContainerService.HintSize="263,230"   
                 Name="Workflow1"   
                 mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces"   
                 xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"   
                 xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
                 xmlns:mv="clr-namespace:Microsoft.VisualBasic;assembly=System"   
                 xmlns:mva="clr-namespace:Microsoft.VisualBasic.Activities;assembly=System.Activities"   
                 xmlns:p="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
                 xmlns:s="clr-namespace:System;assembly=mscorlib"   
                 xmlns:s1="clr-namespace:System;assembly=System"   
                 xmlns:s2="clr-namespace:System;assembly=System.Xml"   
                 xmlns:s3="clr-namespace:System;assembly=System.Core"   
                 xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities"   
                 xmlns:sap="http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation"   
                 xmlns:scg="clr-namespace:System.Collections.Generic;assembly=System"   
                 xmlns:scg1="clr-namespace:System.Collections.Generic;assembly=System.ServiceModel"   
                 xmlns:scg2="clr-namespace:System.Collections.Generic;assembly=System.Core"   
                 xmlns:scg3="clr-namespace:System.Collections.Generic;assembly=mscorlib"   
                 xmlns:sd="clr-namespace:System.Data;assembly=System.Data"   
                 xmlns:sl="clr-namespace:System.Linq;assembly=System.Core"   
                 xmlns:st="clr-namespace:System.Text;assembly=mscorlib"   
                 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <p:Sequence DisplayName="Sequential Service"   
              sad:XamlDebuggerXmlReader.FileName="c:\projects\CreationEndpointTest\CreationEndpoint\Service1.xamlx"   
              sap:VirtualizedContainerService.HintSize="233,200"   
              mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces">  
    <p:Sequence.Variables>  
      <p:Variable x:TypeArguments="CorrelationHandle" Name="handle" />  
      <p:Variable x:TypeArguments="x:Int32" Name="data" />  
    </p:Sequence.Variables>  
    <sap:WorkflowViewStateService.ViewState>  
      <scg3:Dictionary x:TypeArguments="x:String, x:Object">  
        <x:Boolean x:Key="IsExpanded">True</x:Boolean>  
      </scg3:Dictionary>  
    </sap:WorkflowViewStateService.ViewState>  
    <p:WriteLine sap:VirtualizedContainerService.HintSize="211,61" Text="Hello, world" />  
  </p:Sequence>  
</WorkflowService>  
```  
  
```csharp  
// CreationEndpointElement.cs  
using System;  
using System.Configuration;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Description;  
using Shared;  
  
namespace CreationEndpointTest  
{  
    //config element for CreationEndpoint  
    public class CreationEndpointElement : StandardEndpointElement  
    {  
        protected override Type EndpointType  
        {  
            get { return typeof(CreationEndpoint); }  
        }  
  
        protected override ConfigurationPropertyCollection Properties  
        {  
            get  
            {  
                ConfigurationPropertyCollection properties = base.Properties;  
                properties.Add(new ConfigurationProperty("name", typeof(String), null, ConfigurationPropertyOptions.IsRequired));  
                return properties;  
            }  
        }  
  
        protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
        {  
            return new CreationEndpoint();  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
    }  
  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
}  
```  
  
```xml  
<!-- web.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <!--register CreationEndpoint-->  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
    <extensions>  
      <endpointExtensions>  
        <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, Shared, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </endpointExtensions>  
    </extensions>  
    <services>  
      <!-- add endpoint to service-->  
      <service name="Workflow1" behaviorConfiguration="basicConfig" >  
        <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="basicConfig">  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```csharp  
// IWorkflowCreation.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
  
namespace Shared  
{  
    //service contract exposed from the endpoint  
    [ServiceContract(Name = "IWorkflowCreation")]  
    public interface IWorkflowCreation  
    {  
        [OperationContract(Name = "Create")]  
        Guid Create(IDictionary<string, object> inputs);  
  
        [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
        void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
    }  
}  
```  
  
```csharp  
// CreationEndpoint.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Channels;  
using System.ServiceModel;  
using System.Globalization;  
using System.Diagnostics;  
  
namespace Shared  
{  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
  
        public CreationEndpoint(Binding binding, EndpointAddress address)  
            : base(typeof(IWorkflowCreation), binding, address) { }  
  
        public CreationEndpoint()  
            : this(GetDefaultBinding(),  
                new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative)))) { }  
  
        static Uri DefaultBaseUri  
        {  
            get  
            {  
                if (defaultBaseUri == null)  
                {  
                    defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                        Process.GetCurrentProcess().Id,  
                        AppDomain.CurrentDomain.Id));  
                }  
                return defaultBaseUri;  
            }  
        }  
  
        //defaults to NetNamedPipeBinding  
        public static Binding GetDefaultBinding()  
        {  
            return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
        }  
  
        protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
        {  
            //Create was called by client  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                return Guid.Empty;  
            }  
  
            //CreateWithInstanceId was called by client  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                return (Guid)inputs[1];  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
        }  
  
        protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
        {  
            WorkflowCreationContext creationContext = new WorkflowCreationContext();  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to the workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
                //reply to client with instanceId  
                responseContext.SendResponse(instanceId, null);  
            }  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
            return creationContext;  
        }  
    }  
}  
```  
  
```csharp  
// CreationEndpointClient.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Shared;  
using System.ServiceModel;  
  
namespace CreationClient  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                //client using BasicHttpBinding  
                IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/MyCreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                Console.WriteLine("Press return to exit ...");  
                Console.ReadLine();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex);  
                Console.ReadLine();  
            }  
  
        }  
    }  
  
}  
```  
  
 <span data-ttu-id="84d8b-183">Möglicherweise erscheint dieses Beispiel verwirrend, da zu keiner Zeit ein Dienst implementiert wird, der `IWorkflowCreation` implementiert.</span><span class="sxs-lookup"><span data-stu-id="84d8b-183">This example may seem confusing because you never implement a service that implements `IWorkflowCreation`.</span></span> <span data-ttu-id="84d8b-184">Diese Aufgabe wird von `CreationEndpoint` übernommen.</span><span class="sxs-lookup"><span data-stu-id="84d8b-184">This is because the `CreationEndpoint` does this for you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d8b-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84d8b-185">See Also</span></span>  
 [<span data-ttu-id="84d8b-186">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="84d8b-186">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="84d8b-187">Hosten in Internetinformationsdienste (IIS)</span><span class="sxs-lookup"><span data-stu-id="84d8b-187">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [<span data-ttu-id="84d8b-188">Internetinformation Services Hosting bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="84d8b-188">Internet Information Services Hosting Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [<span data-ttu-id="84d8b-189">Internet-Internetinformationsdiensts</span><span class="sxs-lookup"><span data-stu-id="84d8b-189">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)  
 [<span data-ttu-id="84d8b-190">Architektur von Windows-Workflows</span><span class="sxs-lookup"><span data-stu-id="84d8b-190">Windows Workflow Architecture</span></span>](../../../../docs/framework/windows-workflow-foundation/architecture.md)  
 [<span data-ttu-id="84d8b-191">Lesezeichen-Wiederaufnahme WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="84d8b-191">WorkflowHostingEndpoint Resume Bookmark</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/workflowhostingendpoint-resume-bookmark.md)  
 [<span data-ttu-id="84d8b-192">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="84d8b-192">Rehosting the Workflow Designer</span></span>](../../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="84d8b-193">Übersicht über Windows-Workflow</span><span class="sxs-lookup"><span data-stu-id="84d8b-193">Windows Workflow Overview</span></span>](../../../../docs/framework/windows-workflow-foundation/overview.md)
