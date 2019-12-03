---
title: Verwendung von Standardendpunkten
ms.date: 03/30/2017
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
ms.openlocfilehash: 2b210bfe683669aeebf54a1701f07d492e6abdb4
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715347"
---
# <a name="usage-of-standard-endpoints"></a><span data-ttu-id="3f913-102">Verwendung von Standardendpunkten</span><span class="sxs-lookup"><span data-stu-id="3f913-102">Usage of Standard Endpoints</span></span>

<span data-ttu-id="3f913-103">In diesem Beispiel wird veranschaulicht, wie Standardendpunkte in Dienstkonfigurationsdateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f913-103">This sample demonstrates how to use standard endpoints in service configuration files.</span></span> <span data-ttu-id="3f913-104">Ein Standardendpunkt ermöglicht es dem Benutzer, einfacher Endpunktdefinitionen anzugeben, indem mit einer einzigen Eigenschaft eine Kombination aus Adresse, Bindung und Vertrag beschrieben und diesen Elementen zusätzliche Eigenschaften zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="3f913-104">A standard endpoint allows the user to simplify endpoint definitions by using a single property to describe an address, binding and contract combination with additional properties associated to it.</span></span> <span data-ttu-id="3f913-105">In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter Standardendpunkt definiert und implementiert wird und wie bestimmte Eigenschaften im Endpunkt definiert werden.</span><span class="sxs-lookup"><span data-stu-id="3f913-105">This sample demonstrates how to define and implement a custom standard endpoint and how to define specific properties in the endpoint.</span></span>

## <a name="sample-details"></a><span data-ttu-id="3f913-106">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="3f913-106">Sample Details</span></span>

<span data-ttu-id="3f913-107">Dienstendpunkte können mit der Bereitstellung von drei Parametern angegeben werden: Adresse, Bindung und Vertrag.</span><span class="sxs-lookup"><span data-stu-id="3f913-107">Service endpoints can be specified by supplying three parameters: address, binding and contract.</span></span> <span data-ttu-id="3f913-108">Andere Parameter, die angegeben werden können, sind etwa Verhaltenskonfiguration, Header, Überwachungs-URI usw.</span><span class="sxs-lookup"><span data-stu-id="3f913-108">Other parameters that can be supplied include behavior configuration, headers, listen URI, and so on.</span></span> <span data-ttu-id="3f913-109">In einigen Fällen verfügen einige oder alle der Adressen, Bindungen und Verträge über Werte, die nicht veränderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3f913-109">In some cases, any or all of addresses, bindings and contracts have values that cannot change.</span></span> <span data-ttu-id="3f913-110">Aus diesem Grund können Standardendpunkte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f913-110">For this reason, it is possible to use standard endpoints.</span></span> <span data-ttu-id="3f913-111">Einige Beispiele für solche Endpunkte enthalten Metadatenaustausch-Endpunkte und Suchendpunkte.</span><span class="sxs-lookup"><span data-stu-id="3f913-111">Some examples of such endpoints include metadata exchange endpoints and discovery endpoints.</span></span> <span data-ttu-id="3f913-112">Standardendpunkte erhöhen außerdem die Benutzerfreundlichkeit, da sie die Konfiguration von Dienstendpunkten ermöglichen, ohne dass bestimmte Informationen bereitgestellt oder eigene Standardendpunkte erstellt werden müssen, etwa zur Verbesserung der Nutzbarkeit durch die Angabe eines entsprechenden Satzes von Standardwerten, um die Komplexität der Konfigurationsdateien zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="3f913-112">Standard endpoints also improve usability by allowing configuration of service endpoints without having to provide information of a fixed nature or to create their own standard endpoints, for example to improve usability by supplying a reasonable set of default values and thus reducing the verbosity of configuration files.</span></span>

<span data-ttu-id="3f913-113">Dieses Beispiel besteht aus zwei Projekten: dem Dienst, der zwei Standardendpunkte definiert, und dem Client, der mit dem Dienst kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="3f913-113">This sample consists of two projects: the service that defines two standard endpoints and the client that communicates with the service.</span></span> <span data-ttu-id="3f913-114">Die Methode zur Definition der Standardendpunkte für den Dienst in der Konfigurationsdatei wird im folgenden Beispiel erläutert.</span><span class="sxs-lookup"><span data-stu-id="3f913-114">The way the standard endpoints are defined for the service in the configuration file is show in the following example.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <extensions>
      <endpointExtensions>
        <add name="customEndpoint" type="Microsoft.Samples.StandardEndpoints.CustomEndpointCollectionElement, service" />
      </endpointExtensions>
    </extensions>
    <services>
      <service name="Microsoft.Samples.StandardEndpoints.CalculatorService">
        <endpoint address="http://localhost:8000/Samples/Service.svc/customEndpoint" contract="Microsoft.Samples.StandardEndpoints.ICalculator" kind="customEndpoint" />
        <endpoint kind="mexEndpoint" />
      </service>
    </services>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="True"/>
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <standardEndpoints>
      <customEndpoint>
        <standardEndpoint property="True" />
      </customEndpoint>
    </standardEndpoints>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="3f913-115">Der erste für den Dienst definierte Endpunkt ist ein `customEndpoint`, dessen Definition im Abschnitt `<standardEndpoints>` angezeigt wird. Dabei enthält die `property`-Eigenschaft den Wert `true`.</span><span class="sxs-lookup"><span data-stu-id="3f913-115">The first endpoint defined for the service is of kind `customEndpoint`, whose definition can be seen in the `<standardEndpoints>` section, in which the property `property` is given the value `true`.</span></span> <span data-ttu-id="3f913-116">Hierbei handelt es sich um einen Endpunkt, der mit einer neuen Eigenschaft angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="3f913-116">This is the case of an endpoint customized with a new property.</span></span> <span data-ttu-id="3f913-117">Der zweite Endpunkt entspricht einem Metadatenendpunkt, in dem die Werte für die Adresse, die Bindung und den Vertrag fest angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="3f913-117">The second endpoint corresponds to a metadata endpoint, in which the values for address, binding and contract are fixed.</span></span>

