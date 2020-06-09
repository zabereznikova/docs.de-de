---
title: Kanalfactory und Zwischenspeichern
ms.date: 03/30/2017
ms.assetid: 954f030e-091c-4c0e-a7a2-10f9a6b1f529
ms.openlocfilehash: 5b8348a98b484ca08e3dbeba141dc49825c8c071
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84587364"
---
# <a name="channel-factory-and-caching"></a><span data-ttu-id="b7111-102">Kanalfactory und Zwischenspeichern</span><span class="sxs-lookup"><span data-stu-id="b7111-102">Channel Factory and Caching</span></span>

<span data-ttu-id="b7111-103">WCF-Clientanwendungen verwenden die <xref:System.ServiceModel.ChannelFactory%601>-Klasse, um einen Kommunikationskanal mit einem WCF-Dienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7111-103">WCF client applications use the <xref:System.ServiceModel.ChannelFactory%601> class to create a communication channel with a WCF service.</span></span>  <span data-ttu-id="b7111-104">Die Erstellung von <xref:System.ServiceModel.ChannelFactory%601>-Instanzen verursacht einigen Mehraufwand, da sie die folgenden Vorgänge umfasst:</span><span class="sxs-lookup"><span data-stu-id="b7111-104">Creating <xref:System.ServiceModel.ChannelFactory%601> instances incurs some overhead because it involves the following operations:</span></span>

- <span data-ttu-id="b7111-105">Erstellen der <xref:System.ServiceModel.Description.ContractDescription>-Struktur</span><span class="sxs-lookup"><span data-stu-id="b7111-105">Constructing the <xref:System.ServiceModel.Description.ContractDescription> tree</span></span>

- <span data-ttu-id="b7111-106">Reflektieren aller erforderlichen CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="b7111-106">Reflecting all of the required CLR types</span></span>

- <span data-ttu-id="b7111-107">Erstellen des Kanalstapels</span><span class="sxs-lookup"><span data-stu-id="b7111-107">Constructing the channel stack</span></span>

- <span data-ttu-id="b7111-108">Freigeben von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b7111-108">Disposing of resources</span></span>

<span data-ttu-id="b7111-109">Um den Mehraufwand zu minimieren, kann WCF Kanalfactorys zwischenspeichern, wenn Sie einen WCF-Clientproxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7111-109">To help minimize this overhead, WCF can cache channel factories when you are using a WCF client proxy.</span></span>

> [!TIP]
> <span data-ttu-id="b7111-110">Sie können die Erstellung von Kanalfactorys direkt steuern, wenn Sie die <xref:System.ServiceModel.ChannelFactory%601>-Klasse direkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7111-110">You have direct control over channel factory creation when you use the <xref:System.ServiceModel.ChannelFactory%601> class directly.</span></span>

<span data-ttu-id="b7111-111">WCF-Client Proxys, die mit dem [Service Model Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) generiert werden, werden von abgeleitet <xref:System.ServiceModel.ClientBase%601> .</span><span class="sxs-lookup"><span data-stu-id="b7111-111">WCF client proxies generated with [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) are derived from <xref:System.ServiceModel.ClientBase%601>.</span></span> <span data-ttu-id="b7111-112"><xref:System.ServiceModel.ClientBase%601> definiert eine statische <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A>-Eigenschaft, die das Cachingverhalten der Kanalfactory definiert.</span><span class="sxs-lookup"><span data-stu-id="b7111-112"><xref:System.ServiceModel.ClientBase%601> defines a static <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property that defines channel factory caching behavior.</span></span> <span data-ttu-id="b7111-113">Cacheeinstellungen gelten für einen bestimmten Typ.</span><span class="sxs-lookup"><span data-stu-id="b7111-113">Cache settings are made for a specific type.</span></span> <span data-ttu-id="b7111-114">Wenn `ClientBase<ITest>.CacheSettings` Sie z. b. auf einen der unten definierten Werte festlegen, wirkt sich dies nur auf Proxy/ClientBase vom Typ aus `ITest` .</span><span class="sxs-lookup"><span data-stu-id="b7111-114">For example, setting  `ClientBase<ITest>.CacheSettings` to one of the values defined below will affect only those proxy/ClientBase of type `ITest`.</span></span> <span data-ttu-id="b7111-115">Die Cacheeinstellung für eine bestimmte <xref:System.ServiceModel.ClientBase%601> ist unveränderlich, sobald die erste Proxy/ClientBase-Instanz erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b7111-115">The cache setting for a particular <xref:System.ServiceModel.ClientBase%601> is immutable as soon as the first proxy/ClientBase instance is created.</span></span>

