---
title: Konfigurieren von WCF-Diensten in Code
description: Erfahren Sie, wie Sie WCF-Dienste mithilfe von Code anstelle von Konfigurationsdateien für selbstgeh ostete und im Internet gehostete Dienste konfigurieren können.
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: 975eafea5a153287f5ccc71b9aa342c12391004e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689978"
---
# <a name="configuring-wcf-services-in-code"></a><span data-ttu-id="7d12c-103">Konfigurieren von WCF-Diensten in Code</span><span class="sxs-lookup"><span data-stu-id="7d12c-103">Configuring WCF Services in Code</span></span>
<span data-ttu-id="7d12c-104">Windows Communication Foundation (WCF) ermöglicht es Entwicklern, Dienste mithilfe von Konfigurationsdateien oder Code zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7d12c-104">Windows Communication Foundation (WCF) allows developers to configure services using configuration files or code.</span></span>  <span data-ttu-id="7d12c-105">Konfigurationsdateien sind nützlich, wenn ein Dienst konfiguriert werden muss, nachdem er bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7d12c-105">Configuration files are useful when a service needs to be configured after being deployed.</span></span> <span data-ttu-id="7d12c-106">Bei der Verwendung von Konfigurationsdateien muss ein IT-Experte nur die Konfigurationsdatei aktualisieren, es ist keine Neukompilierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d12c-106">When using configuration files, an IT professional only needs to update the configuration file, no recompilation is required.</span></span> <span data-ttu-id="7d12c-107">Konfigurationsdateien können jedoch komplex und schwierig zu pflegen sein.</span><span class="sxs-lookup"><span data-stu-id="7d12c-107">Configuration files, however, can be complex and difficult to maintain.</span></span> <span data-ttu-id="7d12c-108">Das Debuggen von Konfigurationsdateien wird nicht unterstützt. Auf Konfigurationselemente wird über den Namen verwiesen, was die Erstellung von Konfigurationsdateien fehleranfällig und schwierig macht.</span><span class="sxs-lookup"><span data-stu-id="7d12c-108">There is no support for debugging configuration files and configuration elements are referenced by names which makes authoring configuration files error-prone and difficult.</span></span> <span data-ttu-id="7d12c-109">WCF ermöglicht Ihnen außerdem das Konfigurieren von Diensten im Code.</span><span class="sxs-lookup"><span data-stu-id="7d12c-109">WCF also allows you to configure services in code.</span></span> <span data-ttu-id="7d12c-110">In früheren Versionen von WCF (4,0 und früher) war das Konfigurieren von Diensten im Code in selbstgeh osteten Szenarien ganz einfach <xref:System.ServiceModel.ServiceHost> . mit der-Klasse haben Sie die Möglichkeit, Endpunkte und Verhaltensweisen vor dem Aufrufen von Service Host. Open zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7d12c-110">In earlier versions of WCF (4.0 and earlier) configuring services in code was easy in self-hosted scenarios, the <xref:System.ServiceModel.ServiceHost> class allowed you to configure endpoints and behaviors prior to calling ServiceHost.Open.</span></span> <span data-ttu-id="7d12c-111">In webgehosteten Szenarien haben Sie jedoch keinen direkten Zugriff auf die <xref:System.ServiceModel.ServiceHost>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d12c-111">In web hosted scenarios, however, you don’t have direct access to the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="7d12c-112">Um einen webgehosteten Dienst zu konfigurieren, mussten Sie eine `System.ServiceModel.ServiceHostFactory` erstellen, durch die ein <xref:System.ServiceModel.Activation.ServiceHostFactory> erstellt und alle erforderlichen Konfigurationsschritte ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="7d12c-112">To configure a web hosted service you were required to create a `System.ServiceModel.ServiceHostFactory` that created the <xref:System.ServiceModel.Activation.ServiceHostFactory> and performed any needed configuration.</span></span> <span data-ttu-id="7d12c-113">Ab .NET Framework 4,5 bietet WCF eine einfachere Möglichkeit, selbstgeh ostete und im Internet gehostete Dienste im Code zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7d12c-113">Starting with .NET Framework 4.5, WCF provides an easier way to configure both self-hosted and web hosted services in code.</span></span>