<span data-ttu-id="3f913-118">Für die Definition des Standardendpunkt-Elements muss eine Klasse, die sich von `StandardEndpointElement` ableitet, erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3f913-118">To define the standard endpoint element, a class that derives from `StandardEndpointElement` must be created.</span></span> <span data-ttu-id="3f913-119">Im Fall dieses Beispiels wurde die `CustomEndpointElement`-Klasse wie im folgenden Beispiel dargestellt definiert.</span><span class="sxs-lookup"><span data-stu-id="3f913-119">In the case of this sample, the `CustomEndpointElement` class has been defined as shown in the following example.</span></span>

```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```

<span data-ttu-id="3f913-120">Es wird ein `CreateServiceEndpoint`-Objekt in der `CustomEndpoint`-Funktion erstellt.</span><span class="sxs-lookup"><span data-stu-id="3f913-120">In the `CreateServiceEndpoint` function, a `CustomEndpoint` object is created.</span></span> <span data-ttu-id="3f913-121">Die Definition ist im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="3f913-121">Its definition is shown in the following example:</span></span>

```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    {
    }

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    {
    }

    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    public bool Property
    {
        get;
        set;
    }
}
```

 <span data-ttu-id="3f913-122">Für die Kommunikation zwischen Dienst und Client wird im Client ein Dienstverweis zum Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="3f913-122">To perform the communication between service and client, a service reference is created in the client to the service.</span></span> <span data-ttu-id="3f913-123">Wenn das Beispiel erstellt und ausgeführt wurde, wird der Dienst ausgeführt, und der Client kommuniziert damit.</span><span class="sxs-lookup"><span data-stu-id="3f913-123">When the sample is built and executed, the service executes and the client communicates with it.</span></span> <span data-ttu-id="3f913-124">Beachten Sie, dass der Dienstverweis stets aktualisiert werden muss, wenn es eine Änderung im Dienst gibt.</span><span class="sxs-lookup"><span data-stu-id="3f913-124">Note that the service reference should be updated every time there is some change in the service.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="3f913-125">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f913-125">To use this sample</span></span>

1. <span data-ttu-id="3f913-126">Öffnen Sie mit Visual Studio 2012 die Datei "standardendpoints. sln".</span><span class="sxs-lookup"><span data-stu-id="3f913-126">Using Visual Studio 2012, open the StandardEndpoints.sln file.</span></span>

2. <span data-ttu-id="3f913-127">Aktivieren Sie mehrere Projekte, um zu starten.</span><span class="sxs-lookup"><span data-stu-id="3f913-127">Enable multiple projects to start up.</span></span>

    1. <span data-ttu-id="3f913-128">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf die Lösung Standard Endpunkte, und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="3f913-128">In **Solution Explorer**, right-click the Standard Endpoints solution and then select **Properties**.</span></span>

    2. <span data-ttu-id="3f913-129">Wählen Sie unter **Allgemeine Eigenschaften**die Option **Startprojekt**aus, und klicken Sie dann auf **mehrere Start Projekte**.</span><span class="sxs-lookup"><span data-stu-id="3f913-129">In **Common Properties**, select **Startup Project**, and then click **Multiple Startup Projects**.</span></span>

    3. <span data-ttu-id="3f913-130">Verschieben Sie das Dienstprojekt an den Anfang der Liste, wobei die **Aktion** auf **starten**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3f913-130">Move the Service project to the beginning of the list, with the **Action** set to **Start**.</span></span>

    4. <span data-ttu-id="3f913-131">Verschieben Sie das Client Projekt nach dem Dienstprojekt, auch wenn die **Aktion** auf **starten**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3f913-131">Move the Client project after the Service project, also with the **Action** set to **Start**.</span></span>

         <span data-ttu-id="3f913-132">Dadurch wird angegeben, dass das Clientprojekt nach dem Dienstprojekt ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3f913-132">This specifies that the Client project is executed after the Service project.</span></span>

3. <span data-ttu-id="3f913-133">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3f913-133">To run the solution, press F5.</span></span>

> [!NOTE]
> <span data-ttu-id="3f913-134">Wenn diese Schritte nicht funktionieren, stellen Sie sicher, dass Ihre Umgebung ordnungsgemäß eingerichtet wurde, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="3f913-134">If these steps don't work, then make sure that your environment has been properly set up, using the following steps:</span></span>
>
> 1. <span data-ttu-id="3f913-135">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="3f913-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>
> 2. <span data-ttu-id="3f913-136">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f913-136">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>
> 3. <span data-ttu-id="3f913-137">Wenn Sie das Beispiel in einer Konfiguration mit einem oder mehreren Computern ausführen möchten, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3f913-137">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f913-138">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="3f913-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3f913-139">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3f913-139">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="3f913-140">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="3f913-140">If this directory doesn't exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3f913-141">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="3f913-141">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`