## <a name="specifying-caching-behavior"></a><span data-ttu-id="b7111-116">Angeben des Cachingverhaltens</span><span class="sxs-lookup"><span data-stu-id="b7111-116">Specifying Caching Behavior</span></span>

<span data-ttu-id="b7111-117">Das Cachingverhalten wird angegeben, indem die <xref:System.ServiceModel.ClientBase%601.CacheSetting>-Eigenschaft auf einen der folgenden Werte festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="b7111-117">Caching behavior is specified by setting the <xref:System.ServiceModel.ClientBase%601.CacheSetting> property to one of the following values.</span></span>

|<span data-ttu-id="b7111-118">Wert der Cacheeinstellung</span><span class="sxs-lookup"><span data-stu-id="b7111-118">Cache Setting Value</span></span>|<span data-ttu-id="b7111-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b7111-119">Description</span></span>|
|-------------------------|-----------------|
|<xref:System.ServiceModel.CacheSetting.AlwaysOn>|<span data-ttu-id="b7111-120">Alle Instanzen von <xref:System.ServiceModel.ClientBase%601> in der Anwendungsdomäne können am Caching teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="b7111-120">All instances of <xref:System.ServiceModel.ClientBase%601> within the app-domain can participate in caching.</span></span> <span data-ttu-id="b7111-121">Der Entwickler hat bestimmt, dass die Sicherheit des Cachings nicht gefährdet wird.</span><span class="sxs-lookup"><span data-stu-id="b7111-121">The developer has determined that there are no adverse security implications to caching.</span></span> <span data-ttu-id="b7111-122">Die Zwischenspeicherung wird auch dann nicht deaktiviert, wenn auf die sicherheitsrelevanten Eigenschaften von <xref:System.ServiceModel.ClientBase%601> zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="b7111-122">Caching will not be turned off even if "security-sensitive" properties on <xref:System.ServiceModel.ClientBase%601> are accessed.</span></span> <span data-ttu-id="b7111-123">Die "sicherheitsrelevanten" Eigenschaften von <xref:System.ServiceModel.ClientBase%601> sind <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> , <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> und <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A> .</span><span class="sxs-lookup"><span data-stu-id="b7111-123">The "security-sensitive" properties of <xref:System.ServiceModel.ClientBase%601> are <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>, <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> and <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>.</span></span>|
|<xref:System.ServiceModel.CacheSetting.Default>|<span data-ttu-id="b7111-124">Nur Instanzen von <xref:System.ServiceModel.ClientBase%601>, die aus in den Konfigurationsdateien definierten Endpunkten erstellt wurden, nehmen am Caching innerhalb der Anwendungsdomäne teil.</span><span class="sxs-lookup"><span data-stu-id="b7111-124">Only instances of <xref:System.ServiceModel.ClientBase%601> created from endpoints defined in configuration files participate in caching within the app-domain.</span></span> <span data-ttu-id="b7111-125">Alle Instanzen von <xref:System.ServiceModel.ClientBase%601>, die innerhalb dieser Anwendungsdomäne programmgesteuert erstellt wurden, nehmen nicht am Caching teil.</span><span class="sxs-lookup"><span data-stu-id="b7111-125">Any instances of <xref:System.ServiceModel.ClientBase%601> created programmatically within that app-domain will not participate in caching.</span></span> <span data-ttu-id="b7111-126">Außerdem wird das Zwischenspeichern für eine Instanz von deaktiviert, <xref:System.ServiceModel.ClientBase%601> sobald auf eine ihrer "sicherheitsrelevanten" Eigenschaften zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="b7111-126">Also, caching will be disabled for an instance of <xref:System.ServiceModel.ClientBase%601> once any of its "security-sensitive" properties is accessed.</span></span>|
|<xref:System.ServiceModel.CacheSetting.AlwaysOff>|<span data-ttu-id="b7111-127">Das Caching wird für alle <xref:System.ServiceModel.ClientBase%601>-Instanzen eines bestimmten Typs innerhalb der betreffenden Anwendungsdomäne deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b7111-127">Caching is turned off for all instances of <xref:System.ServiceModel.ClientBase%601> of a particular type within the app-domain in question.</span></span>|