## <a name="the-configure-method"></a><span data-ttu-id="7d12c-114">Die Configure-Methode</span><span class="sxs-lookup"><span data-stu-id="7d12c-114">The Configure method</span></span>
 <span data-ttu-id="7d12c-115">Definieren Sie einfach in der Dienstimplementierungsklasse die öffentliche statische Methode `Configure` mit der folgenden Signatur:</span><span class="sxs-lookup"><span data-stu-id="7d12c-115">Simply define a public static method called `Configure` with the following signature in your service implementation class:</span></span>

```csharp
public static void Configure(ServiceConfiguration config)
```

 <span data-ttu-id="7d12c-116">Die Configure-Methode akzeptiert eine <xref:System.ServiceModel.ServiceConfiguration>-Instanz, die es den Entwicklern ermöglicht, Endpunkte und Verhalten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7d12c-116">The Configure method takes a <xref:System.ServiceModel.ServiceConfiguration> instance that enables the developer to add endpoints and behaviors.</span></span> <span data-ttu-id="7d12c-117">Diese Methode wird von WCF aufgerufen, bevor der Dienst Host geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="7d12c-117">This method is called by WCF before the service host is opened.</span></span> <span data-ttu-id="7d12c-118">Sofern definiert, werden alle Dienstkonfigurationseinstellungen in der Datei app.config oder web.config ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7d12c-118">When defined, any service configuration settings specified in an app.config or web.config file will be ignored.</span></span>

 <span data-ttu-id="7d12c-119">Der folgende Codeausschnitt zeigt, wie die `Configure`-Methode definiert wird und ein Dienstendpunkt, ein Endpunktverhalten und Dienstverhalten hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="7d12c-119">The following code snippet illustrates how to define the `Configure` method and add a service endpoint, an endpoint behavior and service behaviors:</span></span>

```csharp
public class Service1 : IService1
    {
        public static void Configure(ServiceConfiguration config)
        {
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));
            se.Behaviors.Add(new MyEndpointBehavior());
            config.AddServiceEndpoint(se);

            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });
        }

        public string GetData(int value)
        {
            return $"You entered: {value}";
        }

        public CompositeType GetDataUsingDataContract(CompositeType composite)
        {
            if (composite == null)
            {
                throw new ArgumentNullException("composite");
            }
            if (composite.BoolValue)
            {
                composite.StringValue += "Suffix";
            }
            return composite;
        }
    }
```

 <span data-ttu-id="7d12c-120">Um ein Protokoll, z. B. HTTPS, für einen Dienst zu aktivieren, können Sie entweder explizit einen Endpunkt hinzufügen, der das Protokoll verwendet, oder Sie können automatisch Endpunkte durch Aufrufen von ServiceConfiguration.EnableProtocol(Binding) hinzufügen. Dabei wird ein Endpunkt für jede Basisadresse, die mit dem Protokoll kompatibel ist, und für jeden definierten Dienstvertrag hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7d12c-120">To enable a protocol such as https for a service, you can either explicitly add an endpoint that uses the protocol or you can automatically add endpoints by calling ServiceConfiguration.EnableProtocol(Binding) which adds an endpoint for each base address compatible with the protocol and each service contract defined.</span></span> <span data-ttu-id="7d12c-121">Der folgende Code veranschaulicht die Verwendung der ServiceConfiguration.EnableProtocol-Methode:</span><span class="sxs-lookup"><span data-stu-id="7d12c-121">The following code illustrates how to use the ServiceConfiguration.EnableProtocol method:</span></span>

