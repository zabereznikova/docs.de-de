---
title: Aufrufen eines REST-Diensts aus einem WCF-Dienst
description: Erfahren Sie, wie Sie einen WCF-Dienst verwenden, um den richtigen Kontext mit einem Dienst im Rest-Stil zu verwenden, indem Sie einen Bereich erstellen und den Dienst im Rest-Stil von diesem Bereich aus aufrufen.
ms.date: 03/30/2017
ms.assetid: 77df81d8-7f53-4daf-8d2d-bf7996e94d5a
ms.openlocfilehash: 15f468923cf55feb85e7aeca1a2cc5e38050d665
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245296"
---
# <a name="calling-a-rest-style-service-from-a-wcf-service"></a><span data-ttu-id="59eda-103">Aufrufen eines REST-Diensts aus einem WCF-Dienst</span><span class="sxs-lookup"><span data-stu-id="59eda-103">Calling a REST-style service from a WCF service</span></span>

<span data-ttu-id="59eda-104">Beim Aufrufen eines REST-Diensts in einem regulären (SOAP-basierten) WCF-Dienst überschreibt der Vorgangskontext in der Dienstmethode (die Informationen über die eingehende Anforderung enthält) den Kontext, der von der ausgehenden Anforderung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="59eda-104">When calling a REST-style service from a regular (SOAP-based) WCF service, the operation context on the service method (which contains information about the incoming request) overrides the context which should be used by the outgoing request.</span></span> <span data-ttu-id="59eda-105">Dies bewirkt, dass HTTP GET-Anforderungen in HTTP POST-Anforderungen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="59eda-105">This causes HTTP GET requests to change to HTTP POST requests.</span></span> <span data-ttu-id="59eda-106">Um zu erzwingen, dass der WCF-Dienst den richtigen Kontext zum Aufrufen des REST-Diensts verwendet, erstellen Sie einen neuen <xref:System.ServiceModel.OperationContextScope>, und rufen Sie den REST-Dienst aus dem Vorgangskontextbereich auf.</span><span class="sxs-lookup"><span data-stu-id="59eda-106">To force the WCF service to use the right context for calling the REST-style service, create a new <xref:System.ServiceModel.OperationContextScope> and call the REST-style service from inside the operation context scope.</span></span> <span data-ttu-id="59eda-107">In diesem Thema wird das Erstellen eines einfachen Beispiels beschrieben, das dieses Verfahren veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="59eda-107">This topic will describe how to create a simple sample that illustrates this technique.</span></span>

## <a name="define-the-rest-style-service-contract"></a><span data-ttu-id="59eda-108">Definieren des REST-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="59eda-108">Define the REST-style service contract</span></span>

<span data-ttu-id="59eda-109">Definieren Sie einen einfachen REST-Dienstvertrag:</span><span class="sxs-lookup"><span data-stu-id="59eda-109">Define a simple  REST-style service contract:</span></span>

```csharp
[ServiceContract]
public interface IRestInterface
{
    [OperationContract, WebGet]
    int Add(int x, int y);

    [OperationContract, WebGet]
    string Echo(string input);
}
```

## <a name="implement-the-rest-style-service-contract"></a><span data-ttu-id="59eda-110">Implementieren des REST-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="59eda-110">Implement the REST-style service contract</span></span>

<span data-ttu-id="59eda-111">Implementieren Sie den REST-Dienstvertrag:</span><span class="sxs-lookup"><span data-stu-id="59eda-111">Implement the REST-style service contract:</span></span>

```csharp
public class RestService : IRestInterface
{
    public int Add(int x, int y)
    {
        return x + y;
    }

    public string Echo(string input)
    {
        return input;
    }
}
```

## <a name="define-the-wcf-service-contract"></a><span data-ttu-id="59eda-112">Definieren des WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="59eda-112">Define the WCF service contract</span></span>

<span data-ttu-id="59eda-113">Definieren Sie einen WCF-Dienstvertrag, der zum Aufrufen des REST-Diensts verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="59eda-113">Define a WCF service contract  that will be used to call the REST-style service:</span></span>

```csharp
[ServiceContract]
public interface INormalInterface
{
    [OperationContract]
    int CallAdd(int x, int y);

    [OperationContract]
    string CallEcho(string input);
}
```

## <a name="implement-the-wcf-service-contract"></a><span data-ttu-id="59eda-114">Implementieren des WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="59eda-114">Implement the WCF service contract</span></span>

<span data-ttu-id="59eda-115">Implementieren Sie den WCF-Dienstvertrag:</span><span class="sxs-lookup"><span data-stu-id="59eda-115">Implement the WCF service contract:</span></span>

```csharp
public class NormalService : INormalInterface
{
    static MyRestClient client = new MyRestClient(RestServiceBaseAddress);
    public int CallAdd(int x, int y)
    {
        return client.Add(x, y);
    }

    public string CallEcho(string input)
    {
        return client.Echo(input);
    }
}
```

## <a name="create-the-client-proxy-for-the-rest-style-service"></a><span data-ttu-id="59eda-116">Erstellen des Clientproxys für den REST-Vertrag</span><span class="sxs-lookup"><span data-stu-id="59eda-116">Create the client proxy for the REST-style service</span></span>