<span data-ttu-id="b7111-128">In den folgenden Codeausschnitten wird die Verwendung der <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A>-Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b7111-128">The following code snippets illustrate how to use the <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property.</span></span>

```csharp
class Program
{
   static void Main(string[] args)
   {
      ClientBase<ITest>.CacheSettings = CacheSettings.AlwaysOn;
      foreach (string msg in messages)
      {
         using (TestClient proxy = new TestClient (new BasicHttpBinding(), new EndpointAddress(address)))
         {
            // ...
            proxy.Test(msg);
            // ...
         }
      }
   }
}
// Generated by SvcUtil.exe
public partial class TestClient : System.ServiceModel.ClientBase, ITest { }
```

<span data-ttu-id="b7111-129">Im obigen Code verwenden alle Instanzen von `TestClient` die gleiche Kanalfactory.</span><span class="sxs-lookup"><span data-stu-id="b7111-129">In the above code, all instances of `TestClient` will use the same channel factory.</span></span>

```csharp
class Program
{
   static void Main(string[] args)
   {
      ClientBase.CacheSettings = CacheSettings.Default;
      int i = 1;
      foreach (string msg in messages)
      {
         using (TestClient proxy = new TestClient ("MyEndpoint", new EndpointAddress(address)))
         {
            if (i == 4)
            {
               ServiceEndpoint endpoint = proxy.Endpoint;
               ... // use endpoint in some way
            }
            proxy.Test(msg);
         }
         i++;
   }
}

// Generated by SvcUtil.exe
public partial class TestClient : System.ServiceModel.ClientBase, ITest {}
```

<span data-ttu-id="b7111-130">Im obigen Beispiel verwenden alle Instanzen von `TestClient` die gleiche Kanalfactory, mit Ausnahme von #4.</span><span class="sxs-lookup"><span data-stu-id="b7111-130">In the example above, all instances of `TestClient` would use the same channel factory except instance #4.</span></span> <span data-ttu-id="b7111-131">Instanz #4 verwendet eine Kanalfactory, die speziell für diesen Zweck erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b7111-131">Instance #4 would use a channel factory that is created specifically for its use.</span></span> <span data-ttu-id="b7111-132">Diese Einstellung eignet sich für Szenarien, in denen ein bestimmter Endpunkt unterschiedliche Sicherheitseinstellungen anderer Endpunkte desselben Kanalfactorytyps (in diesem Fall `ITest`) benötigt.</span><span class="sxs-lookup"><span data-stu-id="b7111-132">This setting would work for scenarios where a particular endpoint needs different security settings from the other endpoints of the same channel factory type (in this case `ITest`).</span></span>

```csharp
class Program
{
   static void Main(string[] args)
   {
      ClientBase.CacheSettings = CacheSettings.AlwaysOff;
      foreach (string msg in messages)
      {
         using (TestClient proxy = new TestClient ("MyEndpoint", new EndpointAddress(address)))
         {
            proxy.Test(msg);
         }
      }
   }
}

// Generated by SvcUtil.exe
public partial class TestClient : System.ServiceModel.ClientBase, ITest {}
```

<span data-ttu-id="b7111-133">Im obigen Beispiel verwenden alle Instanzen von `TestClient` verschiedene Kanalfactorys.</span><span class="sxs-lookup"><span data-stu-id="b7111-133">In the example above, all instances of `TestClient` would use different channel factories.</span></span> <span data-ttu-id="b7111-134">Dies ist nützlich, wenn jeder Endpunkt verschiedene Sicherheitsanforderungen hat und das Caching keinen Sinn macht.</span><span class="sxs-lookup"><span data-stu-id="b7111-134">This is useful when each endpoint has different security requirements and it makes no sense to cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7111-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7111-135">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601>
- [<span data-ttu-id="b7111-136">Erstellen von Clients</span><span class="sxs-lookup"><span data-stu-id="b7111-136">Building Clients</span></span>](../building-clients.md)
- [<span data-ttu-id="b7111-137">Clients</span><span class="sxs-lookup"><span data-stu-id="b7111-137">Clients</span></span>](clients.md)
- [<span data-ttu-id="b7111-138">Zugreifen auf Dienste mithilfe eines WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="b7111-138">Accessing Services Using a WCF Client</span></span>](../accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="b7111-139">Vorgehensweise: Verwenden der ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="b7111-139">How to: Use the ChannelFactory</span></span>](how-to-use-the-channelfactory.md)
