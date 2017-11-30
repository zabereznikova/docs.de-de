---
title: Implementieren die Microservice-Anwendungsebene mithilfe der Web-API
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Implementieren die Microservice-Anwendungsebene mithilfe der Web-API"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: d505a2561ae9b8dee05e803fd639387b63b28b70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-microservice-application-layer-using-the-web-api"></a><span data-ttu-id="d49bc-104">Implementieren die Microservice-Anwendungsebene mithilfe der Web-API</span><span class="sxs-lookup"><span data-stu-id="d49bc-104">Implementing the microservice application layer using the Web API</span></span>

## <a name="using-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a><span data-ttu-id="d49bc-105">Mithilfe der Abhängigkeitsinjektion beim Einfügen von infrastrukturobjekte in Ihrer Anwendungsebene.</span><span class="sxs-lookup"><span data-stu-id="d49bc-105">Using Dependency Injection to inject infrastructure objects into your application layer</span></span>

<span data-ttu-id="d49bc-106">Wie bereits erwähnt, kann die Anwendungsschicht als Teil des Elements, das Sie erstellen, etwa innerhalb einer Web-API-Projekt oder ein MVC-Web-app-Projekt implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-106">As mentioned previously, the application layer can be implemented as part of the artifact you are building, such as within a Web API project or an MVC web app project.</span></span> <span data-ttu-id="d49bc-107">Im Fall einer Microservice mit ASP.NET Core erstellt werden die Anwendungsebene in der Regel Ihre Web-API-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="d49bc-107">In the case of a microservice built with ASP.NET Core, the application layer will usually be your Web API library.</span></span> <span data-ttu-id="d49bc-108">Gegebenenfalls trennen, was vom benutzerdefinierten Anwendungscode Ebene von ASP.NET Core (ihre Infrastruktur und Ihren Domänencontrollern) stammt, Ihrer Anwendungsebene konnte platziert werden, in einer separaten Klassenbibliothek, die ist jedoch optional.</span><span class="sxs-lookup"><span data-stu-id="d49bc-108">If you want to separate what is coming from ASP.NET Core (its infrastructure plus your controllers) from your custom application layer code, you could also place your application layer in a separate class library, but that is optional.</span></span>

<span data-ttu-id="d49bc-109">Der Anwendungscode für die Ebene von der Reihenfolge Microservice wird z. B. direkt implementiert, als Teil der **Ordering.API** Projekt (einer ASP.NET Core Web-API), als gezeigt in Abbildung 9-19.</span><span class="sxs-lookup"><span data-stu-id="d49bc-109">For instance, the application layer code of the ordering microservice is directly implemented as part of the **Ordering.API** project (an ASP.NET Core Web API project), as shown in Figure 9-19.</span></span>

![](./media/image20.png)

<span data-ttu-id="d49bc-110">**Abbildung 9 – 19**.</span><span class="sxs-lookup"><span data-stu-id="d49bc-110">**Figure 9-19**.</span></span> <span data-ttu-id="d49bc-111">Die Anwendungsebene im Projekt Ordering.API ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="d49bc-111">The application layer in the Ordering.API ASP.NET Core Web API project</span></span>