```csharp
public class Service1 : IService1
{
    public string GetData(int value);
    public static void Configure(ServiceConfiguration config)
    {
        // Enable "Add Service Reference" support
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });
       // set up support for http, https, net.tcp, net.pipe
       config.EnableProtocol(new BasicHttpBinding());
       config.EnableProtocol(new BasicHttpsBinding());
       config.EnableProtocol(new NetTcpBinding());
       config.EnableProtocol(new NetNamedPipeBinding());
       // add an extra BasicHttpBinding endpoint at http:///basic
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");
    }
}
```

 <span data-ttu-id="7d12c-122">Die Einstellungen im Abschnitt <`protocolMappings`> werden nur verwendet, wenn dem Programm gesteuert keine Anwendungs Endpunkte hinzugefügt werden <xref:System.ServiceModel.ServiceConfiguration> . Optional können Sie die Dienst Konfiguration aus der Standard Anwendungs Konfigurationsdatei laden, indem Sie aufrufen <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> und dann die Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="7d12c-122">The settings in the <`protocolMappings`> section are only used if no application endpoints are added to the <xref:System.ServiceModel.ServiceConfiguration> programmatically.You can optionally load the service configuration from the default application configuration file by calling <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> and then change the settings.</span></span> <span data-ttu-id="7d12c-123">Sie können auch mit der <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration>-Klasse die Konfiguration aus einer zentralen Konfiguration laden.</span><span class="sxs-lookup"><span data-stu-id="7d12c-123">The <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> class also allows you to load configuration from a centralized configuration.</span></span> <span data-ttu-id="7d12c-124">Im folgenden Code wird veranschaulicht, wie dies implementiert wird:</span><span class="sxs-lookup"><span data-stu-id="7d12c-124">The following code illustrates how to implement this:</span></span>

```csharp
public class Service1 : IService1
{
    public void DoWork();
    public static void Configure(ServiceConfiguration config)
    {
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="7d12c-125">Beachten Sie, dass <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> <`host`> Einstellungen innerhalb des <`service`>-Tags <`system.serviceModel`> ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7d12c-125">Note that <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ignores <`host`> settings within the <`service`> tag of <`system.serviceModel`>.</span></span> <span data-ttu-id="7d12c-126">Konzeptionell ist <`host`> die Host Konfiguration, nicht die Dienst Konfiguration, und Sie wird geladen, bevor die Configure-Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7d12c-126">Conceptually, <`host`> is about host configuration, not service configuration, and it gets loaded before the Configure method executes.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d12c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d12c-127">See also</span></span>

- [<span data-ttu-id="7d12c-128">Konfigurieren von Diensten mit Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="7d12c-128">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)
- [<span data-ttu-id="7d12c-129">Konfigurieren von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="7d12c-129">Configuring Client Behaviors</span></span>](configuring-client-behaviors.md)
- [<span data-ttu-id="7d12c-130">Vereinfachte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7d12c-130">Simplified Configuration</span></span>](simplified-configuration.md)
- [<span data-ttu-id="7d12c-131">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7d12c-131">Configuration</span></span>](./samples/configuration-sample.md)
- [<span data-ttu-id="7d12c-132">Konfigurationsbasierte Aktivierung unter IIS und WAS</span><span class="sxs-lookup"><span data-stu-id="7d12c-132">Configuration-Based Activation in IIS and WAS</span></span>](./feature-details/configuration-based-activation-in-iis-and-was.md)
- [<span data-ttu-id="7d12c-133">Konfiguration und Metadatenunterstützung</span><span class="sxs-lookup"><span data-stu-id="7d12c-133">Configuration and Metadata Support</span></span>](./extending/configuration-and-metadata-support.md)
- [<span data-ttu-id="7d12c-134">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7d12c-134">Configuration</span></span>](./diagnostics/exceptions-reference/configuration.md)
- [<span data-ttu-id="7d12c-135">Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7d12c-135">How to: Specify a Service Binding in Configuration</span></span>](how-to-specify-a-service-binding-in-configuration.md)
- [<span data-ttu-id="7d12c-136">Vorgehensweise: Erstellen eines Dienstendpunkts in einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7d12c-136">How to: Create a Service Endpoint in Configuration</span></span>](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [<span data-ttu-id="7d12c-137">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="7d12c-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="7d12c-138">Vorgehensweise: Angeben einer Clientbindung in einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7d12c-138">How to: Specify a Client Binding in Configuration</span></span>](how-to-specify-a-client-binding-in-configuration.md)