<span data-ttu-id="59eda-117"><xref:System.ServiceModel.ClientBase%601>Die Verwendung von zum Implementieren des Client Proxys.</span><span class="sxs-lookup"><span data-stu-id="59eda-117">Using <xref:System.ServiceModel.ClientBase%601> to implement the client proxy.</span></span> <span data-ttu-id="59eda-118">Für jede aufgerufene Methode wird ein neuer <xref:System.ServiceModel.OperationContextScope> erstellt und zum Aufrufen des Vorgangs verwendet.</span><span class="sxs-lookup"><span data-stu-id="59eda-118">For each method called, a new <xref:System.ServiceModel.OperationContextScope> is created and used to call the operation.</span></span>

```csharp
public class MyRestClient : ClientBase<IRestInterface>, IRestInterface
{
    public MyRestClient(string address)
        : base(new WebHttpBinding(), new EndpointAddress(address))
    {
        this.Endpoint.Behaviors.Add(new WebHttpBehavior());
    }

    public int Add(int x, int y)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Add(x, y);
        }
    }

    public string Echo(string input)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Echo(input);
        }
    }
}
```

## <a name="host-and-call-the-services"></a><span data-ttu-id="59eda-119">Hosten und Aufrufen der Dienste</span><span class="sxs-lookup"><span data-stu-id="59eda-119">Host and call the services</span></span>

<span data-ttu-id="59eda-120">Hosten Sie beide Dienste in einer Konsolenanwendung, und fügen Sie die erforderlichen Endpunkte sowie das erforderliche Verhalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="59eda-120">Host both services in a console app, adding the needed endpoints and behaviors.</span></span> <span data-ttu-id="59eda-121">Rufen Sie dann den regulären WCF-Dienst auf:</span><span class="sxs-lookup"><span data-stu-id="59eda-121">And then call the regular WCF service:</span></span>

```csharp
public static void Main()
{
    ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));
    restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());
    restHost.Open();

    ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));
    normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");
    normalHost.Open();

    Console.WriteLine("Hosts opened");

    ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));
    INormalInterface proxy = factory.CreateChannel();

    Console.WriteLine(proxy.CallAdd(123, 456));
    Console.WriteLine(proxy.CallEcho("Hello world"));
}
```

## <a name="complete-code-listing"></a><span data-ttu-id="59eda-122">Vollständige Codeliste</span><span class="sxs-lookup"><span data-stu-id="59eda-122">Complete code listing</span></span>

<span data-ttu-id="59eda-123">Im Folgenden finden Sie eine vollständige Liste des in diesem Thema implementierten Beispiels:</span><span class="sxs-lookup"><span data-stu-id="59eda-123">The following is a complete listing of the sample implemented in this topic:</span></span>

```csharp
public class CallingRESTSample
{
    static readonly string RestServiceBaseAddress = "http://" + Environment.MachineName + ":8008/Service";
    static readonly string NormalServiceBaseAddress = "http://" + Environment.MachineName + ":8000/Service";

    [ServiceContract]
    public interface IRestInterface
    {
        [OperationContract, WebGet]
        int Add(int x, int y);
        [OperationContract, WebGet]
        string Echo(string input);
    }

    [ServiceContract]
    public interface INormalInterface
    {
        [OperationContract]
        int CallAdd(int x, int y);
        [OperationContract]
        string CallEcho(string input);
    }

    public class RestService : IRestInterface
    {
        public int Add(int x, int y)
        {
            return x + y;
        }

        public string Echo(string input)
        {
            return input;
        }
    }

    public class MyRestClient : ClientBase<IRestInterface>, IRestInterface
    {
        public MyRestClient(string address)
            : base(new WebHttpBinding(), new EndpointAddress(address))
        {
            this.Endpoint.Behaviors.Add(new WebHttpBehavior());
        }

        public int Add(int x, int y)
        {
            using (new OperationContextScope(this.InnerChannel))
            {
                return base.Channel.Add(x, y);
            }
        }

        public string Echo(string input)
        {
            using (new OperationContextScope(this.InnerChannel))
            {
                return base.Channel.Echo(input);
            }
        }
    }

    public class NormalService : INormalInterface
    {
        static MyRestClient client = new MyRestClient(RestServiceBaseAddress);
        public int CallAdd(int x, int y)
        {
            return client.Add(x, y);
        }

        public string CallEcho(string input)
        {
            return client.Echo(input);
        }
    }

    public static void Main()
    {
        ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));
        restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());
        restHost.Open();

        ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));
        normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");
        normalHost.Open();

        Console.WriteLine("Hosts opened");

        ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));
        INormalInterface proxy = factory.CreateChannel();

        Console.WriteLine(proxy.CallAdd(123, 456));
        Console.WriteLine(proxy.CallEcho("Hello world"));
    }
}
```

## <a name="see-also"></a><span data-ttu-id="59eda-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="59eda-124">See also</span></span>

- [<span data-ttu-id="59eda-125">Vorgehensweise: Erstellen eines grundlegenden WCF-Web-HTTP-Diensts</span><span class="sxs-lookup"><span data-stu-id="59eda-125">How to: Create a Basic WCF Web HTTP Service</span></span>](how-to-create-a-basic-wcf-web-http-service.md)
- [<span data-ttu-id="59eda-126">Objektmodell für WCF-Web-HTTP-Programmierung</span><span class="sxs-lookup"><span data-stu-id="59eda-126">WCF Web HTTP Programming Object Model</span></span>](wcf-web-http-programming-object-model.md)