<span data-ttu-id="d49bc-112">ASP.NET Core beinhaltet eine einfache [integrierte IoC-Container](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (dargestellt durch die IServiceProvider-Schnittstelle), konstruktoreinschleusung standardmäßig unterstützt und ASP.NET macht bestimmte Dienste DI erhältlich.</span><span class="sxs-lookup"><span data-stu-id="d49bc-112">ASP.NET Core includes a simple [built-in IoC container](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (represented by the IServiceProvider interface) that supports constructor injection by default, and ASP.NET makes certain services available through DI.</span></span> <span data-ttu-id="d49bc-113">ASP.NET Core wird mit dem Begriff *Service* für den Sie registrieren, Typen, die über DI-anforderungsumgebung eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-113">ASP.NET Core uses the term *service* for any of the types you register that will be injected through DI.</span></span> <span data-ttu-id="d49bc-114">Sie können den integrierten Container Dienste konfigurieren, in der ConfigureServices-Methode in Ihrer Anwendung Startklasse.</span><span class="sxs-lookup"><span data-stu-id="d49bc-114">You configure the built-in container's services in the ConfigureServices method in your application's Startup class.</span></span> <span data-ttu-id="d49bc-115">Ihre Abhängigkeiten werden in den Diensten implementiert, die ein Typ benötigt.</span><span class="sxs-lookup"><span data-stu-id="d49bc-115">Your dependencies are implemented in the services that a type needs.</span></span>

<span data-ttu-id="d49bc-116">In der Regel möchten Sie Abhängigkeiten einfügen, die infrastrukturobjekte implementieren.</span><span class="sxs-lookup"><span data-stu-id="d49bc-116">Typically, you want to inject dependencies that implement infrastructure objects.</span></span> <span data-ttu-id="d49bc-117">Eine sehr typische Abhängigkeit einfügen ist ein Repository.</span><span class="sxs-lookup"><span data-stu-id="d49bc-117">A very typical dependency to inject is a repository.</span></span> <span data-ttu-id="d49bc-118">Aber Sie können eine Abhängigkeit für Infrastruktur, die Sie möglicherweise einfügen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-118">But you could inject any other infrastructure dependency that you may have.</span></span> <span data-ttu-id="d49bc-119">Einfacher Implementierungen konnte Sie Ihr Unit of Work Muster-Objekt (das EF DbContext-Objekt) direkt einfügen, da ' DbContext ' auch die Implementierung Ihrer Infrastruktur Persistenz-Objekte ist.</span><span class="sxs-lookup"><span data-stu-id="d49bc-119">For simpler implementations, you could directly inject your Unit of Work pattern object (the EF DbContext object), because the DBContext is also the implementation of your infrastructure persistence objects.</span></span>

<span data-ttu-id="d49bc-120">Im folgenden Beispiel sehen Sie, wie die .NET Core durch den Konstruktor der erforderlichen Objekte Räumen ist.</span><span class="sxs-lookup"><span data-stu-id="d49bc-120">In the following example, you can see how .NET Core is injecting the required repository objects through the constructor.</span></span> <span data-ttu-id="d49bc-121">Die Klasse ist Befehlshandler, die im nächsten Abschnitt beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d49bc-121">The class is a command handler, which we will cover in the next section.</span></span>

```csharp
// Sample command handler
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;

    // Constructor where Dependencies are injected
    public CreateOrderCommandHandler(IOrderRepository orderRepository)
    {
        if (orderRepository == null)
        {
            throw new ArgumentNullException(nameof(orderRepository));
        }
        _orderRepository = orderRepository;
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        //
        // ... Additional code
        //
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State,
            message.Country, message.ZipCode);
        var order = new Order(address, message.CardTypeId, message.CardNumber,
            message.CardSecurityNumber,
            message.CardHolderName,
            message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                item.Discount, item.PictureUrl, item.Units);
        }

        //Persist the Order through the Repository
        _orderRepository.Add(order);
        var result = await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
        return result > 0;
    }
}
```

<span data-ttu-id="d49bc-122">Die Klasse verwendet den eingefügten Repositorys durch Ausführen der Transaktion und wechselt der beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="d49bc-122">The class uses the injected repositories to execute the transaction and persist the state changes.</span></span> <span data-ttu-id="d49bc-123">Es spielt keine Rolle, ob diese Klasse Befehlshandler, eine ASP.NET Core Web-API-Controller-Methode ist oder eine [DDD Anwendungsdienst](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span><span class="sxs-lookup"><span data-stu-id="d49bc-123">It does not matter whether that class is a command handler, an ASP.NET Core Web API controller method, or a [DDD Application Service](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span></span> <span data-ttu-id="d49bc-124">Letztlich ist es eine einfache Klasse, die ähnlich wie Befehlshandler-Repositorys, Domänenentitäten und anderen Anwendung Koordinierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d49bc-124">It is ultimately a simple class that uses repositories, domain entities, and other application coordination in a fashion similar to a command handler.</span></span> <span data-ttu-id="d49bc-125">Abhängigkeit Injection funktioniert die gleiche Weise für die erwähnten Klassen, wie im Beispiel mithilfe der Abhängigkeitsinjektion auf den Konstruktor basieren.</span><span class="sxs-lookup"><span data-stu-id="d49bc-125">Dependency Injection works the same way for all the mentioned classes, as in the example using DI based on the constructor.</span></span>

### <a name="registering-the-dependency-implementation-types-and-interfaces-or-abstractions"></a><span data-ttu-id="d49bc-126">Registrierung der Abhängigkeitseigenschaft Implementierungstypen und Schnittstellen oder Abstraktionen</span><span class="sxs-lookup"><span data-stu-id="d49bc-126">Registering the dependency implementation types and interfaces or abstractions</span></span>

<span data-ttu-id="d49bc-127">Bevor Sie die Objekte, die über Konstruktoren eingeschleust verwenden, müssen Sie wissen, wo Sie die Schnittstellen und Klassen, die die Objekte in Ihrer Anwendungsklassen über DI eingeschleust erzeugen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="d49bc-127">Before you use the objects injected through constructors, you need to know where to register the interfaces and classes that produce the objects injected into your application classes through DI.</span></span> <span data-ttu-id="d49bc-128">(Z. B. DI basierend auf den Konstruktor wie vorher gezeigt.)</span><span class="sxs-lookup"><span data-stu-id="d49bc-128">(Like DI based on the constructor, as shown previously.)</span></span>

#### <a name="using-the-built-in-ioc-container-provided-by-aspnet-core"></a><span data-ttu-id="d49bc-129">Mithilfe des integrierten IoC-Containers, die von ASP.NET Core bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="d49bc-129">Using the built-in IoC container provided by ASP.NET Core</span></span>

<span data-ttu-id="d49bc-130">Bei Verwendung den integrierten IoC-Container, die von ASP.NET Core bereitgestellten registrieren Sie die Typen, die Sie in der ConfigureServices-Methode in der Datei Startup.cs wie im folgenden Code einfügen möchten:</span><span class="sxs-lookup"><span data-stu-id="d49bc-130">When you use the built-in IoC container provided by ASP.NET Core, you register the types you want to inject in the ConfigureServices method in the Startup.cs file, as in the following code:</span></span>

```csharp
// Registration of types into ASP.NET Core built-in container
public void ConfigureServices(IServiceCollection services)
{
    // Register out-of-the-box framework services.
    services.AddDbContext<CatalogContext>(c =>
    {
        c.UseSqlServer(Configuration["ConnectionString"]);
    },
    ServiceLifetime.Scoped
    );
    services.AddMvc();
    // Register custom application dependencies.
    services.AddScoped<IMyCustomRepository, MyCustomSQLRepository>();
}
```

<span data-ttu-id="d49bc-131">Das bekannteste Muster beim Registrieren von Typen in einem IoC-Container besteht darin, ein Paar von Typen registrieren – eine Schnittstelle und die zugehörigen Implementierungsklasse.</span><span class="sxs-lookup"><span data-stu-id="d49bc-131">The most common pattern when registering types in an IoC container is to register a pair of types—an interface and its related implementation class.</span></span> <span data-ttu-id="d49bc-132">Wenn Sie ein Objekt aus dem IoC-Container mit einem beliebigen anderen Konstruktor anfordern, fordern Sie dann ein Objekt eines bestimmten Typs der Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d49bc-132">Then when you request an object from the IoC container through any constructor, you request an object of a certain type of interface.</span></span> <span data-ttu-id="d49bc-133">Beispielsweise gibt im vorherigen Beispiel die letzte Zeile an, dass bei einer der Konstruktoren der IMyCustomRepository (Schnittstelle oder Abstraktion) eine Abhängigkeit aufweisen, IoC-Container eine Instanz der Implementierung MyCustomSQLServerRepository eingefügt werden. -Klasse.</span><span class="sxs-lookup"><span data-stu-id="d49bc-133">For instance, in the previous example, the last line states that when any of your constructors have a dependency on IMyCustomRepository (interface or abstraction), the IoC container will inject an instance of the MyCustomSQLServerRepository implementation class.</span></span>

#### <a name="using-the-scrutor-library-for-automatic-types-registration"></a><span data-ttu-id="d49bc-134">Mithilfe der Scrutor-Bibliothek für die Typen der automatischen Registrierung</span><span class="sxs-lookup"><span data-stu-id="d49bc-134">Using the Scrutor library for automatic types registration</span></span>

<span data-ttu-id="d49bc-135">Wenn DI in .NET Core verwenden, empfiehlt es sich in der Lage Überprüfung einer Assemblys und die Typen automatisch gemäß der Konvention zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="d49bc-135">When using DI in .NET Core, you might want to be able to scan an assembly and automatically register its types by convention.</span></span> <span data-ttu-id="d49bc-136">Dieses Feature ist zurzeit nicht verfügbar in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d49bc-136">This feature is not currently available in ASP.NET Core.</span></span> <span data-ttu-id="d49bc-137">Sie können jedoch die [Scrutor](https://github.com/khellang/Scrutor) für diese Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="d49bc-137">However, you can use the [Scrutor](https://github.com/khellang/Scrutor) library for that.</span></span> <span data-ttu-id="d49bc-138">Dieser Ansatz eignet sich, wenn Sie Dutzende von Typen haben, die im IoC-Container registriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-138">This approach is convenient when you have dozens of types that need to be registered in your IoC container.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="d49bc-139">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d49bc-139">Additional resources</span></span>

-   <span data-ttu-id="d49bc-140">**Matthew über allem. Registrieren von Diensten mit Scrutor**
    [*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)</span><span class="sxs-lookup"><span data-stu-id="d49bc-140">**Matthew King. Registering services with Scrutor**
[*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)</span></span>

<!-- -->

-   <span data-ttu-id="d49bc-141">**Kristian Hellang. Scrutor.**</span><span class="sxs-lookup"><span data-stu-id="d49bc-141">**Kristian Hellang. Scrutor.**</span></span> <span data-ttu-id="d49bc-142">GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="d49bc-142">GitHub repo.</span></span>
    [<span data-ttu-id="d49bc-143">*https://github.com/khellang/Scrutor*</span><span class="sxs-lookup"><span data-stu-id="d49bc-143">*https://github.com/khellang/Scrutor*</span></span>](https://github.com/khellang/Scrutor)

#### <a name="using-autofac-as-an-ioc-container"></a><span data-ttu-id="d49bc-144">Verwenden Autofac als IoC-container</span><span class="sxs-lookup"><span data-stu-id="d49bc-144">Using Autofac as an IoC container</span></span>

<span data-ttu-id="d49bc-145">Sie können auch zusätzliche IoC-Container verwenden, und schließen Sie diese in die Pipeline von ASP.NET Core, wie in der Reihenfolge Microservice in eShopOnContainers, der verwendet [Autofac](https://autofac.org/).</span><span class="sxs-lookup"><span data-stu-id="d49bc-145">You can also use additional IoC containers and plug them into the ASP.NET Core pipeline, as in the ordering microservice in eShopOnContainers, which uses [Autofac](https://autofac.org/).</span></span> <span data-ttu-id="d49bc-146">Bei Verwendung von Autofac werden in der Regel die Typen über Module, die ermöglichen es Ihnen, teilen die Registrierung Typen zwischen mehreren Dateien je nach, die Typen befinden, ebenso wie Sie die Anwendungstypen, die über mehrere Klassenbibliotheken verteilt aufweisen können, registriert.</span><span class="sxs-lookup"><span data-stu-id="d49bc-146">When using Autofac you typically register the types via modules, which allow you to split the registration types between multiple files depending on where your types are, just as you could have the application types distributed across multiple class libraries.</span></span>

<span data-ttu-id="d49bc-147">Folgendes ist z. B. die [Autofac Anwendungsmodul](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) für die [Ordering.API Web-API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) Projekt mit den Typen, die Sie einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="d49bc-147">For example, the following is the [Autofac application module](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) for the [Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) project with the types you will want to inject.</span></span>

```csharp
public class ApplicationModule
    :Autofac.Module
{
    public string QueriesConnectionString { get; }
    public ApplicationModule(string qconstr)
    {
        QueriesConnectionString = qconstr;
    }

    protected override void Load(ContainerBuilder builder)
    {
        builder.Register(c => new OrderQueries(QueriesConnectionString))
            .As<IOrderQueries>()
            .InstancePerLifetimeScope();
        builder.RegisterType<BuyerRepository>()
            .As<IBuyerRepository>()
            .InstancePerLifetimeScope();
        builder.RegisterType<OrderRepository>()
            .As<IOrderRepository>()
            .InstancePerLifetimeScope();
        builder.RegisterType<RequestManager>()
            .As<IRequestManager>()
            .InstancePerLifetimeScope();
   }
}
```

<span data-ttu-id="d49bc-148">Der Registrierungsvorgang und die Konzepte sind sehr ähnlich wie die Typen mit dem integrierten ASP.NET Core iOS-Container zu registrieren, aber die Syntax, die bei Verwendung von Autofac ist etwas anders.</span><span class="sxs-lookup"><span data-stu-id="d49bc-148">The registration process and concepts are very similar to the way you can register types with the built-in ASP.NET Core iOS container, but the syntax when using Autofac is a bit different.</span></span>

<span data-ttu-id="d49bc-149">Im Beispielcode wird die Abstraktion IOrderRepository zusammen mit der Implementierungsklasse OrderRepository registriert.</span><span class="sxs-lookup"><span data-stu-id="d49bc-149">In the example code, the abstraction IOrderRepository is registered along with the implementation class OrderRepository.</span></span> <span data-ttu-id="d49bc-150">Dies bedeutet, dass wenn ein Konstruktor eine Abhängigkeit über die IOrderRepository Abstraktion oder Schnittstelle deklariert, IoC-Container eine Instanz der Klasse OrderRepository einfügen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-150">This means that whenever a constructor is declaring a dependency through the IOrderRepository abstraction or interface, the IoC container will inject an instance of the OrderRepository class.</span></span>

<span data-ttu-id="d49bc-151">Der Bereichstyp Instanz bestimmt, wie eine Instanz, die allen Anforderungen für den Dienst oder die Abhängigkeit gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="d49bc-151">The instance scope type determines how an instance is shared between requests for the same service or dependency.</span></span> <span data-ttu-id="d49bc-152">Wenn eine Anforderung für eine Abhängigkeit gestellt wird, kann der IoC-Container Folgendes zurück:</span><span class="sxs-lookup"><span data-stu-id="d49bc-152">When a request is made for a dependency, the IoC container can return the following:</span></span>

-   <span data-ttu-id="d49bc-153">Eine einzelne Instanz pro Lebensdauer Bereich (gemäß dem ASP.NET Core IoC-Container als *im Bereich einer*).</span><span class="sxs-lookup"><span data-stu-id="d49bc-153">A single instance per lifetime scope (referred to in the ASP.NET Core IoC container as *scoped*).</span></span>

-   <span data-ttu-id="d49bc-154">Eine neue Instanz pro Abhängigkeit (gemäß dem ASP.NET Core IoC-Container als *vorübergehenden*).</span><span class="sxs-lookup"><span data-stu-id="d49bc-154">A new instance per dependency (referred to in the ASP.NET Core IoC container as *transient*).</span></span>

-   <span data-ttu-id="d49bc-155">Eine einzelne Instanz, die für alle Objekte, die mit der IoC-Container freigegeben (gemäß dem ASP.NET Core IoC-Container als *Singleton*).</span><span class="sxs-lookup"><span data-stu-id="d49bc-155">A single instance shared across all objects using the IoC container (referred to in the ASP.NET Core IoC container as *singleton*).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="d49bc-156">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d49bc-156">Additional resources</span></span>

-   <span data-ttu-id="d49bc-157">**Einführung in die Abhängigkeitsinjektion in ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)</span><span class="sxs-lookup"><span data-stu-id="d49bc-157">**Introduction to Dependency Injection in ASP.NET Core**
[*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)</span></span>

-   <span data-ttu-id="d49bc-158">**Autofac.**</span><span class="sxs-lookup"><span data-stu-id="d49bc-158">**Autofac.**</span></span> <span data-ttu-id="d49bc-159">Offizieller Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="d49bc-159">Official documentation.</span></span>
    [<span data-ttu-id="d49bc-160">*http://docs.autofac.org/en/Latest/*</span><span class="sxs-lookup"><span data-stu-id="d49bc-160">*http://docs.autofac.org/en/latest/*</span></span>](http://docs.autofac.org/en/latest/)

-   <span data-ttu-id="d49bc-161">**Cesar de la Torre. Vergleichen von ASP.NET Core IoC-Container Dienst Lebensdauer mit Autofac IoC-Container Instanz Bereichen**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-Core-IoC-Service-Life-Times-and-autofac-IoC-Instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="d49bc-161">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="implementing-the-command-and-command-handler-patterns"></a><span data-ttu-id="d49bc-162">Implementieren die Befehl und Befehlshandler Mustern</span><span class="sxs-lookup"><span data-stu-id="d49bc-162">Implementing the Command and Command Handler patterns</span></span>

<span data-ttu-id="d49bc-163">Im Beispiel DI-über-Konstruktor im vorherigen Abschnitt gezeigt wurde der IoC-Container Repositorys über einen Konstruktor in einer Klasse injiziert.</span><span class="sxs-lookup"><span data-stu-id="d49bc-163">In the DI-through-constructor example shown in the previous section, the IoC container was injecting repositories through a constructor in a class.</span></span> <span data-ttu-id="d49bc-164">Aber genau, wo wurden diese eingefügt?</span><span class="sxs-lookup"><span data-stu-id="d49bc-164">But exactly where were they injected?</span></span> <span data-ttu-id="d49bc-165">In einer einfachen Web-API (z. B. den Katalog Microservice in eShopOnContainers) fügen Sie sie auf der Ebene des MVC-Controller, in einem Controller-Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="d49bc-165">In a simple Web API (for example, the catalog microservice in eShopOnContainers), you inject them at the MVC controllers level, in a controller constructor.</span></span> <span data-ttu-id="d49bc-166">Allerdings in den anfänglichen Code in diesem Abschnitt (die [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) Klasse aus dem Dienst Ordering.API in eShopOnContainers), die Einfügung des Abhängigkeiten erfolgt über den Konstruktor eines bestimmten Befehls Handler.</span><span class="sxs-lookup"><span data-stu-id="d49bc-166">However, in the initial code of this section (the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) class from the Ordering.API service in eShopOnContainers), the injection of dependencies is done through the constructor of a particular command handler.</span></span> <span data-ttu-id="d49bc-167">Lassen Sie uns wird erläutert, welche Befehlshandler ist und warum Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d49bc-167">Let us explain what a command handler is and why you would want to use it.</span></span>

<span data-ttu-id="d49bc-168">Das Muster Befehl bezieht sich systemintern auf CQRS-Muster, die weiter oben in diesem Handbuch eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d49bc-168">The Command pattern is intrinsically related to the CQRS pattern that was introduced earlier in this guide.</span></span> <span data-ttu-id="d49bc-169">CQRS verfügt über zwei Seiten.</span><span class="sxs-lookup"><span data-stu-id="d49bc-169">CQRS has two sides.</span></span> <span data-ttu-id="d49bc-170">Der erste Bereich ist Abfragen unter Verwendung der vereinfachte Abfragen mit der [dapper, durch](https://github.com/StackExchange/dapper-dot-net) micro-ORM, die zuvor erläutert wurde.</span><span class="sxs-lookup"><span data-stu-id="d49bc-170">The first area is queries, using simplified queries with the [Dapper](https://github.com/StackExchange/dapper-dot-net) micro ORM, which was explained previously.</span></span> <span data-ttu-id="d49bc-171">Der zweite Bereich ist die Befehle, die der Ausgangspunkt für Transaktionen und der Eingabekanal von außerhalb des Diensts sind.</span><span class="sxs-lookup"><span data-stu-id="d49bc-171">The second area is commands, which are the starting point for transactions, and the input channel from outside the service.</span></span>

<span data-ttu-id="d49bc-172">Wie in Abbildung 9 – 20 dargestellt, das Muster basiert auf Befehle von der Clientseite akzeptieren basierend auf der die Domänenregeln für das Modell verarbeiten und schließlich die Status mit Transaktionen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d49bc-172">As shown in Figure 9-20, the pattern is based on accepting commands from the client side, processing them based on the domain model rules, and finally persisting the states with transactions.</span></span>

![](./media/image21.png)

<span data-ttu-id="d49bc-173">**Abbildung 9 – 20**.</span><span class="sxs-lookup"><span data-stu-id="d49bc-173">**Figure 9-20**.</span></span> <span data-ttu-id="d49bc-174">Überblick über die Befehle oder "transaktionale Seite" in einem CQRS-Muster</span><span class="sxs-lookup"><span data-stu-id="d49bc-174">High-level view of the commands or “transactional side” in a CQRS pattern</span></span>

### <a name="the-command-class"></a><span data-ttu-id="d49bc-175">Die Befehlsklasse</span><span class="sxs-lookup"><span data-stu-id="d49bc-175">The command class</span></span>

<span data-ttu-id="d49bc-176">Ein Befehl ist eine Anforderung für das System zum Ausführen einer Aktion, die den Zustand des Systems ändert.</span><span class="sxs-lookup"><span data-stu-id="d49bc-176">A command is a request for the system to perform an action that changes the state of the system.</span></span> <span data-ttu-id="d49bc-177">Befehle sind imperative und sollte nur einmal verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-177">Commands are imperative, and should be processed just once.</span></span>

<span data-ttu-id="d49bc-178">Da Befehle Erfordernisse sind, sie sind in der Regel mit einem Verb in die imperative Ton zu verwenden (z. B. "erstellen" oder "update") bezeichnet, und sie möglicherweise den aggregierten Typ, z. B. CreateOrderCommand enthalten.</span><span class="sxs-lookup"><span data-stu-id="d49bc-178">Since commands are imperatives, they are typically named with a verb in the imperative mood (for example, "create" or "update"), and they might include the aggregate type, such as CreateOrderCommand.</span></span> <span data-ttu-id="d49bc-179">Im Gegensatz zu einer Veranstaltung ist ein Befehl nicht Fakten aus der Vergangenheit. Es ist nur eine Anforderung, und daher möglicherweise abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="d49bc-179">Unlike an event, a command is not a fact from the past; it is only a request, and thus may be refused.</span></span>

<span data-ttu-id="d49bc-180">Befehle können über die Benutzeroberfläche als Ergebnis ein Benutzer eine Anforderung initiiert oder von einem Prozessmanager stammen, wenn der Prozess-Manager ein Aggregat zum Ausführen einer Aktion weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="d49bc-180">Commands can originate from the UI as a result of a user initiating a request, or from a process manager when the process manager is directing an aggregate to perform an action.</span></span>

<span data-ttu-id="d49bc-181">Ein wichtiges Merkmal eines Befehls ist, dass es nur einmal von einem einzelnen Empfänger verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-181">An important characteristic of a command is that it should be processed just once by a single receiver.</span></span> <span data-ttu-id="d49bc-182">Dies ist ein Befehl ist eine einzelne Aktion oder die Transaktion, die Sie in der Anwendung durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="d49bc-182">This is because a command is a single action or transaction you want to perform in the application.</span></span> <span data-ttu-id="d49bc-183">Beispielsweise sollte der gleichen Reihenfolge Erstellungsbefehl nicht mehr als einmal verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-183">For example, the same order creation command should not be processed more than once.</span></span> <span data-ttu-id="d49bc-184">Dies ist ein wichtiger Unterschied zwischen Befehlen und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-184">This is an important difference between commands and events.</span></span> <span data-ttu-id="d49bc-185">Ereignisse können mehrmals verarbeitet werden, da viele Systeme oder Microservices im Ereignis interessiert sein kann.</span><span class="sxs-lookup"><span data-stu-id="d49bc-185">Events may be processed multiple times, because many systems or microservices might be interested in the event.</span></span>

<span data-ttu-id="d49bc-186">Darüber hinaus ist es wichtig, dass ein Befehl für den Fall, dass der Befehl nicht Idempotent ist nur ein Mal verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-186">In addition, it is important that a command be processed only once in case the command is not idempotent.</span></span> <span data-ttu-id="d49bc-187">Ein Befehl ist Idempotent, wenn sie mehrere Male ausgeführt werden kann ohne das Ergebnis, entweder aufgrund der Natur des Befehls oder aufgrund der Art und Weise, die des Systems den Befehl behandelt, zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d49bc-187">A command is idempotent if it can be executed multiple times without changing the result, either because of the nature of the command, or because of the way the system handles the command.</span></span>

<span data-ttu-id="d49bc-188">Es wird empfohlen, stellen Ihre Befehle und Idempotent aktualisiert, wenn es sinnvoll ist unter Ihrer Domäne Geschäftsregeln und Invarianten.</span><span class="sxs-lookup"><span data-stu-id="d49bc-188">It is a good practice to make your commands and updates idempotent when it makes sense under your domain’s business rules and invariants.</span></span> <span data-ttu-id="d49bc-189">Für die Instanz, um dasselbe Beispiel verwenden, wenn aus irgendeinem Grund (Wiederholungslogik, Hacker, usw.) der gleiche CreateOrder Befehl Ihr System mehrmals erreicht, sollte Sie es identifiziert und stellen Sie sicher, dass Sie nicht mehrere Aufträge erstellen können.</span><span class="sxs-lookup"><span data-stu-id="d49bc-189">For instance, to use the same example, if for any reason (retry logic, hacking, etc.) the same CreateOrder command reaches your system multiple times, you should be able to identify it and ensure that you do not create multiple orders.</span></span> <span data-ttu-id="d49bc-190">Zu diesem Zweck müssen Sie irgendeine der Identität in der Betriebskonsole anzufügen und zu ermitteln, ob der Befehl oder das Update bereits verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="d49bc-190">To do so, you need to attach some kind of identity in the operations and identify whether the command or update was already processed.</span></span>

<span data-ttu-id="d49bc-191">Sie senden ein Befehls an einen einzelnen Empfänger; einen Befehl Veröffentlichen nicht.</span><span class="sxs-lookup"><span data-stu-id="d49bc-191">You send a command to a single receiver; you do not publish a command.</span></span> <span data-ttu-id="d49bc-192">Veröffentlichung ist für die integrationsereignisse, die einen Fakt Status –, dass etwas aufgetreten, und möglicherweise für Ereignisempfänger interessant sein.</span><span class="sxs-lookup"><span data-stu-id="d49bc-192">Publishing is for integration events that state a fact—that something has happened and might be interesting for event receivers.</span></span> <span data-ttu-id="d49bc-193">Im Fall von Ereignissen weist der Verleger keine Aspekte, die über die Empfänger erhalten, das Ereignis oder wie sie es verwenden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-193">In the case of events, the publisher has no concerns about which receivers get the event or what they do it.</span></span> <span data-ttu-id="d49bc-194">Aber integrationsereignisse sind bereits in vorherigen Abschnitten eingeführte anders.</span><span class="sxs-lookup"><span data-stu-id="d49bc-194">But integration events are a different story already introduced in previous sections.</span></span>

<span data-ttu-id="d49bc-195">Ein Befehl ist mit einer Klasse implementiert, die Datenfelder oder Sammlungen mit allen Informationen, die benötigt werden, um die Ausführung dieses Befehls enthält.</span><span class="sxs-lookup"><span data-stu-id="d49bc-195">A command is implemented with a class that contains data fields or collections with all the information that is needed in order to execute that command.</span></span> <span data-ttu-id="d49bc-196">Ein Befehl ist eine besondere Art von Daten übertragen Objekt (DTO), die speziell zum Anfordern von Änderungen oder Transaktionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d49bc-196">A command is a special kind of Data Transfer Object (DTO), one that is specifically used to request changes or transactions.</span></span> <span data-ttu-id="d49bc-197">Der Befehl selbst basiert auf genau die Informationen, die für die mit dem Befehl, und keine weitere Verarbeitung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d49bc-197">The command itself is based on exactly the information that is needed for processing the command, and nothing more.</span></span>

<span data-ttu-id="d49bc-198">Das folgende Beispiel zeigt die vereinfachte CreateOrderCommand-Klasse.</span><span class="sxs-lookup"><span data-stu-id="d49bc-198">The following example shows the simplified CreateOrderCommand class.</span></span> <span data-ttu-id="d49bc-199">Dies ist eine unveränderliche-Befehl, der in der Reihenfolge Microservice in eShopOnContainers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d49bc-199">This is an immutable command that is used in the ordering microservice in eShopOnContainers.</span></span>

```csharp
// DDD and CQRS patterns comment
// Note that it is recommended that yuo implement immutable commands
// In this case, immutability is achieved by having all the setters as private
// plus being able to update the data just once, when creating the object
// through the constructor.
// References on immutable commands:
// http://cqrs.nu/Faq
// https://docs.spine3.org/motivation/immutability.html
// http://blog.gauffin.org/2012/06/griffin-container-introducing-command-support/
// https://msdn.microsoft.com/en-us/library/bb383979.aspx
[DataContract]
public class CreateOrderCommand
    :IAsyncRequest<bool>
{
    [DataMember]
    private readonly List<OrderItemDTO> _orderItems;

    [DataMember]
    public string City { get; private set; }

    [DataMember]
    public string Street { get; private set; }

    [DataMember]
    public string State { get; private set; }

    [DataMember]
    public string Country { get; private set; }

    [DataMember]
    public string ZipCode { get; private set; }

    [DataMember]
    public string CardNumber { get; private set; }

    [DataMember]
    public string CardHolderName { get; private set; }

    [DataMember]
    public DateTime CardExpiration { get; private set; }

    [DataMember]
    public string CardSecurityNumber { get; private set; }

    [DataMember]
    public int CardTypeId { get; private set; }

    [DataMember]
    public IEnumerable<OrderItemDTO> OrderItems => _orderItems;

    public CreateOrderCommand()
    {
        _orderItems = new List<OrderItemDTO>();
    }

    public CreateOrderCommand(List<OrderItemDTO> orderItems, string city,
        string street,
        string state, string country, string zipcode,
        string cardNumber, string cardHolderName, DateTime cardExpiration,
        string cardSecurityNumber, int cardTypeId) : this()
    {
        _orderItems = orderItems;
        City = city;
        Street = street;
        State = state;
        Country = country;
        ZipCode = zipcode;
        CardNumber = cardNumber;
        CardHolderName = cardHolderName;
        CardSecurityNumber = cardSecurityNumber;
        CardTypeId = cardTypeId;
        CardExpiration = cardExpiration;
    }

    public class OrderItemDTO
    {
        public int ProductId { get; set; }
        public string ProductName { get; set; }
        public decimal UnitPrice { get; set; }
        public decimal Discount { get; set; }
        public int Units { get; set; }
        public string PictureUrl { get; set; }
    }
}
```

<span data-ttu-id="d49bc-200">Die Befehlsklasse enthält im Grunde die zum Ausführen einer Geschäftstransaktion mithilfe der domänenmodellobjekten benötigten Daten.</span><span class="sxs-lookup"><span data-stu-id="d49bc-200">Basically, the command class contains all the data you need for performing a business transaction by using the domain model objects.</span></span> <span data-ttu-id="d49bc-201">Daher sind die Befehle einfach Datenstrukturen, die schreibgeschützten Daten und kein Verhalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="d49bc-201">Thus, commands are simply data structures that contain read-only data, and no behavior.</span></span> <span data-ttu-id="d49bc-202">Name des Befehls gibt ihren Zweck an.</span><span class="sxs-lookup"><span data-stu-id="d49bc-202">The command’s name indicates its purpose.</span></span> <span data-ttu-id="d49bc-203">In vielen Sprachen wie C#\#, Befehle werden als Klassen dargestellt, aber sie sind nicht in dem Sinne real objektorientierte "true" Klassen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-203">In many languages like C\#, commands are represented as classes, but they are not true classes in the real object-oriented sense.</span></span>

<span data-ttu-id="d49bc-204">Als eine zusätzliche Eigenschaft sind die Befehle unveränderlich, da die erwartete Verwendung ist, dass sie direkt von der Domänenmodell verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-204">As an additional characteristic, commands are immutable, because the expected usage is that they are processed directly by the domain model.</span></span> <span data-ttu-id="d49bc-205">Sie müssen nicht während ihrer Lebensdauer projizierten ändern.</span><span class="sxs-lookup"><span data-stu-id="d49bc-205">They do not need to change during their projected lifetime.</span></span> <span data-ttu-id="d49bc-206">In einem C\# Klasse Unveränderlichkeit kann erreicht werden, da keine Setter oder andere Methoden, die internen Status ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-206">In a C\# class, immutability can be achieved by not having any setters or other methods that change internal state.</span></span>

<span data-ttu-id="d49bc-207">Z. B. die Befehlsklasse zum Erstellen einer Bestellung ist wahrscheinlich ähnlich im Hinblick auf Daten der Bestellung, die Sie erstellen möchten, aber Sie wahrscheinlich nicht benötigen, dass dieselben Attribute.</span><span class="sxs-lookup"><span data-stu-id="d49bc-207">For example, the command class for creating an order is probably similar in terms of data to the order you want to create, but you probably do not need the same attributes.</span></span> <span data-ttu-id="d49bc-208">Beispielsweise verfügt CreateOrderCommand keine Auftrags-ID, da der Auftrag noch nicht erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d49bc-208">For instance, CreateOrderCommand does not have an order ID, because the order has not been created yet.</span></span>

<span data-ttu-id="d49bc-209">Viele Befehlsklassen kann einfach und erfordert nur wenige Felder über ein Zustand, der geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="d49bc-209">Many command classes can be simple, requiring only a few fields about some state that needs to be changed.</span></span> <span data-ttu-id="d49bc-210">Das wäre der Fall, wenn Sie nur den Status einer Bestellung aus "in Bearbeitung" zu ändern "bezahlt" oder "geliefert", mit dem Befehl etwa wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d49bc-210">That would be the case if you are just changing the status of an order from “in process” to “paid” or “shipped” by using a command similar to the following:</span></span>

```csharp
[DataContract]
public class UpdateOrderStatusCommand
    :IAsyncRequest<bool>
{
    [DataMember]
    public string Status { get; private set; }

    [DataMember]
    public string OrderId { get; private set; }

    [DataMember]
    public string BuyerIdentityGuid { get; private set; }
}
```

<span data-ttu-id="d49bc-211">Einige Entwickler ihre Anforderung Benutzeroberflächenobjekte stellen ihre DTOs Befehl trennen, aber, die geht nur darum, Voreinstellung.</span><span class="sxs-lookup"><span data-stu-id="d49bc-211">Some developers make their UI request objects separate from their command DTOs, but that is just a matter of preference.</span></span> <span data-ttu-id="d49bc-212">Es ist ein zeitraubender Trennung mit nicht viel Nutzwerts, und die Objekte sind nahezu identisch mit der gleichen Form.</span><span class="sxs-lookup"><span data-stu-id="d49bc-212">It is a tedious separation with not much added value, and the objects are almost exactly the same shape.</span></span> <span data-ttu-id="d49bc-213">Beispielsweise sind in verschiedenen eShopOnContainers, die Befehle direkt von der Clientseite.</span><span class="sxs-lookup"><span data-stu-id="d49bc-213">For instance, in eShopOnContainers, the commands come directly from the client side.</span></span>

### <a name="the-command-handler-class"></a><span data-ttu-id="d49bc-214">Der Befehlshandler-Klasse</span><span class="sxs-lookup"><span data-stu-id="d49bc-214">The Command Handler class</span></span>

<span data-ttu-id="d49bc-215">Sie sollten eine bestimmten Befehl Handlerklasse für jeden Befehl implementieren.</span><span class="sxs-lookup"><span data-stu-id="d49bc-215">You should implement a specific command handler class for each command.</span></span> <span data-ttu-id="d49bc-216">Ist die Funktionsweise des Musters, und es ist, in dem Sie das Command-Objekt, das Domänenobjekte und Repository-infrastrukturobjekte verwenden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-216">That is how the pattern works, and it is where you will use the command object, the domain objects, and the infrastructure repository objects.</span></span> <span data-ttu-id="d49bc-217">Der Befehlshandler ist tatsächlich das Kernstück der Anwendungsschicht im Hinblick auf CQRS und DDD.</span><span class="sxs-lookup"><span data-stu-id="d49bc-217">The command handler is in fact the heart of the application layer in terms of CQRS and DDD.</span></span> <span data-ttu-id="d49bc-218">Allerdings sollte die Domänenlogik innerhalb der Domänenklassen enthalten – innerhalb der aggregierten Stämme (Stamm-Entitäten), untergeordneten Entitäten, oder [Domänendienste](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), aber nicht innerhalb der Befehlshandler also eine Klasse von der Anwendung Ebene.</span><span class="sxs-lookup"><span data-stu-id="d49bc-218">However, all the domain logic should be contained within the domain classes—within the aggregate roots (root entities), child entities, or [domain services](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), but not within the command handler, which is a class from the application layer.</span></span>

<span data-ttu-id="d49bc-219">Befehlshandler einen Befehl empfängt und erhält ein Ergebnis aus dem Aggregat, das verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d49bc-219">A command handler receives a command and obtains a result from the aggregate that is used.</span></span> <span data-ttu-id="d49bc-220">Das Ergebnis sollte der Befehl erfolgreich ausgeführt wurde, oder aber eine Ausnahme sein.</span><span class="sxs-lookup"><span data-stu-id="d49bc-220">The result should be either successful execution of the command, or an exception.</span></span> <span data-ttu-id="d49bc-221">Im Falle einer Ausnahme sollte der Systemstatus nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-221">In the case of an exception, the system state should be unchanged.</span></span>

<span data-ttu-id="d49bc-222">Der Befehlshandler fließen i. d. r. die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d49bc-222">The command handler usually takes the following steps:</span></span>

-   <span data-ttu-id="d49bc-223">Er empfängt das Command-Objekt, wie ein DTO (aus der [Vermittler](https://en.wikipedia.org/wiki/Mediator_pattern) oder ein anderes Infrastrukturobjekt).</span><span class="sxs-lookup"><span data-stu-id="d49bc-223">It receives the command object, like a DTO (from the [mediator](https://en.wikipedia.org/wiki/Mediator_pattern) or other infrastructure object).</span></span>

-   <span data-ttu-id="d49bc-224">Er überprüft, dass der Befehl (sofern nicht durch den Vermittler überprüft) gültig ist.</span><span class="sxs-lookup"><span data-stu-id="d49bc-224">It validates that the command is valid (if not validated by the mediator).</span></span>

-   <span data-ttu-id="d49bc-225">Die aggregierten Stamminstanz, die das Ziel des aktuellen Befehls wird instanziiert.</span><span class="sxs-lookup"><span data-stu-id="d49bc-225">It instantiates the aggregate root instance that is the target of the current command.</span></span>

-   <span data-ttu-id="d49bc-226">Er führt die Methode für die aggregierten Stamminstanz Abrufen der erforderlichen Daten aus den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d49bc-226">It executes the method on the aggregate root instance, getting the required data from the command.</span></span>

-   <span data-ttu-id="d49bc-227">Den neuen Zustand des Aggregats in die zugehörige Datenbank weiterhin auftritt.</span><span class="sxs-lookup"><span data-stu-id="d49bc-227">It persists the new state of the aggregate to its related database.</span></span> <span data-ttu-id="d49bc-228">Dieser letzte Vorgang ist die aktuelle Transaktion.</span><span class="sxs-lookup"><span data-stu-id="d49bc-228">This last operation is the actual transaction.</span></span>

<span data-ttu-id="d49bc-229">Normalerweise befasst sich Befehlshandler mit einer einzelnen gesamtverstärkung durch aggregieren Stamm (Stammentität) gesteuert.</span><span class="sxs-lookup"><span data-stu-id="d49bc-229">Typically, a command handler deals with a single aggregate driven by its aggregate root (root entity).</span></span> <span data-ttu-id="d49bc-230">Wenn mehrere Aggregate von den Empfang eines einzelnen Befehls betroffen sein sollen, können Sie Domäne Ereignisse verwenden, Status oder Aktionen über mehrere Aggregate weitergegeben</span><span class="sxs-lookup"><span data-stu-id="d49bc-230">If multiple aggregates should be impacted by the reception of a single command, you could use domain events to propagate states or actions across multiple aggregates</span></span>

<span data-ttu-id="d49bc-231">Wichtig dabei ist, dass bei der Verarbeitung eines Befehls die Domänenlogik innerhalb der Domänenmodell (Aggregate) vollständig gekapselten und bereit für die Komponententests werden soll.</span><span class="sxs-lookup"><span data-stu-id="d49bc-231">The important point here is that when a command is being processed, all the domain logic should be inside the domain model (the aggregates), fully encapsulated and ready for unit testing.</span></span> <span data-ttu-id="d49bc-232">Befehlshandler dient lediglich als eine Möglichkeit, das Domänenmodell aus der Datenbank erhalten und als letzten Schritt informieren Sie die Infrastrukturebene (Repositorys), damit die Änderungen beibehalten, wenn das Modell geändert wird.</span><span class="sxs-lookup"><span data-stu-id="d49bc-232">The command handler just acts as a way to get the domain model from the database, and as the final step, to tell the infrastructure layer (repositories) to persist the changes when the model is changed.</span></span> <span data-ttu-id="d49bc-233">Der Vorteil dieses Ansatzes ist, dass Sie die Domänenlogik in eine isolierte, vollständig gekapselten, umfangreiche, verhaltensbasierten Domänenmodell Umgestalten können, ohne Ändern des Codes in der Anwendung oder Infrastruktur-Ebenen, die sind die Aufgaben, die Ebene (Befehlshandler, Web-API -Repositorys, usw.).</span><span class="sxs-lookup"><span data-stu-id="d49bc-233">The advantage of this approach is that you can refactor the domain logic in an isolated, fully encapsulated, rich, behavioral domain model without changing code in the application or infrastructure layers, which are the plumbing level (command handlers, Web API, repositories, etc.).</span></span>

<span data-ttu-id="d49bc-234">Wenn Befehlshandler komplex sein, mit viel Logik erhalten, kann die anderen Code sein.</span><span class="sxs-lookup"><span data-stu-id="d49bc-234">When command handlers get complex, with too much logic, that can be a code smell.</span></span> <span data-ttu-id="d49bc-235">Überprüfen sie, und findet Domänenlogik gestalten Sie den Code, um dieses Domänenverhalten auf die Methoden der Domänenobjekte (die aggregierten Stamm und untergeordnete Entität) zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="d49bc-235">Review them, and if you find domain logic, refactor the code to move that domain behavior to the methods of the domain objects (the aggregate root and child entity).</span></span>

<span data-ttu-id="d49bc-236">Der folgende Code zeigt als ein Beispiel einer Command-Handler-Klasse die gleiche CreateOrderCommandHandler-Klasse, die Sie gesehen haben, am Anfang dieses Kapitels.</span><span class="sxs-lookup"><span data-stu-id="d49bc-236">As an example of a command handler class, the following code shows the same CreateOrderCommandHandler class that you saw at the beginning of this chapter.</span></span> <span data-ttu-id="d49bc-237">In diesem Fall haben wir die Handle-Methode und die Vorgänge mit der Domäne Modell Objekte/Aggregaten hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="d49bc-237">In this case we have highlighted the Handle method and the operations with the domain model objects/aggregates.</span></span>

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IBuyerRepository _buyerRepository;
    private readonly IOrderRepository _orderRepository;

    public CreateOrderCommandHandler(IBuyerRepository buyerRepository,
        IOrderRepository orderRepository)
    {
        if (buyerRepository == null)
        {
            throw new ArgumentNullException(nameof(buyerRepository));
        }
        if (orderRepository == null)
        {
            throw new ArgumentNullException(nameof(orderRepository));
        }

        _buyerRepository = buyerRepository;
        _orderRepository = orderRepository;
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        //
        // Additional code ...
        //
        // Create the Order aggregate root
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var order = new Order(buyer.Id, payment.Id,
            new Address(message.Street,
            message.City, message.State,
            message.Country, message.ZipCode));

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                item.Discount, item.PictureUrl, item.Units);
        }

        // Persist the Order through the aggregate's repository
        _orderRepository.Add(order);
        return await _orderRepository.UnitOfWork.SaveChangesAsync();
    }
}
```

<span data-ttu-id="d49bc-238">Hierbei handelt es sich um zusätzliche Befehlshandler auszuführenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="d49bc-238">These are additional steps a command handler should take:</span></span>

-   <span data-ttu-id="d49bc-239">Verwenden Sie den Befehl Daten, mit des aggregierten Stamms Methoden und Verhalten verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d49bc-239">Use the command’s data to operate with the aggregate root’s methods and behavior.</span></span>

-   <span data-ttu-id="d49bc-240">Lösen Sie intern innerhalb der Domänenobjekte Domäne Ereignisse aus, während die Transaktion wird ausgeführt, sondern transparent aus einem Befehl Handler der Sicht.</span><span class="sxs-lookup"><span data-stu-id="d49bc-240">Internally within the domain objects, raise domain events while the transaction is executed, but that is transparent from a command handler point of view.</span></span>

-   <span data-ttu-id="d49bc-241">Lösen Sie Wenn das Aggregat Ergebnis des Vorgangs erfolgreich ist, und nachdem die Transaktion abgeschlossen ist aus, Integration Ereignisse Befehlshandler.</span><span class="sxs-lookup"><span data-stu-id="d49bc-241">If the aggregate’s operation result is successful and after the transaction is finished, raise integration events command handler.</span></span> <span data-ttu-id="d49bc-242">(Dies können auch von Infrastrukturklassen wie Repositorys ausgelöst werden.)</span><span class="sxs-lookup"><span data-stu-id="d49bc-242">(These might also be raised by infrastructure classes like repositories.)</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="d49bc-243">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d49bc-243">Additional resources</span></span>

-   <span data-ttu-id="d49bc-244">**Mark Seemann. Die Grenzen sind nicht mit dem objektorientierten**
    [*http://blog.ploeh.dk/2011/05/31/AttheBoundaries, ApplicationsareNotObject-orientierten /*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)</span><span class="sxs-lookup"><span data-stu-id="d49bc-244">**Mark Seemann. At the Boundaries, Applications are Not Object-Oriented**
[*http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)</span></span>

-   <span data-ttu-id="d49bc-245">**Befehle und Ereignisse**
    [*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)</span><span class="sxs-lookup"><span data-stu-id="d49bc-245">**Commands and events**
[*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)</span></span>

-   <span data-ttu-id="d49bc-246">**Wie funktioniert die Befehlshandler? ** 
     [ *http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)</span><span class="sxs-lookup"><span data-stu-id="d49bc-246">**What does a command handler do?**
[*http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)</span></span>

-   <span data-ttu-id="d49bc-247">**Jimmy Bogard. Muster für den Befehl Domäne – Handler**
    [*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)</span><span class="sxs-lookup"><span data-stu-id="d49bc-247">**Jimmy Bogard. Domain Command Patterns – Handlers**
[*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)</span></span>

-   <span data-ttu-id="d49bc-248">**Jimmy Bogard. Muster für den Befehl Domäne – Überprüfung**
    [*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)</span><span class="sxs-lookup"><span data-stu-id="d49bc-248">**Jimmy Bogard. Domain Command Patterns – Validation**
[*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)</span></span>

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a><span data-ttu-id="d49bc-249">Der Befehl Prozesspipeline: Befehlshandler auslösen</span><span class="sxs-lookup"><span data-stu-id="d49bc-249">The Command process pipeline: how to trigger a command handler</span></span>

<span data-ttu-id="d49bc-250">Die nächste Frage ist, wie Befehlshandler aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d49bc-250">The next question is how to invoke a command handler.</span></span> <span data-ttu-id="d49bc-251">Sie können manuell aus jedem zugehörigen ASP.NET Core Controller aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-251">You could manually call it from each related ASP.NET Core controller.</span></span> <span data-ttu-id="d49bc-252">Ansatz zu wäre allerdings gekoppelt und ist nicht ideal.</span><span class="sxs-lookup"><span data-stu-id="d49bc-252">However, that approach would be too coupled and is not ideal.</span></span>

<span data-ttu-id="d49bc-253">Die anderen zwei Hauptoptionen, die die empfohlenen Optionen sind, sind:</span><span class="sxs-lookup"><span data-stu-id="d49bc-253">The other two main options, which are the recommended options, are:</span></span>

-   <span data-ttu-id="d49bc-254">Über ein Element der in-Memory-Vermittler-Muster.</span><span class="sxs-lookup"><span data-stu-id="d49bc-254">Through an in-memory Mediator pattern artifact.</span></span>

-   <span data-ttu-id="d49bc-255">Mit einer asynchronen Nachrichtenwarteschlange zwischen Domänencontrollern und Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="d49bc-255">With an asynchronous message queue, in between controllers and handlers.</span></span>

### <a name="using-the-mediator-pattern-in-memory-in-the-command-pipeline"></a><span data-ttu-id="d49bc-256">Mithilfe der Vermittler-Musters (in-Memory) in der Befehlspipeline</span><span class="sxs-lookup"><span data-stu-id="d49bc-256">Using the Mediator pattern (in-memory) in the command pipeline</span></span>

<span data-ttu-id="d49bc-257">Wie in Abbildung 9-21 dargestellt, verwenden Sie in einem CQRS Ansatz eine intelligente Vermittler, ähnlich einem in-Memory-Bus, also intelligent genug, um die Umleitung an den richtigen Befehlshandler basierend auf dem Typ des Befehls oder des DTO empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-257">As shown in Figure 9-21, in a CQRS approach you use an intelligent mediator, similar to an in-memory bus, which is smart enough to redirect to the right command handler based on the type of the command or DTO being received.</span></span> <span data-ttu-id="d49bc-258">Die einzelnen schwarzen Pfeile zwischen Komponenten stellen die Abhängigkeiten zwischen Objekten (in vielen Fällen eingefügten mit DI) mit der zugehörigen Interaktionen dar.</span><span class="sxs-lookup"><span data-stu-id="d49bc-258">The single black arrows between components represent the dependencies between objects (in many cases, injected through DI) with their related interactions.</span></span>

![](./media/image22.png)

<span data-ttu-id="d49bc-259">**Abbildung 9 – 21**.</span><span class="sxs-lookup"><span data-stu-id="d49bc-259">**Figure 9-21**.</span></span> <span data-ttu-id="d49bc-260">Mithilfe der Vermittler Muster im Prozess in einem einzelnen CQRS microservice</span><span class="sxs-lookup"><span data-stu-id="d49bc-260">Using the Mediator pattern in process in a single CQRS microservice</span></span>

<span data-ttu-id="d49bc-261">Der Grund, der unter Verwendung des Musters Vermittler sinnvoll ist, dass in Enterprise-Anwendungen, die verarbeitungsanforderungen komplizierte abrufen können.</span><span class="sxs-lookup"><span data-stu-id="d49bc-261">The reason that using the Mediator pattern makes sense is that in enterprise applications, the processing requests can get complicated.</span></span> <span data-ttu-id="d49bc-262">Sie möchten eine geöffnete Anzahl von querschnittliche Anliegen wie Protokollierung, Überprüfungen, Überwachung und Sicherheit hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="d49bc-262">You want to be able to add an open number of cross-cutting concerns like logging, validations, audit, and security.</span></span> <span data-ttu-id="d49bc-263">In diesen Fällen können Sie auf eine Pipeline Vermittler basieren (finden Sie unter [Vermittler Muster](https://en.wikipedia.org/wiki/Mediator_pattern)) systemverarbeitungsaufwand für diese zusätzliche Verhaltensweisen oder querschnittliche Bedenken.</span><span class="sxs-lookup"><span data-stu-id="d49bc-263">In these cases, you can rely on a mediator pipeline (see [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern)) to provide a means for these extra behaviors or cross-cutting concerns.</span></span>

<span data-ttu-id="d49bc-264">Ein Vermittler ist ein Objekt, das "wie" dieses Prozesses kapselt: koordiniert die Ausführung basierend auf Status, wie Befehlshandler aufgerufen wird oder der Nutzlast, die Sie an den Handler bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-264">A mediator is an object that encapsulates the “how” of this process: it coordinates execution based on state, the way a command handler is invoked, or the payload you provide to the handler.</span></span> <span data-ttu-id="d49bc-265">Mit einer Komponente Vermittler können Sie querschnittliche Bedenken in einer zentralen und transparente Weise anwenden, durch Anwenden von Decorator-Elementen (oder [pipeline Verhalten](https://github.com/jbogard/MediatR/wiki/Behaviors) seit Vermittler v3).</span><span class="sxs-lookup"><span data-stu-id="d49bc-265">With a mediator component you can apply cross-cutting concerns in a centralized and transparent way by applying decorators (or [pipeline behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) since Mediator v3).</span></span> <span data-ttu-id="d49bc-266">(Weitere Informationen finden Sie unter der [Decorator-Muster](https://en.wikipedia.org/wiki/Decorator_pattern).)</span><span class="sxs-lookup"><span data-stu-id="d49bc-266">(For more information, see the [Decorator pattern](https://en.wikipedia.org/wiki/Decorator_pattern).)</span></span>

<span data-ttu-id="d49bc-267">Decorator-Elementen und Verhaltensweisen ähneln [Aspekt Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming)nur auf eine bestimmte Prozesspipeline verwaltet, die von der Komponente Vermittler angewendet.</span><span class="sxs-lookup"><span data-stu-id="d49bc-267">Decorators and behaviors are similar to [Aspect Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), only applied to a specific process pipeline managed by the mediator component.</span></span> <span data-ttu-id="d49bc-268">Aspekte im AOP, die querschnittliche Bedenken implementieren werden basierend auf angewendet *Aspekt Weavers* eingefügten zum Zeitpunkt der Kompilierung oder basierend auf Objekt Aufruf abfangen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-268">Aspects in AOP that implement cross-cutting concerns are applied based on *aspect weavers* injected at compilation time or based on object call interception.</span></span> <span data-ttu-id="d49bc-269">Beide Ansätze für typische AOP werden manchmal auch als "wie Magic," funktionieren, da er nicht schwer ist zu verstehen, wie AOP seine Arbeit ausführt.</span><span class="sxs-lookup"><span data-stu-id="d49bc-269">Both typical AOP approaches are sometimes said to work "like magic," because it is not easy to see how AOP does its work.</span></span> <span data-ttu-id="d49bc-270">Beim Umgang mit schwerwiegenden Problemen oder Fehlern kann AOP Debuggen schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="d49bc-270">When dealing with serious issues or bugs, AOP can be difficult to debug.</span></span> <span data-ttu-id="d49bc-271">Andererseits, sind diese Decorators/Verhaltensweisen explizite und nur im Rahmen der Vermittler angewendeten Debuggen wesentlich besser vorhersagbar und einfach.</span><span class="sxs-lookup"><span data-stu-id="d49bc-271">On the other hand, these decorators/behaviors are explicit and applied only in the context of the mediator, so debugging is much more predictable and easy.</span></span>

<span data-ttu-id="d49bc-272">Z. B. in der eShopOnContainers Microservice Sortierung, wir die beiden Beispiel Decorators implementiert eine [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) Klasse und ein [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) Klasse.</span><span class="sxs-lookup"><span data-stu-id="d49bc-272">For example, in the eShopOnContainers ordering microservice, we implemented two sample decorators, a [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) class and a [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) class.</span></span> <span data-ttu-id="d49bc-273">Die Decorator-Implementierung wird im nächsten Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="d49bc-273">The decorator’s implementation is explained in the next section.</span></span> <span data-ttu-id="d49bc-274">Beachten Sie, dass in einer zukünftigen Version eShopOnContainers zu migrieren [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) und ans [Verhalten](https://github.com/jbogard/MediatR/wiki/Behaviors) anstelle von Decorator-Elementen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-274">Note that in a future version, eShopOnContainers will migrate to [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) and move to [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) instead of using decorators.</span></span>

### <a name="using-message-queues-out-of-proc-in-the-commands-pipeline"></a><span data-ttu-id="d49bc-275">Mithilfe von Nachrichtenwarteschlangen (Out-of-Proc) in den Befehl pipeline</span><span class="sxs-lookup"><span data-stu-id="d49bc-275">Using message queues (out-of-proc) in the command’s pipeline</span></span>

<span data-ttu-id="d49bc-276">Eine andere ist die Verwendung von asynchroner Nachrichten basierend auf Brokern oder Meldungswarteschlangen, wie in Abbildung 9 – 22 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d49bc-276">Another choice is to use asynchronous messages based on brokers or message queues, as shown in Figure 9-22.</span></span> <span data-ttu-id="d49bc-277">Diese Option kann auch mit der Vermittler Komponente direkt vor dem Befehlshandler kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-277">That option could also be combined with the mediator component right before the command handler.</span></span>

![](./media/image23.png)

<span data-ttu-id="d49bc-278">**Abbildung 9 – 22**.</span><span class="sxs-lookup"><span data-stu-id="d49bc-278">**Figure 9-22**.</span></span> <span data-ttu-id="d49bc-279">Mithilfe von Nachrichtenwarteschlangen (außerhalb des Prozesses und Kommunikation zwischen Prozessen) mit CQRS-Befehlen</span><span class="sxs-lookup"><span data-stu-id="d49bc-279">Using message queues (out of process and inter-process communication) with CQRS commands</span></span>

<span data-ttu-id="d49bc-280">Mit Nachrichtentext zustimmen, werden weitere Befehle können mithilfe von Warteschlangen des Befehls Pipeline erschweren, da benötigen Sie wahrscheinlich die Pipeline in zwei Prozesse unterteilt, die über externe Nachrichtenwarteschlange verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="d49bc-280">Using message queues to accept the commands can further complicate your command’s pipeline, because you will probably need to split the pipeline into two processes connected through the external message queue.</span></span> <span data-ttu-id="d49bc-281">Es sollte dennoch verwendet werden, wenn müssen Sie die Skalierbarkeit und Leistung basierend auf asynchrones messaging verbessert werden können.</span><span class="sxs-lookup"><span data-stu-id="d49bc-281">Still, it should be used if you need to have improved scalability and performance based on asynchronous messaging.</span></span> <span data-ttu-id="d49bc-282">Beachten Sie, dass im Fall von Abbildung 9 – 22, der Controller nur sendet der befehlsmeldung in die Warteschlange zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d49bc-282">Consider that in the case of Figure 9-22, the controller just posts the command message into the queue and returns.</span></span> <span data-ttu-id="d49bc-283">Die Nachrichten in ihrem eigenen Tempo wird anschließend der Befehlshandler verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d49bc-283">Then the command handlers process the messages at their own pace.</span></span> <span data-ttu-id="d49bc-284">D. h. ein großer Vorteil von Warteschlangen – die Nachrichtenwarteschlange kann zu fungieren als Puffer in Fällen, wenn hyper Skalierbarkeit erforderlich, z. B. durch Aktien oder allen anderen Szenarien, die mit einer großen Datenmenge eingehend ist.</span><span class="sxs-lookup"><span data-stu-id="d49bc-284">That is a great benefit of queues—the message queue can act as a buffer in cases when hyper scalability is needed, such as for stocks or any other scenario with a high volume of ingress data.</span></span>

<span data-ttu-id="d49bc-285">Allerdings müssen aufgrund der asynchronen Natur von Nachrichtenwarteschlangen, herauszufinden, wie für die Kommunikation mit der Clientanwendung über den Erfolg oder Misserfolg des Prozesses für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d49bc-285">However, because of the asynchronous nature of message queues, you need to figure out how to communicate with the client application about the success or failure of the command’s process.</span></span> <span data-ttu-id="d49bc-286">In der Regel sollten Sie nie "fire and forget"-Befehle verwenden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-286">As a rule, you should never use “fire and forget” commands.</span></span> <span data-ttu-id="d49bc-287">Jede Business-Anwendung muss wissen, ob ein Befehl erfolgreich verarbeitet, oder mindestens überprüft und akzeptiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d49bc-287">Every business application needs to know if a command was processed successfully, or at least validated and accepted.</span></span>

<span data-ttu-id="d49bc-288">Daher die Komplexität wird an den Client nach dem Validieren einer Befehlsnachricht, die an eine asynchrone Warteschlange übermittelt wurde reagieren Ihres Systems im Vergleich zu einem in-Process-Befehl-Prozess, der Ergebnis des Vorgangs gibt zurück, nachdem die Transaktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="d49bc-288">Thus, being able to respond to the client after validating a command message that was submitted to an asynchronous queue adds complexity to your system, as compared to an in-process command process that returns the operation’s result after running the transaction.</span></span> <span data-ttu-id="d49bc-289">Verwendung von Warteschlangen, müssen Sie das Ergebnis des Befehls Prozesses über anderen vorgangsmeldungen Ergebnis zurückzugeben, die zusätzliche Komponenten und benutzerdefinierte Kommunikation in Ihrem System benötigen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-289">Using queues, you might need to return the result of the command process through other operation result messages, which will require additional components and custom communication in your system.</span></span>

<span data-ttu-id="d49bc-290">Darüber hinaus sind asynchrone Befehle unidirektionale Befehle, die in vielen Fällen jedoch nicht benötigt werden möglicherweise wie im folgenden interessante Austausches zwischen Burtsev Alexey und Greg Young in erläutert wird, ein [online Konversation](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span><span class="sxs-lookup"><span data-stu-id="d49bc-290">Additionally, async commands are one-way commands, which in many cases might not be needed, as is explained in the following interesting exchange between Burtsev Alexey and Greg Young in an [online conversation](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span></span>

<span data-ttu-id="d49bc-291">\[Burtsev Alexey\] : viel Code suchen, wo Personen Async befehlsverarbeitung oder unidirektionale Befehl messaging ohne aus irgendeinem Grund dazu verwenden (sie sind nicht ausführen eines langen Vorgangs, sie externe asynchronem Code nicht ausgeführt werden, diese Anwendung nicht selbst durchgestrichen die Grenze Nachrichtenbus verwenden werden).</span><span class="sxs-lookup"><span data-stu-id="d49bc-291">\[Burtsev Alexey\] I find lots of code where people use async command handling or one way command messaging without any reason to do so (they are not doing some long operation, they are not executing external async code, they do not even cross application boundary to be using message bus).</span></span> <span data-ttu-id="d49bc-292">Warum führen sie diese unnötige Komplexität?</span><span class="sxs-lookup"><span data-stu-id="d49bc-292">Why do they introduce this unnecessary complexity?</span></span> <span data-ttu-id="d49bc-293">Und ich noch nicht tatsächlich ein Codebeispiel CQRS mit Befehlshandler bisher blockiert gefunden, obwohl in den meisten Fällen gut geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="d49bc-293">And actually, I haven't seen a CQRS code example with blocking command handlers so far, though it will work just fine in most cases.</span></span>

<span data-ttu-id="d49bc-294">\[Greg Young\] \[... \] ein asynchrones Befehls ist nicht vorhanden; es ist tatsächlich ein anderes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="d49bc-294">\[Greg Young\] \[...\] an asynchronous command doesn't exist; it's actually another event.</span></span> <span data-ttu-id="d49bc-295">Wenn ich muss übernehmen, was mich senden und ein Ereignis wird ausgelöst, wenn ich stimme nicht zu, ist es nicht mehr Sie darüber informiert, dass ich etwas tun.</span><span class="sxs-lookup"><span data-stu-id="d49bc-295">If I must accept what you send me and raise an event if I disagree, it's no longer you telling me to do something.</span></span> <span data-ttu-id="d49bc-296">Es ist Sie darüber informiert mich, etwas vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="d49bc-296">It's you telling me something has been done.</span></span> <span data-ttu-id="d49bc-297">Dies scheint zunächst einen geringfügigen Unterschied, verfügt aber über viele Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-297">This seems like a slight difference at first, but it has many implications.</span></span>

<span data-ttu-id="d49bc-298">Asynchrone Befehle erhöhen die Komplexität eines Systems zu erheblich, da es keine einfache Möglichkeit ist, Fehler hinweisen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-298">Asynchronous commands greatly increase the complexity of a system, because there is no simple way to indicate failures.</span></span> <span data-ttu-id="d49bc-299">Daher sind asynchrone Befehle nicht außer empfohlen, wenn skalierungsanforderungen benötigt werden oder in besonderen Fällen bei der Kommunikation von den internen Microservices über messaging.</span><span class="sxs-lookup"><span data-stu-id="d49bc-299">Therefore, asynchronous commands are not recommended other than when scaling requirements are needed or in special cases when communicating the internal microservices through messaging.</span></span> <span data-ttu-id="d49bc-300">In diesen Fällen müssen Sie ein eigenes reporting und Recovery System zum Fehler entwerfen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-300">In those cases, you must design a separate reporting and recovery system for failures.</span></span>

<span data-ttu-id="d49bc-301">In der ursprünglichen Version von eShopOnContainers entschieden wir synchrone Verarbeitung von HTTP-Anforderungen gestartet und anhand des Musters Vermittler driven verwenden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-301">In the initial version of eShopOnContainers, we decided to use synchronous command processing, started from HTTP requests and driven by the Mediator pattern.</span></span> <span data-ttu-id="d49bc-302">Die leicht ermöglicht den Erfolg oder Misserfolg des Prozesses, wie in der [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) Implementierung.</span><span class="sxs-lookup"><span data-stu-id="d49bc-302">That easily allows you to return the success or failure of the process, as in the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) implementation.</span></span>

<span data-ttu-id="d49bc-303">In jedem Fall sollte dies eine Entscheidung auf Basis Ihrer Anwendung oder des Microservice geschäftlichen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-303">In any case, this should be a decision based on your application’s or microservice’s business requirements.</span></span>

## <a name="implementing-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a><span data-ttu-id="d49bc-304">Implementieren der Prozesspipeline Befehl mit einem Vermittler-Muster (MediatR)</span><span class="sxs-lookup"><span data-stu-id="d49bc-304">Implementing the command process pipeline with a mediator pattern (MediatR)</span></span>

<span data-ttu-id="d49bc-305">Als eine beispielimplementierung dieses Handbuchs mit in-Process-Pipeline, basierend auf den Vermittler Muster, mit dem Befehl "Erfassung" Laufwerk und routing, im Arbeitsspeicher, an die richtige-Befehlshandler vorgeschlagen werden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-305">As a sample implementation, this guide proposes using the in-process pipeline based on the Mediator pattern to drive command ingestion and routing them, in memory, to the right command handlers.</span></span> <span data-ttu-id="d49bc-306">Das Handbuch auch vorgeschlagen Decorator-Elemente anwenden oder [Verhalten](https://github.com/jbogard/MediatR/wiki/Behaviors) um querschnittliche Aspekte zu trennen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-306">The guide also proposes applying decorators or [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) in order to separate cross-cutting concerns.</span></span>

<span data-ttu-id="d49bc-307">Bei Implementierung in .NET Core sind mehrere Open-Source-Bibliotheken verfügbar sind, die Vermittler-Muster implementieren.</span><span class="sxs-lookup"><span data-stu-id="d49bc-307">For implementation in .NET Core, there are multiple open-source libraries available that implement the Mediator pattern.</span></span> <span data-ttu-id="d49bc-308">Die Bibliothek, die in diesem Handbuch verwendeten ist die [MediatR](https://github.com/jbogard/MediatR) Open Source-Bibliothek (Jimmy Bogard erstellt), aber Sie können einen anderen Ansatz verwenden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-308">The library used in this guide is the [MediatR](https://github.com/jbogard/MediatR) open-source library (created by Jimmy Bogard), but you could use another approach.</span></span> <span data-ttu-id="d49bc-309">MediatR ist eine kleine und einfache-Bibliothek, die Ihnen ermöglicht, die in-Memory-Nachrichten, z. B. einen Befehl zu verarbeiten, beim Anwenden der Decorators oder Verhalten.</span><span class="sxs-lookup"><span data-stu-id="d49bc-309">MediatR is a small and simple library that allows you to process in-memory messages like a command, while applying decorators or behaviors.</span></span>

<span data-ttu-id="d49bc-310">Mithilfe des Musters Vermittler zeigt Ihnen, verbundener Einzelsysteme zu verringern und isolieren die Probleme beim Herstellen der Verbindung automatisch an den Handler, der diese Aufgabe führt die erforderlichen Aufgaben – in diesem Fall um Befehlshandler.</span><span class="sxs-lookup"><span data-stu-id="d49bc-310">Using the Mediator pattern helps you to reduce coupling and to isolate the concerns of the requested work, while automatically connecting to the handler that performs that work—in this case, to command handlers.</span></span>

<span data-ttu-id="d49bc-311">Ein weiterer guter Grund das Muster der Vermittler verwendet wurde beim Überprüfen von diesem Handbuch Jimmy Bogard behandelt:</span><span class="sxs-lookup"><span data-stu-id="d49bc-311">Another good reason to use the Mediator pattern was explained by Jimmy Bogard when reviewing this guide:</span></span>

<span data-ttu-id="d49bc-312">Ich denke Objektzuständen Testen hier ist es möglicherweise – es stellt ein nützliches konsistent Fenster, in das Verhalten Ihres Systems.</span><span class="sxs-lookup"><span data-stu-id="d49bc-312">I think it might be worth mentioning testing here – it provides a nice consistent window into the behavior of your system.</span></span> <span data-ttu-id="d49bc-313">Anforderung, Antwort Out. Wir haben diesen Aspekt überzeugendes im Gebäude konsistent verhält Tests gefunden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-313">Request-in, response-out. We’ve found that aspect quite valuable in building consistently behaving tests.</span></span>

<span data-ttu-id="d49bc-314">Zunächst lassen Sie uns sehen Sie an den controllercode, in denen würden Sie tatsächlich den Vermittler-Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="d49bc-314">First, let us take a look to the controller code where you actually would use the mediator object.</span></span> <span data-ttu-id="d49bc-315">Wenn Sie jedoch stattdessen das Vermittler nicht verwenden, müssen Sie alle Abhängigkeiten für diesen Controller, z. B. ein Protokollierungsobjekt und andere einfügen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-315">If you were not using the mediator object, you would need to inject all the dependencies for that controller, things like a logger object and others.</span></span> <span data-ttu-id="d49bc-316">Daher würde der Konstruktor ziemlich kompliziert sein.</span><span class="sxs-lookup"><span data-stu-id="d49bc-316">Therefore, the constructor would be quite complicated.</span></span> <span data-ttu-id="d49bc-317">Andererseits, wenn Sie jedoch stattdessen das Vermittler verwenden, der Konstruktor der Domänencontroller viel einfacher, mit wenigen Abhängigkeiten anstatt viele Abhängigkeiten ist möglich, die eine pro querschnittliche-Vorgang, wie im folgenden Beispiel wäre:</span><span class="sxs-lookup"><span data-stu-id="d49bc-317">On the other hand, if you use the mediator object, the constructor of your controller can be a lot simpler, with just a few dependencies instead of many dependencies that you would have if you had one per cross-cutting operation, as in the following example:</span></span>

```csharp
public class OrdersController : Controller
{
    public OrdersController(IMediator mediator,
        IOrderQueries orderQueries)
    // ...
```

<span data-ttu-id="d49bc-318">Sie können sehen, dass der Vermittler einen sauberen und lean Web-API-Controller-Konstruktor zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d49bc-318">You can see that the mediator provides a clean and lean Web API controller constructor.</span></span> <span data-ttu-id="d49bc-319">Darüber hinaus wird der Code zum Senden eines Befehls auf den Vermittler-Objekt innerhalb der Controllermethoden fast nur eine Zeile:</span><span class="sxs-lookup"><span data-stu-id="d49bc-319">In addition, within the controller methods, the code to send a command to the mediator object is almost one line:</span></span>

```csharp
[Route("new")]
[HttpPost]
public async Task<IActionResult> CreateOrder([FromBody]CreateOrderCommand
    createOrderCommand)
{
    var commandResult = await _mediator.SendAsync(createOrderCommand);
    return commandResult ? (IActionResult)Ok() : (IActionResult)BadRequest();
}
```

<span data-ttu-id="d49bc-320">In der Reihenfolge für MediatR zu Ihrem Ereignishandler Befehlsklassen berücksichtigen müssen Sie die Vermittler und der Befehl Handler-Klassen im IoC-Container zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="d49bc-320">In order for MediatR to be aware of your command handler classes, you need to register the mediator classes and the command handler classes in your IoC container.</span></span> <span data-ttu-id="d49bc-321">Standardmäßig MediatR Autofac als IoC-Container verwendet, aber Sie können auch die integrierte ASP.NET Core IoC-Container oder andere Container, die von MediatR unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d49bc-321">By default, MediatR uses Autofac as the IoC container, but you can also use the built-in ASP.NET Core IoC container or any other container supported by MediatR.</span></span>

<span data-ttu-id="d49bc-322">Der folgende Code zeigt, wie bei Autofac Module mithilfe der Vermittler Typen und Befehle zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="d49bc-322">The following code shows how to register Mediator’s types and commands when using Autofac modules.</span></span>

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();
        builder.RegisterAssemblyTypes(typeof(CreateOrderCommand)
            .GetTypeInfo().Assembly)
            .As(o => o.GetInterfaces()
            .Where(i => i.IsClosedTypeOf(typeof(IAsyncRequestHandler<,>)))
            .Select(i => new KeyedService("IAsyncRequestHandler", i)));
        builder.RegisterGenericDecorator(typeof(LogDecorator<,>),
            typeof(IAsyncRequestHandler<,>), "IAsyncRequestHandler");

        // Other types registration
    }
}
```

<span data-ttu-id="d49bc-323">Da jede Befehlshandler der Schnittstelle mit generischen IAsyncRequestHandler implementiert&lt;T&gt; und überprüft dann die RegisteredAssemblyTypes Objekt ist, wird der Handler ist in der Lage, jeden Befehl mit der Befehlshandler beziehen, da, Beziehung angegeben ist in der CommandHandler-Klasse, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d49bc-323">Because each command handler implements the interface with generic IAsyncRequestHandler&lt;T&gt; and then inspects the RegisteredAssemblyTypes object, the handler is able to relate each command with its command handler, because that relationship is stated in the CommandHandler class, as in the following example:</span></span>

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

<span data-ttu-id="d49bc-324">Dies ist der Code, der Befehle mit Befehlshandler korreliert.</span><span class="sxs-lookup"><span data-stu-id="d49bc-324">This is the code that correlates commands with command handlers.</span></span> <span data-ttu-id="d49bc-325">Der Handler nur eine einfache Klasse vorhanden ist, aber es erbt von RequestHandler&lt;T&gt;, und MediatR wird sichergestellt, er ruft mit dem richtigen Nutzlast aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-325">The handler is just a simple class, but it inherits from RequestHandler&lt;T&gt;, and MediatR makes sure it gets invoked with the correct payload.</span></span>

## <a name="applying-cross-cutting-concerns-when-processing-commands-with-the-mediator-and-decorator-patterns"></a><span data-ttu-id="d49bc-326">Anwenden von querschnittliche Aspekte bei der Verarbeitung von Befehlen mit den Vermittler und Decorator-Mustern</span><span class="sxs-lookup"><span data-stu-id="d49bc-326">Applying cross-cutting concerns when processing commands with the Mediator and Decorator patterns</span></span>

<span data-ttu-id="d49bc-327">Es gibt noch etwas: querschnittliche Bedenken hinsichtlich der Vermittler Pipeline anwenden wird.</span><span class="sxs-lookup"><span data-stu-id="d49bc-327">There is one more thing: being able to apply cross-cutting concerns to the mediator pipeline.</span></span> <span data-ttu-id="d49bc-328">Sie sehen auch am Ende der Autofac Registrierung Modulcode wie sie registriert wird, einen Decorator-Element eingeben, insbesondere eine benutzerdefinierte LogDecorator-Klasse.</span><span class="sxs-lookup"><span data-stu-id="d49bc-328">You can also see at the end of the Autofac registration module code how it is registering a decorator type, specifically, a custom LogDecorator class.</span></span>

<span data-ttu-id="d49bc-329">Erneut, beachten Sie, dass eine zukünftige Version von eShopOnContainers ihn zum Migrieren [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) und ans [Verhalten](https://github.com/jbogard/MediatR/wiki/Behaviors) anstelle von Decorator-Elementen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-329">Again, note that a future version of eShopOnContainers it will migrate to [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) and move to [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) instead of using decorators.</span></span>

<span data-ttu-id="d49bc-330">Dass [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) Klasse implementiert werden kann, wie der folgende Code, in dem Informationen zu ausgeführten Befehlshandler und gibt an, ob es erfolgreich war oder nicht protokolliert.</span><span class="sxs-lookup"><span data-stu-id="d49bc-330">That [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) class can be implemented as the following code, which logs information about the command handler being executed and whether it was successful or not.</span></span>

```csharp
public class LogDecorator<TRequest, TResponse>
    : IAsyncRequestHandler<TRequest, TResponse>
    where TRequest : IAsyncRequest<TResponse>
{
    private readonly IAsyncRequestHandler<TRequest, TResponse> _inner;
    private readonly ILogger<LogDecorator<TRequest, TResponse>> _logger;

    public LogDecorator(
        IAsyncRequestHandler<TRequest, TResponse> inner,
        ILogger<LogDecorator<TRequest, TResponse>> logger)
    {
        _inner = inner;
        _logger = logger;
    }

    public async Task<TResponse> Handle(TRequest message)
    {
        _logger.LogInformation($"Executing command {_inner.GetType().FullName}");
        var response = await _inner.Handle(message);
        _logger.LogInformation($"Succeeded executed command{_inner.GetType().FullName}");
        return response;
    }
}
```

<span data-ttu-id="d49bc-331">Durch Implementieren dieser Decorator-Klasse und durch das ergänzen der Pipeline mit werden alle Befehle, die über MediatR verarbeitet Informationen zur Ausführung Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="d49bc-331">Just by implementing this decorator class and by decorating the pipeline with it, all the commands processed through MediatR will be logging information about the execution.</span></span>

<span data-ttu-id="d49bc-332">Die Sortierung Microservice gilt auch für einen zweiten Decorator-Element für grundlegende Validierungen eShopOnContainers der [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) Klasse, die benötigt die [FluentValidation](https://github.com/JeremySkinner/FluentValidation) Bibliothek, entsprechend der folgender Code:</span><span class="sxs-lookup"><span data-stu-id="d49bc-332">The eShopOnContainers ordering microservice also applies a second decorator for basic validations, the [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) class that relies on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, as shown in the following code:</span></span>

```csharp
public class ValidatorDecorator<TRequest, TResponse>
    : IAsyncRequestHandler<TRequest, TResponse>
    where TRequest : IAsyncRequest<TResponse>
{
    private readonly IAsyncRequestHandler<TRequest, TResponse> _inner;
    private readonly IValidator<TRequest>[] _validators;

    public ValidatorDecorator(
        IAsyncRequestHandler<TRequest, TResponse> inner,
        IValidator<TRequest>[] validators)
    {
        _inner = inner;
        _validators = validators;
    }

    public async Task<TResponse> Handle(TRequest message)
    {
        var failures = _validators
            .Select(v => v.Validate(message))
            .SelectMany(result => result.Errors)
            .Where(error => error != null)
            .ToList();
            if (failures.Any())
            {
                throw new OrderingDomainException(
                $"Command Validation Errors for type {typeof(TRequest).Name}",
                new ValidationException("Validation exception", failures));
            }
            var response = await _inner.Handle(message);
        return response;
    }
}
```

<span data-ttu-id="d49bc-333">Klicken Sie dann auf der Grundlage der [FluentValidation](https://github.com/JeremySkinner/FluentValidation) -Bibliothek erstellten Validierung für die Daten mit CreateOrderCommand, übergeben wird, wie im folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="d49bc-333">Then, based on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, we created validation for the data passed with CreateOrderCommand, as in the following code:</span></span>

```csharp
public class CreateOrderCommandValidator : AbstractValidator<CreateOrderCommand>
{
    public CreateOrderCommandValidator()
    {
        RuleFor(command => command.City).NotEmpty();
        RuleFor(command => command.Street).NotEmpty();
        RuleFor(command => command.State).NotEmpty();
        RuleFor(command => command.Country).NotEmpty();
        RuleFor(command => command.ZipCode).NotEmpty();
        RuleFor(command => command.CardNumber).NotEmpty().Length(12, 19);
        RuleFor(command => command.CardHolderName).NotEmpty();
        RuleFor(command => command.CardExpiration).NotEmpty().Must(BeValidExpirationDate).
            WithMessage("Please specify a valid card expiration date");
        RuleFor(command => command.CardSecurityNumber).NotEmpty().Length(3);
        RuleFor(command => command.CardTypeId).NotEmpty();
        RuleFor(command => command.OrderItems).
            Must(ContainOrderItems).WithMessage("No order items found");
    }

    private bool BeValidExpirationDate(DateTime dateTime)
    {
        return dateTime >= DateTime.UtcNow;
    }

    private bool ContainOrderItems(IEnumerable<OrderItemDTO> orderItems)
    {
        return orderItems.Any();
    }
}
```

<span data-ttu-id="d49bc-334">Sie können zusätzliche Überprüfungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d49bc-334">You could create additional validations.</span></span> <span data-ttu-id="d49bc-335">Dies ist eine sehr sauber und elegante Möglichkeit, Ihre Überprüfungen Befehl zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="d49bc-335">This is a very clean and elegant way to implement your command validations.</span></span>

<span data-ttu-id="d49bc-336">Auf ähnliche Weise könnten Sie andere Decorators für zusätzliche Aspekte oder querschnittliche Aspekte, die Sie auf Befehle angewendet, wenn sie behandeln möchten, implementieren.</span><span class="sxs-lookup"><span data-stu-id="d49bc-336">In a similar way, you could implement other decorators for additional aspects or cross-cutting concerns that you want to apply to commands when handling them.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="d49bc-337">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d49bc-337">Additional resources</span></span>

##### <a name="the-mediator-pattern"></a><span data-ttu-id="d49bc-338">Das Muster Vermittler</span><span class="sxs-lookup"><span data-stu-id="d49bc-338">The mediator pattern</span></span>

-   <span data-ttu-id="d49bc-339">**Vermittler Muster**
    [*https://en.wikipedia.org/wiki/Mediator\_Muster*](https://en.wikipedia.org/wiki/Mediator_pattern)</span><span class="sxs-lookup"><span data-stu-id="d49bc-339">**Mediator pattern**
[*https://en.wikipedia.org/wiki/Mediator\_pattern*](https://en.wikipedia.org/wiki/Mediator_pattern)</span></span>

##### <a name="the-decorator-pattern"></a><span data-ttu-id="d49bc-340">Das Decorator-Muster</span><span class="sxs-lookup"><span data-stu-id="d49bc-340">The decorator pattern</span></span>

-   <span data-ttu-id="d49bc-341">**Decorator-Musters**
    [*https://en.wikipedia.org/wiki/Decorator\_Muster*](https://en.wikipedia.org/wiki/Decorator_pattern)</span><span class="sxs-lookup"><span data-stu-id="d49bc-341">**Decorator pattern**
[*https://en.wikipedia.org/wiki/Decorator\_pattern*](https://en.wikipedia.org/wiki/Decorator_pattern)</span></span>

##### <a name="mediatr-jimmy-bogard"></a><span data-ttu-id="d49bc-342">MediatR (Jimmy Bogard)</span><span class="sxs-lookup"><span data-stu-id="d49bc-342">MediatR (Jimmy Bogard)</span></span>

-   <span data-ttu-id="d49bc-343">**MediatR.**</span><span class="sxs-lookup"><span data-stu-id="d49bc-343">**MediatR.**</span></span> <span data-ttu-id="d49bc-344">GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="d49bc-344">GitHub repo.</span></span>
    [<span data-ttu-id="d49bc-345">*https://github.com/jbogard/MediatR*</span><span class="sxs-lookup"><span data-stu-id="d49bc-345">*https://github.com/jbogard/MediatR*</span></span>](https://github.com/jbogard/MediatR)

-   <span data-ttu-id="d49bc-346">**CQRS mit MediatR und AutoMapper**
    [*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)</span><span class="sxs-lookup"><span data-stu-id="d49bc-346">**CQRS with MediatR and AutoMapper**
[*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)</span></span>

-   <span data-ttu-id="d49bc-347">**Fügen Sie Ihre Domänencontroller in einer Ernährung: POSTs und Befehle. ** 
     [ *https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)</span><span class="sxs-lookup"><span data-stu-id="d49bc-347">**Put your controllers on a diet: POSTs and commands.**
[*https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)</span></span>

-   <span data-ttu-id="d49bc-348">**Bewältigt Fortschritts querschnittliche Aspekte, die eine Pipeline Vermittler**
    [*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)</span><span class="sxs-lookup"><span data-stu-id="d49bc-348">**Tackling cross-cutting concerns with a mediator pipeline**
[*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)</span></span>

-   <span data-ttu-id="d49bc-349">**CQRS und REST: perfekte Übereinstimmung**
    [*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)</span><span class="sxs-lookup"><span data-stu-id="d49bc-349">**CQRS and REST: the perfect match**
[*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)</span></span>

-   <span data-ttu-id="d49bc-350">**Beispiele für die Pipeline MediatR**
    [*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)</span><span class="sxs-lookup"><span data-stu-id="d49bc-350">**MediatR Pipeline Examples**
[*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)</span></span>

-   <span data-ttu-id="d49bc-351">**Vertikale Slice Testfixtures für MediatR und ASP.NET Core**
    *<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>*</span><span class="sxs-lookup"><span data-stu-id="d49bc-351">**Vertical Slice Test Fixtures for MediatR and ASP.NET Core**
*<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/> *</span></span>

-   <span data-ttu-id="d49bc-352">**MediatR-Erweiterungen für Microsoft Abhängigkeitsinjektion freigegeben**
    [*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)</span><span class="sxs-lookup"><span data-stu-id="d49bc-352">**MediatR Extensions for Microsoft Dependency Injection Released**
[*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)</span></span>

##### <a name="fluent-validation"></a><span data-ttu-id="d49bc-353">Fluent-Überprüfung</span><span class="sxs-lookup"><span data-stu-id="d49bc-353">Fluent validation</span></span>

-   <span data-ttu-id="d49bc-354">**Jeremy Skinner. FluentValidation.**</span><span class="sxs-lookup"><span data-stu-id="d49bc-354">**Jeremy Skinner. FluentValidation.**</span></span> <span data-ttu-id="d49bc-355">GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="d49bc-355">GitHub repo.</span></span>
    [<span data-ttu-id="d49bc-356">*https://github.com/JeremySkinner/FluentValidation*</span><span class="sxs-lookup"><span data-stu-id="d49bc-356">*https://github.com/JeremySkinner/FluentValidation*</span></span>](https://github.com/JeremySkinner/FluentValidation)

>[!div class="step-by-step"]
<span data-ttu-id="d49bc-357">[Vorherigen] (Microservice-application-layer-web-api-design.md) [weiter] (.. /Implement-Resilient-Applications/Index.MD)</span><span class="sxs-lookup"><span data-stu-id="d49bc-357">[Previous] (microservice-application-layer-web-api-design.md) [Next] (../implement-resilient-applications/index.md)</span></span>
