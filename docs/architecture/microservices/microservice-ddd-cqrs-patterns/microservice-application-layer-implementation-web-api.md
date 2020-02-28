---
title: Implementieren der Microservice-Anwendungsschicht mithilfe der Web-API
description: Übersicht über die Abhängigkeitsinjektion und Vermittlermuster und ihre Implementierung in der Web-API Anwendungsschicht.
ms.date: 01/30/2020
ms.openlocfilehash: a88f3bfd11ea06df085ca82ed7265cb37006fc31
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502445"
---
# <a name="implement-the-microservice-application-layer-using-the-web-api"></a><span data-ttu-id="b76eb-103">Implementieren der Microserviceanwendungsschicht mithilfe der Web-API</span><span class="sxs-lookup"><span data-stu-id="b76eb-103">Implement the microservice application layer using the Web API</span></span>

## <a name="use-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a><span data-ttu-id="b76eb-104">Einfügen von Infrastrukturobjekten in die Anwendungsschicht mithilfe der Abhängigkeitsinjektion</span><span class="sxs-lookup"><span data-stu-id="b76eb-104">Use Dependency Injection to inject infrastructure objects into your application layer</span></span>

<span data-ttu-id="b76eb-105">Wie bereits erwähnt, kann die Anwendungsschicht als Teil des Artefakts (der Assembly) implementiert werden, das Sie erstellen, etwa innerhalb eines Web-API-Projekts oder eines MVC-Web-App-Projekts.</span><span class="sxs-lookup"><span data-stu-id="b76eb-105">As mentioned previously, the application layer can be implemented as part of the artifact (assembly) you are building, such as within a Web API project or an MVC web app project.</span></span> <span data-ttu-id="b76eb-106">Im Falle eines mit ASP.NET Core erstellten Microservice ist die Anwendungsschicht in der Regel Ihre Web-API-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="b76eb-106">In the case of a microservice built with ASP.NET Core, the application layer will usually be your Web API library.</span></span> <span data-ttu-id="b76eb-107">Wenn Sie das, was von ASP.NET Core stammt (dessen Infrastruktur und Ihren Domänencontroller) von Ihrem benutzerdefinierten Anwendungsschichtcode trennen möchten, können Sie Ihre Anwendungsschicht auch in einer separaten Klassenbibliothek platzieren. Dies ist jedoch optional.</span><span class="sxs-lookup"><span data-stu-id="b76eb-107">If you want to separate what is coming from ASP.NET Core (its infrastructure plus your controllers) from your custom application layer code, you could also place your application layer in a separate class library, but that is optional.</span></span>

<span data-ttu-id="b76eb-108">Der Anwendungsschichtcode des Microservices für Bestellungen ist beispielsweise direkt als Teil des **Ordering.API**-Projekts (ein ASP.NET Core-Web-API-Projekt) implementiert (s. Abbildung 7-23).</span><span class="sxs-lookup"><span data-stu-id="b76eb-108">For instance, the application layer code of the ordering microservice is directly implemented as part of the **Ordering.API** project (an ASP.NET Core Web API project), as shown in Figure 7-23.</span></span>

:::image type="complex" source="./media/microservice-application-layer-implementation-web-api/ordering-api-microservice.png" alt-text="Screenshot des Microservice „Ordering.API“ im Projektmappen-Explorer.":::
<span data-ttu-id="b76eb-110">Der Projektmappen-Explorer des Microservice „Ordering.API“, der die Unterordner von „Anwendung“ anzeigt: Verhalten, Befehle, DomainEventHandlers, IntegrationEvents, Modelle, Abfragen und Prüfungen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-110">The Solution Explorer view of the Ordering.API microservice, showing the sub-folders under the Application folder: Behaviors, Commands, DomainEventHandlers, IntegrationEvents, Models, Queries and Validations.</span></span>
:::image-end:::

<span data-ttu-id="b76eb-111">**Abbildung 7-23**.</span><span class="sxs-lookup"><span data-stu-id="b76eb-111">**Figure 7-23**.</span></span> <span data-ttu-id="b76eb-112">Die Anwendungsschicht im Projekt Ordering.API-Projekt (ASP.NET Core-Web-API-Projekt)</span><span class="sxs-lookup"><span data-stu-id="b76eb-112">The application layer in the Ordering.API ASP.NET Core Web API project</span></span>

<span data-ttu-id="b76eb-113">ASP.NET Core enthält einen einfachen [integrierten Container](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (dargestellt durch die IServiceProvider-Schnittstelle), der die Constructor Injection standardmäßig unterstützt. Zudem stellt ASP.NET bestimmte Dienste über Dependency Injection zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b76eb-113">ASP.NET Core includes a simple [built-in IoC container](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (represented by the IServiceProvider interface) that supports constructor injection by default, and ASP.NET makes certain services available through DI.</span></span> <span data-ttu-id="b76eb-114">ASP.NET Core verwendet den Begriff *Dienst* für alle Typen, die Sie registrieren und die über DI eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-114">ASP.NET Core uses the term *service* for any of the types you register that will be injected through DI.</span></span> <span data-ttu-id="b76eb-115">Sie konfigurieren die integrierten Containerdienste in der ConfigureServices-Methode in der Startup-Klasse Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b76eb-115">You configure the built-in container's services in the ConfigureServices method in your application's Startup class.</span></span> <span data-ttu-id="b76eb-116">Ihre Abhängigkeiten werden in den Diensten implementiert, die ein Typ benötigt und die Sie im IoC-Container registrieren.</span><span class="sxs-lookup"><span data-stu-id="b76eb-116">Your dependencies are implemented in the services that a type needs and that you register in the IoC container.</span></span>

<span data-ttu-id="b76eb-117">In der Regel fügen Sie Abhängigkeiten ein, die Infrastrukturobjekte implementieren.</span><span class="sxs-lookup"><span data-stu-id="b76eb-117">Typically, you want to inject dependencies that implement infrastructure objects.</span></span> <span data-ttu-id="b76eb-118">Eine sehr typische einzufügende Abhängigkeit ist ein Repository.</span><span class="sxs-lookup"><span data-stu-id="b76eb-118">A very typical dependency to inject is a repository.</span></span> <span data-ttu-id="b76eb-119">Sie können jedoch auch jede andere Infrastrukturabhängigkeit einfügen, die verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b76eb-119">But you could inject any other infrastructure dependency that you may have.</span></span> <span data-ttu-id="b76eb-120">Für einfachere Implementierungen können Sie Ihr Arbeitseinheitsmuster-Objekt (EF DbContext-Objekt) direkt einfügen, da der DBContext auch die Implementierung Ihrer Infrastrukturpersistenzobjekte ist.</span><span class="sxs-lookup"><span data-stu-id="b76eb-120">For simpler implementations, you could directly inject your Unit of Work pattern object (the EF DbContext object), because the DBContext is also the implementation of your infrastructure persistence objects.</span></span>

<span data-ttu-id="b76eb-121">Im folgenden Beispiel sehen Sie, wie .NET Core die erforderlichen Repositoryobjekte über den Konstruktor einfügt.</span><span class="sxs-lookup"><span data-stu-id="b76eb-121">In the following example, you can see how .NET Core is injecting the required repository objects through the constructor.</span></span> <span data-ttu-id="b76eb-122">Die Klasse ist ein Befehlshandler, der im nächsten Abschnitt beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="b76eb-122">The class is a command handler, which we will cover in the next section.</span></span>

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
                                     IOrderRepository orderRepository,
                                     IIdentityService identityService)
    {
        _orderRepository = orderRepository ??
                          throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ??
                          throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ??
                                 throw new ArgumentNullException(nameof(mediator));
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State,
                                  message.Country, message.ZipCode);
        var order = new Order(message.UserId, address, message.CardTypeId,
                              message.CardNumber, message.CardSecurityNumber,
                              message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                               item.Discount, item.PictureUrl, item.Units);
        }

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
    }
}
```

<span data-ttu-id="b76eb-123">Die Klasse verwendet die eingefügten Repositorys zum Ausführen der Transaktion und Beibehalten der Zustandsänderungen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-123">The class uses the injected repositories to execute the transaction and persist the state changes.</span></span> <span data-ttu-id="b76eb-124">Es spielt keine Rolle, ob diese Klasse ein Befehlshandler, eine Web-API-Controller-Methode von ASP.NET Core oder ein [DDD-Anwendungsdienst](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/) ist.</span><span class="sxs-lookup"><span data-stu-id="b76eb-124">It does not matter whether that class is a command handler, an ASP.NET Core Web API controller method, or a [DDD Application Service](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span></span> <span data-ttu-id="b76eb-125">Letztlich handelt es sich um eine einfache Klasse, die Repositorys, Domänenentitäten und die sonstige Anwendungskoordinierung auf eine mit einem Befehlshandler vergleichbare Art und Weise verwendet.</span><span class="sxs-lookup"><span data-stu-id="b76eb-125">It is ultimately a simple class that uses repositories, domain entities, and other application coordination in a fashion similar to a command handler.</span></span> <span data-ttu-id="b76eb-126">Die Dependency Injection funktioniert auf die gleiche Weise für alle erwähnten Klassen, wie etwa im Beispiel, in dem die DI basierend auf dem Konstruktor verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b76eb-126">Dependency Injection works the same way for all the mentioned classes, as in the example using DI based on the constructor.</span></span>

### <a name="register-the-dependency-implementation-types-and-interfaces-or-abstractions"></a><span data-ttu-id="b76eb-127">Registrieren von Abhängigkeitsimplementierungstypen und Schnittstellen oder Abstraktionen</span><span class="sxs-lookup"><span data-stu-id="b76eb-127">Register the dependency implementation types and interfaces or abstractions</span></span>

<span data-ttu-id="b76eb-128">Bevor Sie die Objekte verwenden, die über Konstruktoren eingefügt werden, müssen Sie wissen, wo Sie die Schnittstellen und Klassen registrieren, die die über die DI in Ihre Anwendungsklassen eingefügten Objekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-128">Before you use the objects injected through constructors, you need to know where to register the interfaces and classes that produce the objects injected into your application classes through DI.</span></span> <span data-ttu-id="b76eb-129">(Wie DI basierend auf den Konstruktor, wie weiter oben dargestellt.)</span><span class="sxs-lookup"><span data-stu-id="b76eb-129">(Like DI based on the constructor, as shown previously.)</span></span>

#### <a name="use-the-built-in-ioc-container-provided-by-aspnet-core"></a><span data-ttu-id="b76eb-130">Verwenden des integrierten und von ASP.NET Core bereitgestellten IoC-Containers</span><span class="sxs-lookup"><span data-stu-id="b76eb-130">Use the built-in IoC container provided by ASP.NET Core</span></span>

<span data-ttu-id="b76eb-131">Bei Verwendung des integrierten IoC-Containers, der von ASP.NET Core bereitgestellt wird, registrieren Sie die Typen, die Sie in die ConfigureServices-Methode in der Datei Startup.cs wie im folgenden Code einfügen möchten:</span><span class="sxs-lookup"><span data-stu-id="b76eb-131">When you use the built-in IoC container provided by ASP.NET Core, you register the types you want to inject in the ConfigureServices method in the Startup.cs file, as in the following code:</span></span>

```csharp
// Registration of types into ASP.NET Core built-in container
public void ConfigureServices(IServiceCollection services)
{
    // Register out-of-the-box framework services.
    services.AddDbContext<CatalogContext>(c =>
        c.UseSqlServer(Configuration["ConnectionString"]),
        ServiceLifetime.Scoped);

    services.AddMvc();
    // Register custom application dependencies.
    services.AddScoped<IMyCustomRepository, MyCustomSQLRepository>();
}
```

<span data-ttu-id="b76eb-132">Das bekannteste Muster beim Registrieren von Typen in einem IoC-Container ist die Registrierung eines Typenpaars, d.h. eine Schnittstelle und die zugehörige Implementierungsklasse.</span><span class="sxs-lookup"><span data-stu-id="b76eb-132">The most common pattern when registering types in an IoC container is to register a pair of types—an interface and its related implementation class.</span></span> <span data-ttu-id="b76eb-133">Wenn Sie ein Objekt aus dem IoC-Container über einen beliebigen anderen Konstruktor anfordern, fordern Sie ein Objekt eines bestimmten Schnittstellentyps an.</span><span class="sxs-lookup"><span data-stu-id="b76eb-133">Then when you request an object from the IoC container through any constructor, you request an object of a certain type of interface.</span></span> <span data-ttu-id="b76eb-134">Beispielsweise gibt die letzte Zeile aus dem vorherigen Beispiel an, dass der IoC-Container eine Instanz der MyCustomSQLServerRepository-Implementierungsklasse einfügt, wenn Ihre Konstruktoren eine Abhängigkeit von IMyCustomRepository (Schnittstellen oder Abstraktion) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-134">For instance, in the previous example, the last line states that when any of your constructors have a dependency on IMyCustomRepository (interface or abstraction), the IoC container will inject an instance of the MyCustomSQLServerRepository implementation class.</span></span>

#### <a name="use-the-scrutor-library-for-automatic-types-registration"></a><span data-ttu-id="b76eb-135">Verwenden der Scrutor-Bibliothek zur automatischen Typenregistrierung</span><span class="sxs-lookup"><span data-stu-id="b76eb-135">Use the Scrutor library for automatic types registration</span></span>

<span data-ttu-id="b76eb-136">Bei Verwendung der DI in .NET Core empfiehlt es sich, eine Assembly zu überprüfen und ihre Typen automatisch gemäß Konvention zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="b76eb-136">When using DI in .NET Core, you might want to be able to scan an assembly and automatically register its types by convention.</span></span> <span data-ttu-id="b76eb-137">Dieses Feature ist in ASP.NET Core derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b76eb-137">This feature is not currently available in ASP.NET Core.</span></span> <span data-ttu-id="b76eb-138">Sie können jedoch die [Scrutor](https://github.com/khellang/Scrutor)-Bibliothek zu diesem Zweck verwenden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-138">However, you can use the [Scrutor](https://github.com/khellang/Scrutor) library for that.</span></span> <span data-ttu-id="b76eb-139">Dieser Ansatz eignet sich, wenn Sie Dutzende von Typen haben, die im IoC-Container registriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-139">This approach is convenient when you have dozens of types that need to be registered in your IoC container.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="b76eb-140">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b76eb-140">Additional resources</span></span>

- <span data-ttu-id="b76eb-141">**Matthew King. Registering services with Scrutor (Registrieren von Diensten mit Scrutor)**  </span><span class="sxs-lookup"><span data-stu-id="b76eb-141">**Matthew King. Registering services with Scrutor** </span></span>\
  <https://www.mking.net/blog/registering-services-with-scrutor>

- <span data-ttu-id="b76eb-142">**Kristian Hellang. Scrutor.**</span><span class="sxs-lookup"><span data-stu-id="b76eb-142">**Kristian Hellang. Scrutor.**</span></span> <span data-ttu-id="b76eb-143">GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="b76eb-143">GitHub repo.</span></span> \
  <https://github.com/khellang/Scrutor>

#### <a name="use-autofac-as-an-ioc-container"></a><span data-ttu-id="b76eb-144">Verwenden von Autofac als IoC-Container</span><span class="sxs-lookup"><span data-stu-id="b76eb-144">Use Autofac as an IoC container</span></span>

<span data-ttu-id="b76eb-145">Sie können auch zusätzliche IoC-Container verwenden und diese direkt an die Pipeline von ASP.NET Core anschließen, wie z.B. im Microservice für Bestellung in eShopOnContainers, der [Autofac](https://autofac.org/) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b76eb-145">You can also use additional IoC containers and plug them into the ASP.NET Core pipeline, as in the ordering microservice in eShopOnContainers, which uses [Autofac](https://autofac.org/).</span></span> <span data-ttu-id="b76eb-146">Bei Verwendung von Autofac werden in der Regel die Typen über Module registriert, die ermöglichen, die Registrierungstypen zwischen mehreren Dateien je nachdem zu teilen, wo sich die Typen befinden. Die Anwendungstypen können aber auch über mehrere Klassenbibliotheken verteilt sein.</span><span class="sxs-lookup"><span data-stu-id="b76eb-146">When using Autofac you typically register the types via modules, which allow you to split the registration types between multiple files depending on where your types are, just as you could have the application types distributed across multiple class libraries.</span></span>

<span data-ttu-id="b76eb-147">Das folgende Modul beispielsweise ist das [Autofac-Anwendungsmodul](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) für das [Ordering.API-Web-API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API)-Projekt mit den Typen, die Sie einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="b76eb-147">For example, the following is the [Autofac application module](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) for the [Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) project with the types you will want to inject.</span></span>

```csharp
public class ApplicationModule : Autofac.Module
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

<span data-ttu-id="b76eb-148">Autofac hat auch eine Funktion, um [Assemblys und Registertypen auf Namenskonventionen](https://autofac.readthedocs.io/en/latest/register/scanning.html) zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-148">Autofac also has a feature to [scan assemblies and register types by name conventions](https://autofac.readthedocs.io/en/latest/register/scanning.html).</span></span>

<span data-ttu-id="b76eb-149">Der Registrierungsvorgang und die Konzepte ähneln stark der Methode für die Typenregistrierung mit dem integrierten ASP.NET Core-IoC-Container, aber die Syntax unterscheidet sich geringfügig bei der Verwendung von Autofac.</span><span class="sxs-lookup"><span data-stu-id="b76eb-149">The registration process and concepts are very similar to the way you can register types with the built-in ASP.NET Core IoC container, but the syntax when using Autofac is a bit different.</span></span>

<span data-ttu-id="b76eb-150">Im Beispielcode wird die Abstraktion IOrderRepository zusammen mit der Implementierungsklasse OrderRepository registriert.</span><span class="sxs-lookup"><span data-stu-id="b76eb-150">In the example code, the abstraction IOrderRepository is registered along with the implementation class OrderRepository.</span></span> <span data-ttu-id="b76eb-151">Dies bedeutet, dass IoC-Container eine Instanz der OrderRepository-Klasse einfügen, wenn ein Konstruktor eine Abhängigkeit über die IOrderRepository-Abstraktion oder -Schnittstelle deklariert.</span><span class="sxs-lookup"><span data-stu-id="b76eb-151">This means that whenever a constructor is declaring a dependency through the IOrderRepository abstraction or interface, the IoC container will inject an instance of the OrderRepository class.</span></span>

<span data-ttu-id="b76eb-152">Der Instanzbereichstyp bestimmt, wie eine Instanz von Anforderungen für den gleichen Dienst oder die gleiche Abhängigkeit gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="b76eb-152">The instance scope type determines how an instance is shared between requests for the same service or dependency.</span></span> <span data-ttu-id="b76eb-153">Wenn eine Anforderung für eine Abhängigkeit gestellt wird, kann der IoC-Container Folgendes zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="b76eb-153">When a request is made for a dependency, the IoC container can return the following:</span></span>

- <span data-ttu-id="b76eb-154">Eine einzelne Instanz pro Lebensdauerbereich (gemäß dem ASP.NET Core-IoC-Container *bereichsbezogen*).</span><span class="sxs-lookup"><span data-stu-id="b76eb-154">A single instance per lifetime scope (referred to in the ASP.NET Core IoC container as *scoped*).</span></span>

- <span data-ttu-id="b76eb-155">Eine neue Instanz pro Abhängigkeit (gemäß dem ASP.NET Core-IoC-Container *vorübergehend*).</span><span class="sxs-lookup"><span data-stu-id="b76eb-155">A new instance per dependency (referred to in the ASP.NET Core IoC container as *transient*).</span></span>

- <span data-ttu-id="b76eb-156">Eine einzelne Instanz, die von allen Objekten gemeinsam genutzt wird, die den IoC-Container verwenden (gemäß dem ASP.NET Core IoC-Container *Singleton*).</span><span class="sxs-lookup"><span data-stu-id="b76eb-156">A single instance shared across all objects using the IoC container (referred to in the ASP.NET Core IoC container as *singleton*).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="b76eb-157">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b76eb-157">Additional resources</span></span>

- <span data-ttu-id="b76eb-158">**Einführung in Abhängigkeitsinjektion in ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="b76eb-158">**Introduction to Dependency Injection in ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection](/aspnet/core/fundamentals/dependency-injection)

- <span data-ttu-id="b76eb-159">**Autofac.**</span><span class="sxs-lookup"><span data-stu-id="b76eb-159">**Autofac.**</span></span> <span data-ttu-id="b76eb-160">Offizielle Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="b76eb-160">Official documentation.</span></span> \
  <https://docs.autofac.org/en/latest/>

- <span data-ttu-id="b76eb-161">**Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes – Cesar de la Torre (Vergleichen der Lebensdauer von Containerdiensten mit ASP.NET Core IoC und Autofac IoC-Containerinstanzbereichen – Cesar de la Torre**</span><span class="sxs-lookup"><span data-stu-id="b76eb-161">**Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes - Cesar de la Torre.**</span></span> \
  <https://devblogs.microsoft.com/cesardelatorre/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/>

## <a name="implement-the-command-and-command-handler-patterns"></a><span data-ttu-id="b76eb-162">Implementieren von Befehls- und Befehlshandlermustern</span><span class="sxs-lookup"><span data-stu-id="b76eb-162">Implement the Command and Command Handler patterns</span></span>

<span data-ttu-id="b76eb-163">Im Beispiel DI-über-Konstruktor im vorherigen Abschnitt hat der IoC-Container Repositorys über einen Konstruktor in einer Klasse eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b76eb-163">In the DI-through-constructor example shown in the previous section, the IoC container was injecting repositories through a constructor in a class.</span></span> <span data-ttu-id="b76eb-164">Aber wo genau wurden diese eingefügt?</span><span class="sxs-lookup"><span data-stu-id="b76eb-164">But exactly where were they injected?</span></span> <span data-ttu-id="b76eb-165">In einer einfachen Web-API (z.B. Katalogmicroservice in eShopOnContainers) fügen Sie sie auf der Ebene des MVC-Controllers als Teil der Anforderungspipeline von ASP.NET Core in einen Controllerkonstruktor ein.</span><span class="sxs-lookup"><span data-stu-id="b76eb-165">In a simple Web API (for example, the catalog microservice in eShopOnContainers), you inject them at the MVC controllers’ level, in a controller constructor, as part of the request pipeline of ASP.NET Core.</span></span> <span data-ttu-id="b76eb-166">Allerdings erfolgt die Einfügung von Abhängigkeiten im anfänglichen Code in diesem Abschnitt ([CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs)-Klasse aus dem Ordering.API-Dienst in eShopOnContainers) über den Konstruktor eines bestimmten Befehlshandlers.</span><span class="sxs-lookup"><span data-stu-id="b76eb-166">However, in the initial code of this section (the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) class from the Ordering.API service in eShopOnContainers), the injection of dependencies is done through the constructor of a particular command handler.</span></span> <span data-ttu-id="b76eb-167">Lassen Sie uns erklären, was ein Befehlshandler ist und weshalb Sie ihn verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="b76eb-167">Let us explain what a command handler is and why you would want to use it.</span></span>

<span data-ttu-id="b76eb-168">Das Befehlsmuster bezieht sich systemintern auf das CQRS-Muster, das weiter oben in dieser Anleitung erläutert wurde.</span><span class="sxs-lookup"><span data-stu-id="b76eb-168">The Command pattern is intrinsically related to the CQRS pattern that was introduced earlier in this guide.</span></span> <span data-ttu-id="b76eb-169">CQRS verfügt über zwei Seiten.</span><span class="sxs-lookup"><span data-stu-id="b76eb-169">CQRS has two sides.</span></span> <span data-ttu-id="b76eb-170">Der erste Bereich sind Abfragen unter Verwendung vereinfachter Abfragen mit der [Dapper](https://github.com/StackExchange/dapper-dot-net)-micro-ORM, der zuvor erläutert wurde.</span><span class="sxs-lookup"><span data-stu-id="b76eb-170">The first area is queries, using simplified queries with the [Dapper](https://github.com/StackExchange/dapper-dot-net) micro ORM, which was explained previously.</span></span> <span data-ttu-id="b76eb-171">Der zweite Bereich sind Befehle, die der Ausgangspunkt für Transaktionen sind, und der Eingabekanal außerhalb des Diensts.</span><span class="sxs-lookup"><span data-stu-id="b76eb-171">The second area is commands, which are the starting point for transactions, and the input channel from outside the service.</span></span>

<span data-ttu-id="b76eb-172">Wie in Abbildung 7-24 dargestellt, basiert das Muster auf der clientseitigen Annahme von Befehlen und ihre Verarbeitung auf Grundlage von Domänenmodellregeln und schließlich der Beibehaltung der Status mit Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-172">As shown in Figure 7-24, the pattern is based on accepting commands from the client side, processing them based on the domain model rules, and finally persisting the states with transactions.</span></span>

![Diagramm, das eine Übersicht über den allgemeinen Datenfluss vom Client zur Datenbank zeigt.](./media/microservice-application-layer-implementation-web-api/high-level-writes-side.png)

<span data-ttu-id="b76eb-174">**Abbildung 7-24**.</span><span class="sxs-lookup"><span data-stu-id="b76eb-174">**Figure 7-24**.</span></span> <span data-ttu-id="b76eb-175">Überblick über die Befehle oder die „Transaktionsseite“ in einem CQRS-Muster</span><span class="sxs-lookup"><span data-stu-id="b76eb-175">High-level view of the commands or “transactional side” in a CQRS pattern</span></span>

<span data-ttu-id="b76eb-176">Abbildung 7–24 zeigt, dass die Benutzeroberflächen-App einen Befehl über die API sendet, der zu einem `CommandHandler` gelangt, der vom Domänenmodell und der Infrastruktur abhängt, um die Datenbank zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b76eb-176">Figure 7-24 shows that the UI app sends a command through the API that gets to a `CommandHandler`, that depends on the Domain model and the Infrastructure, to update the database.</span></span>

### <a name="the-command-class"></a><span data-ttu-id="b76eb-177">Die Befehlsklasse</span><span class="sxs-lookup"><span data-stu-id="b76eb-177">The command class</span></span>

<span data-ttu-id="b76eb-178">Ein Befehl ist eine Anforderung für das System zum Ausführen einer Aktion, die den Zustand des Systems ändert.</span><span class="sxs-lookup"><span data-stu-id="b76eb-178">A command is a request for the system to perform an action that changes the state of the system.</span></span> <span data-ttu-id="b76eb-179">Befehle sind imperativ und sollten nur einmal verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-179">Commands are imperative, and should be processed just once.</span></span>

<span data-ttu-id="b76eb-180">Befehle sind zwingende Erfordernisse, werden in der Regel mit einem Verb im Infinitiv gebildet (z.B. „Erstellen“ oder „Aktualisieren“) und können den Aggregattyp, z.B. CreateOrderCommand, enthalten.</span><span class="sxs-lookup"><span data-stu-id="b76eb-180">Since commands are imperatives, they are typically named with a verb in the imperative mood (for example, "create" or "update"), and they might include the aggregate type, such as CreateOrderCommand.</span></span> <span data-ttu-id="b76eb-181">Anders als ein Ereignis ist ein Befehl kein Fakt aus der Vergangenheit, sondern nur eine Anforderung, die auch abgelehnt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b76eb-181">Unlike an event, a command is not a fact from the past; it is only a request, and thus may be refused.</span></span>

<span data-ttu-id="b76eb-182">Befehle können ihren Ursprung in der Benutzeroberfläche als Ergebnis einer Initiierung einer Anforderung durch einen Benutzer oder von einem Prozess-Manager haben, der ein Aggregat zum Ausführen einer Aktion weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="b76eb-182">Commands can originate from the UI as a result of a user initiating a request, or from a process manager when the process manager is directing an aggregate to perform an action.</span></span>

<span data-ttu-id="b76eb-183">Ein wichtiges Merkmal eines Befehls ist, dass er nur einmal von einem einzelnen Empfänger verarbeitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b76eb-183">An important characteristic of a command is that it should be processed just once by a single receiver.</span></span> <span data-ttu-id="b76eb-184">Dies ist darauf zurückzuführen, dass der Befehl eine einzelne Aktion oder Transaktion ist, die Sie in der Anwendung durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="b76eb-184">This is because a command is a single action or transaction you want to perform in the application.</span></span> <span data-ttu-id="b76eb-185">Beispielsweise sollte ein Bestellungserstellungsbefehl nur einmal ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-185">For example, the same order creation command should not be processed more than once.</span></span> <span data-ttu-id="b76eb-186">Dies ist ein wichtiger Unterschied zwischen Befehlen und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-186">This is an important difference between commands and events.</span></span> <span data-ttu-id="b76eb-187">Ereignisse können mehrmals verarbeitet werden, da viele Systeme oder Microservices am Ereignis interessiert sein können.</span><span class="sxs-lookup"><span data-stu-id="b76eb-187">Events may be processed multiple times, because many systems or microservices might be interested in the event.</span></span>

<span data-ttu-id="b76eb-188">Darüber hinaus ist es wichtig, dass ein Befehl für den Fall, dass er nicht idempotent ist, nur einmal verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b76eb-188">In addition, it is important that a command be processed only once in case the command is not idempotent.</span></span> <span data-ttu-id="b76eb-189">Ein Befehl ist idempotent, wenn er mehrere Male ausgeführt werden kann, ohne das Ergebnis entweder aufgrund der Art des Befehls oder aufgrund der Art und Weise, wie das System den Befehl behandelt, zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b76eb-189">A command is idempotent if it can be executed multiple times without changing the result, either because of the nature of the command, or because of the way the system handles the command.</span></span>

<span data-ttu-id="b76eb-190">Es wird empfohlen, Befehle und Updates, sofern dies nach den Geschäftsregeln und Invarianten Ihrer Domäne sinnvoll erscheint, idempotent zu machen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-190">It is a good practice to make your commands and updates idempotent when it makes sense under your domain’s business rules and invariants.</span></span> <span data-ttu-id="b76eb-191">Um das gleiche Beispiel zu verwenden: Wenn der gleiche CreateOrder-Befehl aus einem beliebigen Grund (Wiederholungslogik, Hacker usw.) Ihr System mehrmals erreicht, sollten Sie in der Lage sein, ihn zu identifizieren und sicherzustellen, dass nicht mehrere Bestellungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-191">For instance, to use the same example, if for any reason (retry logic, hacking, etc.) the same CreateOrder command reaches your system multiple times, you should be able to identify it and ensure that you do not create multiple orders.</span></span> <span data-ttu-id="b76eb-192">Zu diesem Zweck müssen Sie ein Art von Identität in den Vorgängen anfügen und feststellen, ob der Befehl oder das Update bereits verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="b76eb-192">To do so, you need to attach some kind of identity in the operations and identify whether the command or update was already processed.</span></span>

<span data-ttu-id="b76eb-193">Sie senden einen Befehl an einen einzelnen Empfänger, d.h. Sie veröffentlichen einen Befehl nicht.</span><span class="sxs-lookup"><span data-stu-id="b76eb-193">You send a command to a single receiver; you do not publish a command.</span></span> <span data-ttu-id="b76eb-194">Die Veröffentlichung wendet sich an Ereignisse, die einen Fakt anführen, z.B. dass etwas passiert ist und dass dies für Ereignisempfänger interessant sein kann.</span><span class="sxs-lookup"><span data-stu-id="b76eb-194">Publishing is for events that state a fact—that something has happened and might be interesting for event receivers.</span></span> <span data-ttu-id="b76eb-195">Im Fall von Ereignissen spielt es für den Verleger keine Rolle, welche Empfänger das Ereignis erhalten oder wie sie es verwenden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-195">In the case of events, the publisher has no concerns about which receivers get the event or what they do it.</span></span> <span data-ttu-id="b76eb-196">Mit Domänen- oder Integrationsereignissen verhält es sich jedoch anders, wie bereits in vorherigen Abschnitten vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="b76eb-196">But domain or integration events are a different story already introduced in previous sections.</span></span>

<span data-ttu-id="b76eb-197">Ein Befehl ist mit einer Klasse implementiert, die Datenfelder oder Sammlungen mit allen Informationen enthält, die benötigt werden, um diesen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-197">A command is implemented with a class that contains data fields or collections with all the information that is needed in order to execute that command.</span></span> <span data-ttu-id="b76eb-198">Ein Befehl ist eine besondere Art von Data Transfer Object (DTO), das speziell zum Anfordern von Änderungen oder Transaktionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b76eb-198">A command is a special kind of Data Transfer Object (DTO), one that is specifically used to request changes or transactions.</span></span> <span data-ttu-id="b76eb-199">Der Befehl selbst basiert auf genau den Informationen, die für die Verarbeitung des Befehls erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b76eb-199">The command itself is based on exactly the information that is needed for processing the command, and nothing more.</span></span>

<span data-ttu-id="b76eb-200">Das folgende Beispiel zeigt die vereinfachte `CreateOrderCommand`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b76eb-200">The following example shows the simplified `CreateOrderCommand` class.</span></span> <span data-ttu-id="b76eb-201">Dies ist ein unveränderlicher-Befehl, der in dem Microservice für Bestellung in eShopOnContainers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b76eb-201">This is an immutable command that is used in the ordering microservice in eShopOnContainers.</span></span>

```csharp
// DDD and CQRS patterns comment
// Note that we recommend that you implement immutable commands
// In this case, immutability is achieved by having all the setters as private
// plus being able to update the data just once, when creating the object
// through the constructor.
// References on immutable commands:
// http://cqrs.nu/Faq
// https://docs.spine3.org/motivation/immutability.html
// http://blog.gauffin.org/2012/06/griffin-container-introducing-command-support/
// https://docs.microsoft.com/dotnet/csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties
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

    public CreateOrderCommand(List<BasketItem> basketItems, string city,
        string street,
        string state, string country, string zipcode,
        string cardNumber, string cardHolderName, DateTime cardExpiration,
        string cardSecurityNumber, int cardTypeId) : this()
    {
        _orderItems = MapToOrderItems(basketItems);
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

<span data-ttu-id="b76eb-202">Die Befehlsklasse enthält im Grunde die zum Ausführen einer Geschäftstransaktion mithilfe der Domänenmodellobjekte benötigten Daten.</span><span class="sxs-lookup"><span data-stu-id="b76eb-202">Basically, the command class contains all the data you need for performing a business transaction by using the domain model objects.</span></span> <span data-ttu-id="b76eb-203">Daher sind die Befehle einfach Datenstrukturen, die schreibgeschützte Daten und kein Verhalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="b76eb-203">Thus, commands are simply data structures that contain read-only data, and no behavior.</span></span> <span data-ttu-id="b76eb-204">Der Name des Befehls gibt seinen Zweck an.</span><span class="sxs-lookup"><span data-stu-id="b76eb-204">The command’s name indicates its purpose.</span></span> <span data-ttu-id="b76eb-205">In vielen Sprachen, z.B. in C#, werden Befehle als Klassen dargestellt, sind aber keine echten Klassen im objektorientierten Sinn.</span><span class="sxs-lookup"><span data-stu-id="b76eb-205">In many languages like C#, commands are represented as classes, but they are not true classes in the real object-oriented sense.</span></span>

<span data-ttu-id="b76eb-206">Befehle haben eine zusätzliche Eigenschaft, d.h. sie sind unveränderlich, da erwartet wird, dass sie direkt vom Domänenmodell verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-206">As an additional characteristic, commands are immutable, because the expected usage is that they are processed directly by the domain model.</span></span> <span data-ttu-id="b76eb-207">Sie müssen während ihrer projizierten Lebensdauer nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-207">They do not need to change during their projected lifetime.</span></span> <span data-ttu-id="b76eb-208">In einer C#-Klasse kann Unveränderlichkeit dadurch erreicht werden, dass keine Setter oder andere Methoden verwendet werden, die den internen Status ändern.</span><span class="sxs-lookup"><span data-stu-id="b76eb-208">In a C# class, immutability can be achieved by not having any setters or other methods that change internal state.</span></span>

<span data-ttu-id="b76eb-209">Beachten Sie, dass zum Durchlaufen des Serialisierungs-/Deserialisierungsprozesses durch Befehle die Eigenschaften den Setter „privat“ und das Attribut `[DataMember]` (oder `[JsonProperty]`) erfordern.</span><span class="sxs-lookup"><span data-stu-id="b76eb-209">Keep in mind that if you intend or expect commands to go through a serializing/deserializing process, the properties must have a private setter, and the `[DataMember]` (or `[JsonProperty]`) attribute.</span></span> <span data-ttu-id="b76eb-210">Andernfalls kann der Deserialisierer das Objekt im Ziel nicht mit den erforderlichen Werten rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="b76eb-210">Otherwise, the deserializer won't be able to reconstruct the object at destination with the required values.</span></span> <span data-ttu-id="b76eb-211">Sie können auch tatsächlich schreibgeschützte Eigenschaften verwenden, wenn die Klasse einen Konstruktor mit Parametern für alle Eigenschaften mit der üblichen camelCase-Benennungskonvention hat, und den Konstruktor mit `[JsonConstructor]` kommentieren.</span><span class="sxs-lookup"><span data-stu-id="b76eb-211">You can also use truly read-only properties if the class has a constructor with parameters for all properties, with the usual camelCase naming convention, and annotate the constructor as `[JsonConstructor]`.</span></span> <span data-ttu-id="b76eb-212">Diese Option erfordert jedoch mehr Code.</span><span class="sxs-lookup"><span data-stu-id="b76eb-212">However, this option requires more code.</span></span>

<span data-ttu-id="b76eb-213">Die Befehlsklasse zum Erstellen einer Bestellung beispielsweise ist möglicherweise im Hinblick auf Daten der Bestellung ähnlich, die Sie erstellen möchten, aber Sie benötigen wahrscheinlich nicht die gleichen Attribute.</span><span class="sxs-lookup"><span data-stu-id="b76eb-213">For example, the command class for creating an order is probably similar in terms of data to the order you want to create, but you probably do not need the same attributes.</span></span> <span data-ttu-id="b76eb-214">Beispielsweise enthält `CreateOrderCommand` keine Bestell-ID, da die Bestellung noch nicht erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b76eb-214">For instance, `CreateOrderCommand` does not have an order ID, because the order has not been created yet.</span></span>

<span data-ttu-id="b76eb-215">Viele Befehlsklassen können einfach sein und nur wenige Felder über einen Zustand erfordern, der geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="b76eb-215">Many command classes can be simple, requiring only a few fields about some state that needs to be changed.</span></span> <span data-ttu-id="b76eb-216">Das wäre der Fall, wenn Sie nur den Status einer Bestellung aus „In Bearbeitung“ in „Bezahlt“ oder „Geliefert“ ändern, indem Sie einen Befehl wie den Folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="b76eb-216">That would be the case if you are just changing the status of an order from “in process” to “paid” or “shipped” by using a command similar to the following:</span></span>

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

<span data-ttu-id="b76eb-217">Einige Entwickler trennen ihre Benutzeroberflächen-Anforderungsobjekte von den Befehls-DTOs, was jedoch eine „Geschmacksfrage“ ist.</span><span class="sxs-lookup"><span data-stu-id="b76eb-217">Some developers make their UI request objects separate from their command DTOs, but that is just a matter of preference.</span></span> <span data-ttu-id="b76eb-218">Die Trennung ist zeitraubend und nur mit geringem Mehrwert verbunden, und die Form der Objekte ist nahezu identisch.</span><span class="sxs-lookup"><span data-stu-id="b76eb-218">It is a tedious separation with not much added value, and the objects are almost exactly the same shape.</span></span> <span data-ttu-id="b76eb-219">In eShopOnContainers beispielsweise stammen einige Befehle direkt von der Clientseite.</span><span class="sxs-lookup"><span data-stu-id="b76eb-219">For instance, in eShopOnContainers, some commands come directly from the client side.</span></span>

### <a name="the-command-handler-class"></a><span data-ttu-id="b76eb-220">Die Befehlshandler-Klasse</span><span class="sxs-lookup"><span data-stu-id="b76eb-220">The Command handler class</span></span>

<span data-ttu-id="b76eb-221">Sie sollten für jeden Befehl eine bestimmte Befehlshandler-Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="b76eb-221">You should implement a specific command handler class for each command.</span></span> <span data-ttu-id="b76eb-222">Sie gibt vor, wie das Muster funktioniert, und ist der Ort, an dem Sie das Befehlsobjekt, die Domänenobjekte und die Repositoryobjekte der Infrastruktur verwenden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-222">That is how the pattern works, and it's where you'll use the command object, the domain objects, and the infrastructure repository objects.</span></span> <span data-ttu-id="b76eb-223">Der Befehlshandler ist das Herzstück der Anwendungsschicht im Hinblick auf CQRS und DDD.</span><span class="sxs-lookup"><span data-stu-id="b76eb-223">The command handler is in fact the heart of the application layer in terms of CQRS and DDD.</span></span> <span data-ttu-id="b76eb-224">Allerdings sollte die Domänenlogik in den Domänenklassen enthalten sein, und zwar in den aggregierten Stämmen (Stammentitäten), untergeordneten Entitäten oder [Domänendiensten](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), aber nicht im Befehlshandler, der eine Klasse der Anwendungsschicht ist.</span><span class="sxs-lookup"><span data-stu-id="b76eb-224">However, all the domain logic should be contained in the domain classes—within the aggregate roots (root entities), child entities, or [domain services](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), but not within the command handler, which is a class from the application layer.</span></span>

<span data-ttu-id="b76eb-225">Die Befehlshandlerklasse eignet sich ideal zum Erreichen bereits erwähnten Prinzips der einzigen Verantwortung.</span><span class="sxs-lookup"><span data-stu-id="b76eb-225">The command handler class offers a strong stepping stone in the way to achieve the Single Responsibility Principle (SRP) mentioned in a previous section.</span></span>

<span data-ttu-id="b76eb-226">Ein Befehlshandler empfängt einen Befehl und erhält ein Ergebnis aus dem Aggregat, das verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b76eb-226">A command handler receives a command and obtains a result from the aggregate that is used.</span></span> <span data-ttu-id="b76eb-227">Das Ergebnis sollte die erfolgreiche Ausführung des Befehls oder eine Ausnahme sein.</span><span class="sxs-lookup"><span data-stu-id="b76eb-227">The result should be either successful execution of the command, or an exception.</span></span> <span data-ttu-id="b76eb-228">Im Falle einer Ausnahme sollte der Systemstatus nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-228">In the case of an exception, the system state should be unchanged.</span></span>

<span data-ttu-id="b76eb-229">In den Befehlshandler fließen normalerweise die folgenden Schritte ein:</span><span class="sxs-lookup"><span data-stu-id="b76eb-229">The command handler usually takes the following steps:</span></span>

- <span data-ttu-id="b76eb-230">Er empfängt das Befehlsobjekt wie ein DTO (aus dem [Vermittler](https://en.wikipedia.org/wiki/Mediator_pattern)- oder einem anderen Infrastrukturobjekt).</span><span class="sxs-lookup"><span data-stu-id="b76eb-230">It receives the command object, like a DTO (from the [mediator](https://en.wikipedia.org/wiki/Mediator_pattern) or other infrastructure object).</span></span>

- <span data-ttu-id="b76eb-231">Er überprüft, ob der Befehl (sofern nicht durch den Vermittler überprüft) gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b76eb-231">It validates that the command is valid (if not validated by the mediator).</span></span>

- <span data-ttu-id="b76eb-232">Er instanziiert die Aggregatstamminstanz, die das Ziel des aktuellen Befehls ist.</span><span class="sxs-lookup"><span data-stu-id="b76eb-232">It instantiates the aggregate root instance that is the target of the current command.</span></span>

- <span data-ttu-id="b76eb-233">Sie führt die Methode für die Aggregatsstamminstanz aus und erhält dabei die erforderlichen Daten vom Befehl.</span><span class="sxs-lookup"><span data-stu-id="b76eb-233">It executes the method on the aggregate root instance, getting the required data from the command.</span></span>

- <span data-ttu-id="b76eb-234">Sie behält den neuen Zustand des Aggregats in Bezug auf die zugehörige Datenbank bei.</span><span class="sxs-lookup"><span data-stu-id="b76eb-234">It persists the new state of the aggregate to its related database.</span></span> <span data-ttu-id="b76eb-235">Dieser letzte Vorgang ist die eigentliche Transaktion.</span><span class="sxs-lookup"><span data-stu-id="b76eb-235">This last operation is the actual transaction.</span></span>

<span data-ttu-id="b76eb-236">Normalerweise befasst sich der Befehlshandler mit einem einzelnen Aggregat, das von seinem Aggregatstamm (Stammentität) gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="b76eb-236">Typically, a command handler deals with a single aggregate driven by its aggregate root (root entity).</span></span> <span data-ttu-id="b76eb-237">Wenn mehrere Aggregate vom Empfang eines einzelnen Befehls betroffen sein sollen, können Sie mit den Domänenereignissen Status oder Aktionen über mehrere Aggregate weitergeben.</span><span class="sxs-lookup"><span data-stu-id="b76eb-237">If multiple aggregates should be impacted by the reception of a single command, you could use domain events to propagate states or actions across multiple aggregates.</span></span>

<span data-ttu-id="b76eb-238">Wichtig dabei ist, dass sich die Domänenlogik bei der Verarbeitung eines Befehls im Domänenmodell (Aggregat) befinden, vollständig gekapselt und bereit für die Komponententests sein soll.</span><span class="sxs-lookup"><span data-stu-id="b76eb-238">The important point here is that when a command is being processed, all the domain logic should be inside the domain model (the aggregates), fully encapsulated and ready for unit testing.</span></span> <span data-ttu-id="b76eb-239">Befehlshandler sind lediglich eine Möglichkeit, um das Domänenmodell aus der Datenbank abzurufen und zum Schluss die Infrastrukturschicht (Repositorys) anzuweisen, die Änderungen beizubehalten, wenn das Modell geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b76eb-239">The command handler just acts as a way to get the domain model from the database, and as the final step, to tell the infrastructure layer (repositories) to persist the changes when the model is changed.</span></span> <span data-ttu-id="b76eb-240">Der Vorteil dieses Ansatzes ist, dass Sie die Domänenlogik in ein isoliertes, vollständig gekapseltes, umfangreiches, verhaltensbasiertes Domänenmodell umgestalten können, ohne Code in der Anwendung oder in Infrastrukturschichten zu ändern, die die Grundstruktur (Befehlshandler, Web-API, Repositorys usw.) bilden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-240">The advantage of this approach is that you can refactor the domain logic in an isolated, fully encapsulated, rich, behavioral domain model without changing code in the application or infrastructure layers, which are the plumbing level (command handlers, Web API, repositories, etc.).</span></span>

<span data-ttu-id="b76eb-241">Wenn Befehlshandler komplex werden und mit zu viel Logik einhergehen, kann dies zu schlecht strukturiertem Code führen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-241">When command handlers get complex, with too much logic, that can be a code smell.</span></span> <span data-ttu-id="b76eb-242">Überprüfen Sie sie. Wenn Sie Domänenlogik finden, gestalten Sie den Code um, um dieses Domänenverhalten auf die Methoden der Domänenobjekte (Aggregatstamm und untergeordnete Entität) zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-242">Review them, and if you find domain logic, refactor the code to move that domain behavior to the methods of the domain objects (the aggregate root and child entity).</span></span>

<span data-ttu-id="b76eb-243">Der folgende Code zeigt als Beispiel einer Befehlshandlerklasse die gleiche `CreateOrderCommandHandler`-Klasse, die Sie bereits am Anfang des Kapitels gesehen haben.</span><span class="sxs-lookup"><span data-stu-id="b76eb-243">As an example of a command handler class, the following code shows the same `CreateOrderCommandHandler` class that you saw at the beginning of this chapter.</span></span> <span data-ttu-id="b76eb-244">In diesem Fall sollen die Handle-Methode und die Vorgänge mit den Domänenmodellobjekten/Aggregaten hervorgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-244">In this case, we want to highlight the Handle method and the operations with the domain model objects/aggregates.</span></span>

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
                                     IOrderRepository orderRepository,
                                     IIdentityService identityService)
    {
        _orderRepository = orderRepository ??
                          throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ??
                          throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ??
                                 throw new ArgumentNullException(nameof(mediator));
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State,
                                  message.Country, message.ZipCode);
        var order = new Order(message.UserId, address, message.CardTypeId,
                              message.CardNumber, message.CardSecurityNumber,
                              message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                               item.Discount, item.PictureUrl, item.Units);
        }

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
    }
}
```

<span data-ttu-id="b76eb-245">Hierbei handelt es sich um zusätzliche Schritte, die ein Befehlshandler ausführen sollte:</span><span class="sxs-lookup"><span data-stu-id="b76eb-245">These are additional steps a command handler should take:</span></span>

- <span data-ttu-id="b76eb-246">Verwenden Sie die Daten des Befehls für Arbeit mit den Methoden und dem Verhalten des Aggregatstamms.</span><span class="sxs-lookup"><span data-stu-id="b76eb-246">Use the command’s data to operate with the aggregate root’s methods and behavior.</span></span>

- <span data-ttu-id="b76eb-247">Lösen Sie intern in den Domänenobjekten Domänenereignisse aus, während die Transaktion ausgeführt wird, was aus der Sicht des Befehlshandlers transparent ist.</span><span class="sxs-lookup"><span data-stu-id="b76eb-247">Internally within the domain objects, raise domain events while the transaction is executed, but that is transparent from a command handler point of view.</span></span>

- <span data-ttu-id="b76eb-248">Wenn das Vorgangsergebnis des Aggregats erfolgreich und die Transaktion beendet ist, lösen Sie Integrationsereignisse aus.</span><span class="sxs-lookup"><span data-stu-id="b76eb-248">If the aggregate’s operation result is successful and after the transaction is finished, raise integration events.</span></span> <span data-ttu-id="b76eb-249">(Diese können auch von Infrastrukturklassen wie Repositorys ausgelöst werden.)</span><span class="sxs-lookup"><span data-stu-id="b76eb-249">(These might also be raised by infrastructure classes like repositories.)</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="b76eb-250">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b76eb-250">Additional resources</span></span>

- <span data-ttu-id="b76eb-251">**Mark Seemann. At the Boundaries, Applications are Not Object-Oriented (An den Grenzen sind Anwendungen nicht objektorientiert)**  </span><span class="sxs-lookup"><span data-stu-id="b76eb-251">**Mark Seemann. At the Boundaries, Applications are Not Object-Oriented** </span></span>\
  <https://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/>

- <span data-ttu-id="b76eb-252">**Commands and events (Befehle und Ereignisse)**  </span><span class="sxs-lookup"><span data-stu-id="b76eb-252">**Commands and events** </span></span>\
  <https://cqrs.nu/Faq/commands-and-events>

- <span data-ttu-id="b76eb-253">**What does a command handler do? (Wie funktioniert ein Befehlshandler?)**</span><span class="sxs-lookup"><span data-stu-id="b76eb-253">**What does a command handler do?**</span></span> \
  <https://cqrs.nu/Faq/command-handlers>

- <span data-ttu-id="b76eb-254">**Jimmy Bogard. Domain Command Patterns – Handlers (Domänenbefehlsmuster – Handler)**  </span><span class="sxs-lookup"><span data-stu-id="b76eb-254">**Jimmy Bogard. Domain Command Patterns – Handlers** </span></span>\
  <https://jimmybogard.com/domain-command-patterns-handlers/>

- <span data-ttu-id="b76eb-255">**Jimmy Bogard. Domain Command Patterns – Validation (Domänenbefehlsmuser – Prüfung)**  </span><span class="sxs-lookup"><span data-stu-id="b76eb-255">**Jimmy Bogard. Domain Command Patterns – Validation** </span></span>\
  <https://jimmybogard.com/domain-command-patterns-validation/>

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a><span data-ttu-id="b76eb-256">Die Befehlsprozesspipeline: So wird ein Befehlshandler ausgelöst</span><span class="sxs-lookup"><span data-stu-id="b76eb-256">The Command process pipeline: how to trigger a command handler</span></span>

<span data-ttu-id="b76eb-257">Die nächste Frage lautet, wie ein Befehlshandler aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b76eb-257">The next question is how to invoke a command handler.</span></span> <span data-ttu-id="b76eb-258">Sie können ihn manuell über jeden zugehörigen ASP.NET Core-Controller aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-258">You could manually call it from each related ASP.NET Core controller.</span></span> <span data-ttu-id="b76eb-259">Der Ansatz wäre allerdings zu sehr gekoppelt und ist nicht ideal.</span><span class="sxs-lookup"><span data-stu-id="b76eb-259">However, that approach would be too coupled and is not ideal.</span></span>

<span data-ttu-id="b76eb-260">Die anderen beiden Hauptoptionen, die empfohlen werden, lauten:</span><span class="sxs-lookup"><span data-stu-id="b76eb-260">The other two main options, which are the recommended options, are:</span></span>

- <span data-ttu-id="b76eb-261">Über ein In-Memory-Vermittlermusterartefakt.</span><span class="sxs-lookup"><span data-stu-id="b76eb-261">Through an in-memory Mediator pattern artifact.</span></span>

- <span data-ttu-id="b76eb-262">Mit einer asynchronen Nachrichtenwarteschlange zwischen Controllern und Handlern.</span><span class="sxs-lookup"><span data-stu-id="b76eb-262">With an asynchronous message queue, in between controllers and handlers.</span></span>

### <a name="use-the-mediator-pattern-in-memory-in-the-command-pipeline"></a><span data-ttu-id="b76eb-263">Verwenden von Vermittlermustern (In-Memory) in der Befehlspipeline</span><span class="sxs-lookup"><span data-stu-id="b76eb-263">Use the Mediator pattern (in-memory) in the command pipeline</span></span>

<span data-ttu-id="b76eb-264">Wie in Abbildung 7-25 dargestellt, verwenden Sie in einem CQRS-Ansatz einen intelligenten Vermittler, ähnlich einem In-Memory-Bus. Dieser ist ausreichend intelligent, um den richtigen Befehlshandler basierend auf dem empfangenen Befehlstyp oder dem DTO (Datentransferobjekt) umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="b76eb-264">As shown in Figure 7-25, in a CQRS approach you use an intelligent mediator, similar to an in-memory bus, which is smart enough to redirect to the right command handler based on the type of the command or DTO being received.</span></span> <span data-ttu-id="b76eb-265">Die schwarzen Pfeile zwischen Komponenten stellen die Abhängigkeiten zwischen Objekten (in vielen Fällen mit DI eingefügt) mit den zugehörigen Interaktionen dar.</span><span class="sxs-lookup"><span data-stu-id="b76eb-265">The single black arrows between components represent the dependencies between objects (in many cases, injected through DI) with their related interactions.</span></span>

![Diagramm, das eine detailliertere Übersicht über den Datenfluss vom Client zur Datenbank zeigt.](./media/microservice-application-layer-implementation-web-api/mediator-cqrs-microservice.png)

<span data-ttu-id="b76eb-267">**Abbildung 7-25**.</span><span class="sxs-lookup"><span data-stu-id="b76eb-267">**Figure 7-25**.</span></span> <span data-ttu-id="b76eb-268">Verwenden des Vermittlermusters in einem CQRS-Microservice</span><span class="sxs-lookup"><span data-stu-id="b76eb-268">Using the Mediator pattern in process in a single CQRS microservice</span></span>

<span data-ttu-id="b76eb-269">Das obige Diagramm zeigt eine Vergrößerung der Abbildung 7–24: Der ASP.NET Core-Controller sendet den Befehl an die Befehlspipeline von MediatR, damit er zum entsprechenden Handler gelangt.</span><span class="sxs-lookup"><span data-stu-id="b76eb-269">The above diagram shows a zoom-in from image 7-24: the ASP.NET Core controller sends the command to MediatR's command pipeline, so they get to the appropriate handler.</span></span>

<span data-ttu-id="b76eb-270">Die Verwendung des Vermittlermusters ist sinnvoll, da Verarbeitungsanforderungen in Unternehmensanforderungen kompliziert sein können.</span><span class="sxs-lookup"><span data-stu-id="b76eb-270">The reason that using the Mediator pattern makes sense is that in enterprise applications, the processing requests can get complicated.</span></span> <span data-ttu-id="b76eb-271">Sie möchten eine offene Anzahl von querschnittlichen Belangen wie Protokollierung, Überprüfungen, Überwachung und Sicherheit hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="b76eb-271">You want to be able to add an open number of cross-cutting concerns like logging, validations, audit, and security.</span></span> <span data-ttu-id="b76eb-272">In diesen Fällen können Sie auf eine Vermittlerpipeline zurückgreifen (weitere Informationen finden Sie unter [Vermittlermuster](https://en.wikipedia.org/wiki/Mediator_pattern)), um ein Mittel für diese zusätzlichen Verhaltensweisen oder querschnittlichen Belange bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-272">In these cases, you can rely on a mediator pipeline (see [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern)) to provide a means for these extra behaviors or cross-cutting concerns.</span></span>

<span data-ttu-id="b76eb-273">Ein Vermittler ist ein Objekt, dass das „wie“ dieses Prozesses kapselt: Er koordiniert die Ausführung basierend auf dem Status, der Art und Weise, wie ein Befehlshandler aufgerufen wird, oder der Nutzlast, die Sie dem Handler bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-273">A mediator is an object that encapsulates the “how” of this process: it coordinates execution based on state, the way a command handler is invoked, or the payload you provide to the handler.</span></span> <span data-ttu-id="b76eb-274">Mit einer Vermittlerkomponente können Sie querschnittliche Belange zentral und transparent anwenden, indem Sie von Decorator-Elemente (oder [Pipeline-Verhaltensweisen](https://github.com/jbogard/MediatR/wiki/Behaviors) seit [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)) anwenden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-274">With a mediator component you can apply cross-cutting concerns in a centralized and transparent way by applying decorators (or [pipeline behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) since [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)).</span></span> <span data-ttu-id="b76eb-275">Weitere Informationen finden Sie unter [Decorator pattern (Decorator-Muster)](https://en.wikipedia.org/wiki/Decorator_pattern).</span><span class="sxs-lookup"><span data-stu-id="b76eb-275">For more information, see the [Decorator pattern](https://en.wikipedia.org/wiki/Decorator_pattern).</span></span>

<span data-ttu-id="b76eb-276">Decorator-Elemente und Verhaltensweisen ähneln der [Aspect Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), werden aber nur auf eine bestimmte Prozesspipeline angewendet, die von der Vermittlerkomponente verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="b76eb-276">Decorators and behaviors are similar to [Aspect Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), only applied to a specific process pipeline managed by the mediator component.</span></span> <span data-ttu-id="b76eb-277">Aspekte in AOP, die übergreifende Anliegen implementieren, werden basierend auf *Aspect Weavers* angewendet, die zum Zeitpunkt der Kompilierung oder basierend auf einer Objektaufruf-Interception eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-277">Aspects in AOP that implement cross-cutting concerns are applied based on *aspect weavers* injected at compilation time or based on object call interception.</span></span> <span data-ttu-id="b76eb-278">Über die beiden typischen AOP-Ansätze wird gesagt, dass sie wie „Zauberei“ funktionieren, da es nicht einfach ist nachzuvollziehen, wie AOP seine Aufgabe erledigt.</span><span class="sxs-lookup"><span data-stu-id="b76eb-278">Both typical AOP approaches are sometimes said to work "like magic," because it is not easy to see how AOP does its work.</span></span> <span data-ttu-id="b76eb-279">Beim Umgang mit schwerwiegenden Problemen oder Fehlern kann das Debuggen von AOP schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="b76eb-279">When dealing with serious issues or bugs, AOP can be difficult to debug.</span></span> <span data-ttu-id="b76eb-280">Da diese Decorator-Elemente/Verhaltensweisen andererseits explizit sind und nur im Rahmen des Vermittlers angewendet werden, ist das Debuggen wesentlich besser vorhersagbar und einfach.</span><span class="sxs-lookup"><span data-stu-id="b76eb-280">On the other hand, these decorators/behaviors are explicit and applied only in the context of the mediator, so debugging is much more predictable and easy.</span></span>

<span data-ttu-id="b76eb-281">Im Microservice für Bestellung von eShopOnContainers werden beispielsweise zwei Musterverhalten implementiert, eine [LogBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs)-Klasse und eine [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs)-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b76eb-281">For example, in the eShopOnContainers ordering microservice, we implemented two sample behaviors, a [LogBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) class and a [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs) class.</span></span> <span data-ttu-id="b76eb-282">Die Implementierung von Verhalten wird im nächsten Abschnitt erläutert. Dort wird erklärt, wie eShopOnContainers [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)-[Verhalten](https://github.com/jbogard/MediatR/wiki/Behaviors) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b76eb-282">The implementation of the behaviors is explained in the next section by showing how eShopOnContainers uses [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors).</span></span>

### <a name="use-message-queues-out-of-proc-in-the-commands-pipeline"></a><span data-ttu-id="b76eb-283">Verwenden von Nachrichtenwarteschlangen (prozessextern) in der Befehlspipeline</span><span class="sxs-lookup"><span data-stu-id="b76eb-283">Use message queues (out-of-proc) in the command’s pipeline</span></span>

<span data-ttu-id="b76eb-284">Eine andere Möglichkeit ist die Verwendung asynchroner Nachrichten basierend auf Brokern oder Nachrichtenwarteschlagen (s. Abbildung 7-26).</span><span class="sxs-lookup"><span data-stu-id="b76eb-284">Another choice is to use asynchronous messages based on brokers or message queues, as shown in Figure 7-26.</span></span> <span data-ttu-id="b76eb-285">Diese Option kann auch mit der Vermittlerkomponente direkt vor dem Befehlshandler kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-285">That option could also be combined with the mediator component right before the command handler.</span></span>

![Diagramm, das den Datenfluss unter Verwendung einer Hochverfügbarkeits-Nachrichtenwarteschlange zeigt.](./media/microservice-application-layer-implementation-web-api/add-ha-message-queue.png)

<span data-ttu-id="b76eb-287">**Abbildung 7-26**.</span><span class="sxs-lookup"><span data-stu-id="b76eb-287">**Figure 7-26**.</span></span> <span data-ttu-id="b76eb-288">Verwenden von Nachrichtenwarteschlangen (prozessexterne und prozessübergreifende Kommunikation) mit CQRS-Befehlen</span><span class="sxs-lookup"><span data-stu-id="b76eb-288">Using message queues (out of process and inter-process communication) with CQRS commands</span></span>

<span data-ttu-id="b76eb-289">Die Befehlspipeline kann auch über eine hochverfügbare Nachrichtenwarteschlange verarbeitet werden, um die Befehle an den entsprechenden Handler zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="b76eb-289">Command's pipeline can also be handled by a high availability message queue to deliver the commands to the appropriate handler.</span></span> <span data-ttu-id="b76eb-290">Wenn Nachrichtenwarteschlangen verwendet werden, um die Befehle zu akzeptieren, kann die Pipeline des Befehls noch komplexer werden, da Sie sie wahrscheinlich in zwei über die externe Warteschlange verbundene Prozesse aufteilen müssen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-290">Using message queues to accept the commands can further complicate your command’s pipeline, because you will probably need to split the pipeline into two processes connected through the external message queue.</span></span> <span data-ttu-id="b76eb-291">Die Verwendung ist jedoch sinnvoll, wenn Sie Skalierbarkeit und Leistung basierend auf asynchronem Messaging verbessern müssen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-291">Still, it should be used if you need to have improved scalability and performance based on asynchronous messaging.</span></span> <span data-ttu-id="b76eb-292">Beachten Sie, dass im Fall von Abbildung 7-26 der Controller nur die Befehlsnachricht in die Warteschlange sendet und zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b76eb-292">Consider that in the case of Figure 7-26, the controller just posts the command message into the queue and returns.</span></span> <span data-ttu-id="b76eb-293">Die Befehlshandler verarbeiten die Nachrichten in ihrem eigenen Tempo.</span><span class="sxs-lookup"><span data-stu-id="b76eb-293">Then the command handlers process the messages at their own pace.</span></span> <span data-ttu-id="b76eb-294">Dies ist ein großer Vorteil von Warteschlangen: Die Nachrichtenwarteschlange kann als Puffer fungieren, wenn Hyperskalierbarkeit erforderlich ist, z.B. für Lager oder jedes andere Szenario mit einem hohen eingehenden Datenaufkommen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-294">That is a great benefit of queues: the message queue can act as a buffer in cases when hyper scalability is needed, such as for stocks or any other scenario with a high volume of ingress data.</span></span>

<span data-ttu-id="b76eb-295">Da die Nachrichtenwarteschlangen asynchron sind, müssen Sie herausfinden, wie mit der Clientanwendung über den Erfolg oder Misserfolg des Prozesses des Befehls kommuniziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b76eb-295">However, because of the asynchronous nature of message queues, you need to figure out how to communicate with the client application about the success or failure of the command’s process.</span></span> <span data-ttu-id="b76eb-296">Im Allgemeinen sollten Sie nie „Fire and Forget“-Befehle verwenden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-296">As a rule, you should never use “fire and forget” commands.</span></span> <span data-ttu-id="b76eb-297">Jede Geschäftsanwendung muss wissen, ob ein Befehl erfolgreich verarbeitet oder zumindest überprüft und akzeptiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b76eb-297">Every business application needs to know if a command was processed successfully, or at least validated and accepted.</span></span>

<span data-ttu-id="b76eb-298">Die Komplexität Ihres Systems wird erhöht, da nach dem Validieren einer Befehlsnachricht, die an eine asynchrone Warteschlange übermittelt wurde, auf den Client reagiert werden kann, während ein prozessinterner Befehl das Ergebnis des Befehls nach der Ausführung der Transaktion zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b76eb-298">Thus, being able to respond to the client after validating a command message that was submitted to an asynchronous queue adds complexity to your system, as compared to an in-process command process that returns the operation’s result after running the transaction.</span></span> <span data-ttu-id="b76eb-299">Bei Verwendung von Warteschlangen, müssen Sie möglicherweise das Ergebnis des Befehlsprozesses über andere Vorgangsergebnismeldungen zurückgeben, wofür zusätzliche Komponenten und eine benutzerdefinierte Kommunikation in Ihrem System benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-299">Using queues, you might need to return the result of the command process through other operation result messages, which will require additional components and custom communication in your system.</span></span>

<span data-ttu-id="b76eb-300">Darüber hinaus sind asynchrone Befehle unidirektionale Befehle, die jedoch in vielen Fällen möglicherweise nicht benötigt werden, was in der folgenden interessanten [Online-Unterhaltung](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ) zwischen Burtsev Alexey und Greg Young erläutert wird:</span><span class="sxs-lookup"><span data-stu-id="b76eb-300">Additionally, async commands are one-way commands, which in many cases might not be needed, as is explained in the following interesting exchange between Burtsev Alexey and Greg Young in an [online conversation](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span></span>

> <span data-ttu-id="b76eb-301">\[Burtsev Alexey\] Ich finde häufig Code, in dem grundlos asynchrone Befehlsbehandlung oder unidirektionales Befehlsmessaging verwendet wird (es handelt sich nicht um einen langen Vorgang, es wird kein externer asynchroner Code ausgeführt, es handelt sich noch nicht einmal um anwendungsübergreifende Grenzen für die Verwendung des Nachrichtenbusses).</span><span class="sxs-lookup"><span data-stu-id="b76eb-301">\[Burtsev Alexey\] I find lots of code where people use async command handling or one way command messaging without any reason to do so (they are not doing some long operation, they are not executing external async code, they do not even cross application boundary to be using message bus).</span></span> <span data-ttu-id="b76eb-302">Wozu diese unnötige Komplexität?</span><span class="sxs-lookup"><span data-stu-id="b76eb-302">Why do they introduce this unnecessary complexity?</span></span> <span data-ttu-id="b76eb-303">Und ich habe bisher noch kein CQRS-Codebeispiel mit blockierendem Befehlshandler gesehen, obwohl dieser in den meisten Fällen gut geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="b76eb-303">And actually, I haven't seen a CQRS code example with blocking command handlers so far, though it will work just fine in most cases.</span></span>
>
> <span data-ttu-id="b76eb-304">\[Greg Young\] \[...\] ein asynchroner Befehl ist nicht vorhanden. Es handelt sich eigentlich um ein anderes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b76eb-304">\[Greg Young\] \[...\] an asynchronous command doesn't exist; it's actually another event.</span></span> <span data-ttu-id="b76eb-305">Wenn ich das annehmen muss, was man mir sendet, und ein Ereignis auslösen muss, wenn ich nicht zustimme, sagt man \[d.h. der Befehl\] mir nicht mehr, dass ich etwas tun muss.</span><span class="sxs-lookup"><span data-stu-id="b76eb-305">If I must accept what you send me and raise an event if I disagree, it's no longer you telling me to do something \[that is, it’s not a command\].</span></span> <span data-ttu-id="b76eb-306">Man informiert mich vielmehr darüber, dass etwas getan wurde.</span><span class="sxs-lookup"><span data-stu-id="b76eb-306">It's you telling me something has been done.</span></span> <span data-ttu-id="b76eb-307">Auf den ersten Blick scheint es sich um einen geringfügigen Unterschied zu handeln, aber er hat viele Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-307">This seems like a slight difference at first, but it has many implications.</span></span>

<span data-ttu-id="b76eb-308">Asynchrone Befehle erhöhen die Komplexität eines Systems entscheidend, da es keine einfache Möglichkeit gibt, Fehler anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-308">Asynchronous commands greatly increase the complexity of a system, because there is no simple way to indicate failures.</span></span> <span data-ttu-id="b76eb-309">Daher werden asynchrone Befehle nur dann empfohlen, wenn Skalierungsanforderungen erforderlich sind, oder aber in besonderen Fällen für die Kommunikation von internen Microservices über Messaging.</span><span class="sxs-lookup"><span data-stu-id="b76eb-309">Therefore, asynchronous commands are not recommended other than when scaling requirements are needed or in special cases when communicating the internal microservices through messaging.</span></span> <span data-ttu-id="b76eb-310">In diesen Fällen müssen Sie ein eigenes Reporting- und Wiederherstellungssystem für Fehler entwickeln.</span><span class="sxs-lookup"><span data-stu-id="b76eb-310">In those cases, you must design a separate reporting and recovery system for failures.</span></span>

<span data-ttu-id="b76eb-311">Bei der ursprünglichen Version von eShopOnContainers haben wir uns für die Verwendung der synchronen Befehlsverarbeitung entschlossen, ausgehend von HTTP-Anforderungen und gesteuert von Vermittlermustern.</span><span class="sxs-lookup"><span data-stu-id="b76eb-311">In the initial version of eShopOnContainers, we decided to use synchronous command processing, started from HTTP requests and driven by the Mediator pattern.</span></span> <span data-ttu-id="b76eb-312">Auf diese Weise kann der Erfolg oder Misserfolg des Prozesses wie in der [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs)-Implementierung zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-312">That easily allows you to return the success or failure of the process, as in the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) implementation.</span></span>

<span data-ttu-id="b76eb-313">In jedem Fall sollte diese Entscheidung auf der Grundlage der geschäftlichen Anforderung Ihrer Anwendung oder des Microservices getroffen werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-313">In any case, this should be a decision based on your application’s or microservice’s business requirements.</span></span>

## <a name="implement-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a><span data-ttu-id="b76eb-314">Implementieren der Befehlsprozesspipeline mit einem Vermittlermuster (MediatR)</span><span class="sxs-lookup"><span data-stu-id="b76eb-314">Implement the command process pipeline with a mediator pattern (MediatR)</span></span>

<span data-ttu-id="b76eb-315">Als Beispielimplementierung wird in dieser Anleitung die Verwendung der prozessinternen Pipeline basierend auf dem Vermittlermuster vorgeschlagen, um im Speicher die Befehlserfassung zu steuern und Befehle an die richtigen Befehlshandler weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="b76eb-315">As a sample implementation, this guide proposes using the in-process pipeline based on the Mediator pattern to drive command ingestion and route commands, in memory, to the right command handlers.</span></span> <span data-ttu-id="b76eb-316">In der Anleitung wird außerdem die Anwendung von [Verhaltensweisen](https://github.com/jbogard/MediatR/wiki/Behaviors) vorgeschlagen, um querschnittliche Belange abzutrennen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-316">The guide also proposes applying [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) in order to separate cross-cutting concerns.</span></span>

<span data-ttu-id="b76eb-317">Für die Implementierung in .NET Core sind mehrere Open-Source-Bibliotheken verfügbar sind, die das Vermittlermuster implementieren.</span><span class="sxs-lookup"><span data-stu-id="b76eb-317">For implementation in .NET Core, there are multiple open-source libraries available that implement the Mediator pattern.</span></span> <span data-ttu-id="b76eb-318">In dieser Anleitung wird die Open-Source-Bibliothek [MediatR](https://github.com/jbogard/MediatR) verwendet (von Jimmy Bogard erstellt), aber Sie können auch einen anderen Ansatz verwenden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-318">The library used in this guide is the [MediatR](https://github.com/jbogard/MediatR) open-source library (created by Jimmy Bogard), but you could use another approach.</span></span> <span data-ttu-id="b76eb-319">MediatR ist eine kleine und einfache-Bibliothek, die Ihnen ermöglicht, die In-Memory-Nachrichten, z.B. einen Befehl, zu verarbeiten, während Sie Decorator-Elemente oder Verhaltensweisen anwenden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-319">MediatR is a small and simple library that allows you to process in-memory messages like a command, while applying decorators or behaviors.</span></span>

<span data-ttu-id="b76eb-320">Mithilfe des Vermittlermusters können Sie die Kopplung reduzieren und mit den angeforderten Aufgaben verbundene Bedenken isolieren, während automatisch eine Verbindung mit dem Handler herstellt wurde, der die Aufgaben ausführt - in diesem Fall mit Befehlshandlern.</span><span class="sxs-lookup"><span data-stu-id="b76eb-320">Using the Mediator pattern helps you to reduce coupling and to isolate the concerns of the requested work, while automatically connecting to the handler that performs that work—in this case, to command handlers.</span></span>

<span data-ttu-id="b76eb-321">Ein weiterer guter Grund für die Verwendung des Musters wurde von Jimmy Bogard erläutert, als er die vorliegende Anleitung überprüfte:</span><span class="sxs-lookup"><span data-stu-id="b76eb-321">Another good reason to use the Mediator pattern was explained by Jimmy Bogard when reviewing this guide:</span></span>

> <span data-ttu-id="b76eb-322">An dieser Stelle sollten auch Tests erwähnt werden. Sie bieten einen interessanten und konsistenten Einblick in das Verhalten des Systems.</span><span class="sxs-lookup"><span data-stu-id="b76eb-322">I think it might be worth mentioning testing here – it provides a nice consistent window into the behavior of your system.</span></span> <span data-ttu-id="b76eb-323">Eingabe der Anforderung , Ausgabe der Antwort. Der Aspekt war für uns eine wichtige Voraussetzung für die Entwicklung von Tests mit durchgängigem Verhalten.</span><span class="sxs-lookup"><span data-stu-id="b76eb-323">Request-in, response-out. We’ve found that aspect quite valuable in building consistently behaving tests.</span></span>

<span data-ttu-id="b76eb-324">Betrachten wir zunächst einen WebAPI-Beispielcontroller, auf dem Sie normalerweise das Vermittlerobjekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-324">First, let’s look at a sample WebAPI controller where you actually would use the mediator object.</span></span> <span data-ttu-id="b76eb-325">Wenn Sie das Vermittlerobjekt nicht verwenden würden, müssten Sie alle Abhängigkeiten für diesen Controller einfügen, etwa ein Protokollierungsobjekt usw.</span><span class="sxs-lookup"><span data-stu-id="b76eb-325">If you weren't using the mediator object, you'd need to inject all the dependencies for that controller, things like a logger object and others.</span></span> <span data-ttu-id="b76eb-326">Das Ergebnis ist ein ziemlich komplizierter Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="b76eb-326">Therefore, the constructor would be quite complicated.</span></span> <span data-ttu-id="b76eb-327">Wenn Sie jedoch das Vermittlerobjekt verwenden, kann der Konstruktor des Controllers wesentlich einfacher sein, mit einigen wenigen Abhängigkeiten anstelle von vielen Abhängigkeiten, z.B. eine pro querschnittlichen Vorgang, was im folgenden Beispiel veranschaulicht wird:</span><span class="sxs-lookup"><span data-stu-id="b76eb-327">On the other hand, if you use the mediator object, the constructor of your controller can be a lot simpler, with just a few dependencies instead of many dependencies if you had one per cross-cutting operation, as in the following example:</span></span>

```csharp
public class MyMicroserviceController : Controller
{
    public MyMicroserviceController(IMediator mediator,
                                    IMyMicroserviceQueries microserviceQueries)
    {
        // ...
    }
}
```

<span data-ttu-id="b76eb-328">Wie Sie sehen, stellt der Vermittler einen übersichtlichen und schlanken Web-API-Controllerkonstruktor bereit.</span><span class="sxs-lookup"><span data-stu-id="b76eb-328">You can see that the mediator provides a clean and lean Web API controller constructor.</span></span> <span data-ttu-id="b76eb-329">Darüber hinaus nimmt der Code zum Senden eines Befehls an das Vermittlerobjekt in dem Controllermethoden fast eine Zeile ein:</span><span class="sxs-lookup"><span data-stu-id="b76eb-329">In addition, within the controller methods, the code to send a command to the mediator object is almost one line:</span></span>

```csharp
[Route("new")]
[HttpPost]
public async Task<IActionResult> ExecuteBusinessOperation([FromBody]RunOpCommand
                                                               runOperationCommand)
{
    var commandResult = await _mediator.SendAsync(runOperationCommand);

    return commandResult ? (IActionResult)Ok() : (IActionResult)BadRequest();
}
```

### <a name="implement-idempotent-commands"></a><span data-ttu-id="b76eb-330">Implementieren von idempotenten Befehlen</span><span class="sxs-lookup"><span data-stu-id="b76eb-330">Implement idempotent Commands</span></span>

<span data-ttu-id="b76eb-331">**eShopOnContainers** enthält ein komplexeres Beispiel als das oben aufgeführte. Es veranschaulicht die Übermittlung eines CreateOrderCommand-Objekts aus dem Microservice für Bestellungen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-331">In **eShopOnContainers**, a more advanced example than the above is submitting a CreateOrderCommand object from the Ordering microservice.</span></span> <span data-ttu-id="b76eb-332">Aber da der Bestellgeschäftsprozess etwas komplexer ist und im vorliegenden Fall am Warenkorbmicroservice beginnt, wird die Aktion „Übermittlung“ des CreateOrderCommand-Objekts von einem Integrationsereignishandler namens [UserCheckoutAcceptedIntegrationEventHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) und nicht von einem einfachen WebAPI-Controller ausgeführt, der wie in dem vorherigen, einfacheren Verfahren von der Client-App aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b76eb-332">But since the Ordering business process is a bit more complex and, in our case, it actually starts in the Basket microservice, this action of submitting the CreateOrderCommand object is performed from an integration-event handler named [UserCheckoutAcceptedIntegrationEventHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) instead of a simple WebAPI controller called from the client App as in the previous simpler example.</span></span>

<span data-ttu-id="b76eb-333">Die Aktion der Übermittlung des Befehls an MediatR ist, wie im folgenden Code veranschaulicht, relativ ähnlich.</span><span class="sxs-lookup"><span data-stu-id="b76eb-333">Nevertheless, the action of submitting the Command to MediatR is pretty similar, as shown in the following code.</span></span>

```csharp
var createOrderCommand = new CreateOrderCommand(eventMsg.Basket.Items,
                                                eventMsg.UserId, eventMsg.City,
                                                eventMsg.Street, eventMsg.State,
                                                eventMsg.Country, eventMsg.ZipCode,
                                                eventMsg.CardNumber,
                                                eventMsg.CardHolderName,
                                                eventMsg.CardExpiration,
                                                eventMsg.CardSecurityNumber,
                                                eventMsg.CardTypeId);

var requestCreateOrder = new IdentifiedCommand<CreateOrderCommand,bool>(createOrderCommand,
                                                                        eventMsg.RequestId);
result = await _mediator.Send(requestCreateOrder);
```

<span data-ttu-id="b76eb-334">Dieser Fall ist jedoch auch etwas anspruchsvoller, da idempotente Befehle implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-334">However, this case is also a little bit more advanced because we’re also implementing idempotent commands.</span></span> <span data-ttu-id="b76eb-335">Der CreateOrderCommand-Prozess sollte idempotent sein. Wenn eine Nachricht aus einem beliebigen Grund, z.B. bei Neuversuchen, dupliziert im Netzwerk übermittelt wird, wird der gleiche Geschäftsauftrag nur einmal verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b76eb-335">The CreateOrderCommand process should be idempotent, so if the same message comes duplicated through the network, because of any reason, like retries, the same business order will be processed just once.</span></span>

<span data-ttu-id="b76eb-336">Dies wird durch Umschließen des Geschäftsbefehls (hier CreateOrderCommand) und Einbettung in einen generischen IdentifiedCommand implementiert, der von einer ID jeder Nachricht über das Netzwerk verfolgt wird, das idempotent sein muss.</span><span class="sxs-lookup"><span data-stu-id="b76eb-336">This is implemented by wrapping the business command (in this case CreateOrderCommand) and embedding it into a generic IdentifiedCommand which is tracked by an ID of every message coming through the network that has to be idempotent.</span></span>

<span data-ttu-id="b76eb-337">Im folgenden Code können Sie sehen, dass der IdentifiedCommand nichts weiter als eine DTO mit ID sowie das umschlossene Geschäftsbefehlsobjekt ist.</span><span class="sxs-lookup"><span data-stu-id="b76eb-337">In the code below, you can see that the IdentifiedCommand is nothing more than a DTO with and ID plus the wrapped business command object.</span></span>

```csharp
public class IdentifiedCommand<T, R> : IRequest<R>
    where T : IRequest<R>
{
    public T Command { get; }
    public Guid Id { get; }
    public IdentifiedCommand(T command, Guid id)
    {
        Command = command;
        Id = id;
    }
}
```

<span data-ttu-id="b76eb-338">Anschließend prüft der CommandHandler für den IdentifiedCommand namens [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs) grundsätzlich, ob die als Teil der Nachricht ankommende ID bereits in einer Tabelle vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b76eb-338">Then the CommandHandler for the IdentifiedCommand named [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs) will basically check if the ID coming as part of the message already exists in a table.</span></span> <span data-ttu-id="b76eb-339">Wenn sie bereits vorhanden ist, wird der Befehl nicht erneut verarbeitet und verhält sich wie ein idempotenter Befehl.</span><span class="sxs-lookup"><span data-stu-id="b76eb-339">If it already exists, that command won’t be processed again, so it behaves as an idempotent command.</span></span> <span data-ttu-id="b76eb-340">Der Infrastrukturcode wird durch den unten stehenden Methodenaufruf `_requestManager.ExistAsync` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b76eb-340">That infrastructure code is performed by the `_requestManager.ExistAsync` method call below.</span></span>

```csharp
// IdentifiedCommandHandler.cs
public class IdentifiedCommandHandler<T, R> :
                                   IAsyncRequestHandler<IdentifiedCommand<T, R>, R>
                                   where T : IRequest<R>
{
    private readonly IMediator _mediator;
    private readonly IRequestManager _requestManager;

    public IdentifiedCommandHandler(IMediator mediator,
                                    IRequestManager requestManager)
    {
        _mediator = mediator;
        _requestManager = requestManager;
    }

    protected virtual R CreateResultForDuplicateRequest()
    {
        return default(R);
    }

    public async Task<R> Handle(IdentifiedCommand<T, R> message)
    {
        var alreadyExists = await _requestManager.ExistAsync(message.Id);
        if (alreadyExists)
        {
            return CreateResultForDuplicateRequest();
        }
        else
        {
            await _requestManager.CreateRequestForCommandAsync<T>(message.Id);

            // Send the embedded business command to mediator
            // so it runs its related CommandHandler
            var result = await _mediator.Send(message.Command);

            return result;
        }
    }
}
```

<span data-ttu-id="b76eb-341">Der IdentifiedCommand verhält sich wie der Umschlag eines Geschäftsbefehls. Wenn der Geschäftsbefehl verarbeitet werden muss, da er keine wiederholte ID ist, wird der innere Geschäftsbefehl erneut an den Vermittler übermittelt – wie im letzten Teil des oben stehenden Codes bei Ausführung von `_mediator.Send(message.Command)` über [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs).</span><span class="sxs-lookup"><span data-stu-id="b76eb-341">Since the IdentifiedCommand acts like a business command’s envelope, when the business command needs to be processed because it is not a repeated Id, then it takes that inner business command and re-submits it to Mediator, as in the last part of the code shown above when running `_mediator.Send(message.Command)`, from the [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs).</span></span>

<span data-ttu-id="b76eb-342">Dabei wird der Geschäftsbefehlshandler verlinkt und ausgeführt. In diesem Fall handelt es sich um den [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs), der – wie im folgenden Code gezeigt – Transaktionen für die Bestellungsdatenbank ausführt.</span><span class="sxs-lookup"><span data-stu-id="b76eb-342">When doing that, it will link and run the business command handler, in this case, the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) which is running transactions against the Ordering database, as shown in the following code.</span></span>

```csharp
// CreateOrderCommandHandler.cs
public class CreateOrderCommandHandler
                                   : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
                                     IOrderRepository orderRepository,
                                     IIdentityService identityService)
    {
        _orderRepository = orderRepository ??
                          throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ??
                          throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ??
                                 throw new ArgumentNullException(nameof(mediator));
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        // Add/Update the Buyer AggregateRoot
        var address = new Address(message.Street, message.City, message.State,
                                  message.Country, message.ZipCode);
        var order = new Order(message.UserId, address, message.CardTypeId,
                              message.CardNumber, message.CardSecurityNumber,
                              message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                               item.Discount, item.PictureUrl, item.Units);
        }

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
    }
}
```

### <a name="register-the-types-used-by-mediatr"></a><span data-ttu-id="b76eb-343">Registrieren der von MediatR verwendeten Typen</span><span class="sxs-lookup"><span data-stu-id="b76eb-343">Register the types used by MediatR</span></span>

<span data-ttu-id="b76eb-344">Damit MediatR Ihre Befehlshandlerklassen erkennt, müssen Sie die Vermittlerklassen und die Befehlshandlerklassen in Ihrem IoC-Container registrieren.</span><span class="sxs-lookup"><span data-stu-id="b76eb-344">In order for MediatR to be aware of your command handler classes, you need to register the mediator classes and the command handler classes in your IoC container.</span></span> <span data-ttu-id="b76eb-345">MediatR verwendet standardmäßig Autofac als IoC-Container, aber Sie können auch den integrierten ASP.NET Core-IoC-Container oder einen anderen von MediatR unterstützten Container verwenden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-345">By default, MediatR uses Autofac as the IoC container, but you can also use the built-in ASP.NET Core IoC container or any other container supported by MediatR.</span></span>

<span data-ttu-id="b76eb-346">Der folgende Code zeigt, wie die Typen und Befehle des Vermittlers registriert werden, wenn Autofac-Module verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-346">The following code shows how to register Mediator’s types and commands when using Autofac modules.</span></span>

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();

        // Register all the Command classes (they implement IAsyncRequestHandler)
        // in assembly holding the Commands
        builder.RegisterAssemblyTypes(
                              typeof(CreateOrderCommand).GetTypeInfo().Assembly).
                                   AsClosedTypesOf(typeof(IAsyncRequestHandler<,>));
        // Other types registration
        //...
    }
}
```

<span data-ttu-id="b76eb-347">Dies ist sozusagen der Zauberstab von MediatR.</span><span class="sxs-lookup"><span data-stu-id="b76eb-347">This is where “the magic happens” with MediatR.</span></span>

<span data-ttu-id="b76eb-348">Jeder Befehlshandler implementiert die generische `IAsyncRequestHandler<T>`-Schnittstelle. Beim Registrieren der Assemblys registriert der Code mit `RegisteredAssemblyTypes` alle als `IAsyncRequestHandler` markierten Typen, während die `CommandHandlers` dank der in der `CommandHandler`-Klasse angegebenen Beziehung ihren `Commands` zugeordnet werden:</span><span class="sxs-lookup"><span data-stu-id="b76eb-348">Because each command handler implements the generic `IAsyncRequestHandler<T>` interface, when registering the assemblies, the code registers with `RegisteredAssemblyTypes` all the types marked as `IAsyncRequestHandler` while relating the `CommandHandlers` with their `Commands`, thanks to the relationship stated at the `CommandHandler` class, as in the following example:</span></span>

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

<span data-ttu-id="b76eb-349">Das ist der Code, der Befehle mit Befehlshandlern korreliert.</span><span class="sxs-lookup"><span data-stu-id="b76eb-349">That is the code that correlates commands with command handlers.</span></span> <span data-ttu-id="b76eb-350">Der Handler ist nur eine einfache Klasse, aber er erbt vom `RequestHandler<T>` (<T> steht für den Befehlstyp), und MediatR stellt sicher, dass er mit der richtigen Nutzlast aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b76eb-350">The handler is just a simple class, but it inherits from `RequestHandler<T>`, where T is the command type, and MediatR makes sure it is invoked with the correct payload (the command).</span></span>

## <a name="apply-cross-cutting-concerns-when-processing-commands-with-the-behaviors-in-mediatr"></a><span data-ttu-id="b76eb-351">Anwenden von übergreifenden Belangen beim Verarbeiten von Befehlen mit Verhalten in MediatR</span><span class="sxs-lookup"><span data-stu-id="b76eb-351">Apply cross-cutting concerns when processing commands with the Behaviors in MediatR</span></span>

<span data-ttu-id="b76eb-352">Es gibt zudem die Möglichkeit, querschnittliche Belange auf die Vermittlerpipeline anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b76eb-352">There is one more thing: being able to apply cross-cutting concerns to the mediator pipeline.</span></span> <span data-ttu-id="b76eb-353">Sie können auch am Ende des Autofac-Registrierungsmodulcodes sehen, wie ein Verhaltenstyp registriert wird, insbesondere eine benutzerdefinierte LoggingBehavior-Klasse und eine ValidatorBehavior-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b76eb-353">You can also see at the end of the Autofac registration module code how it registers a behavior type, specifically, a custom LoggingBehavior class and a ValidatorBehavior class.</span></span> <span data-ttu-id="b76eb-354">Sie können jedoch auch anderes benutzerdefiniertes Verhalten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-354">But you could add other custom behaviors, too.</span></span>

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();

        // Register all the Command classes (they implement IAsyncRequestHandler)
        // in assembly holding the Commands
        builder.RegisterAssemblyTypes(
                              typeof(CreateOrderCommand).GetTypeInfo().Assembly).
                                   AsClosedTypesOf(typeof(IAsyncRequestHandler<,>));
        // Other types registration
        //...
        builder.RegisterGeneric(typeof(LoggingBehavior<,>)).
                                                   As(typeof(IPipelineBehavior<,>));
        builder.RegisterGeneric(typeof(ValidatorBehavior<,>)).
                                                   As(typeof(IPipelineBehavior<,>));
    }
}
```

<span data-ttu-id="b76eb-355">Die [LoggingBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs)-Klasse kann wie der folgende Code implementiert werden, der Informationen über den Befehlshandler, der ausgeführt wird, und über den Erfolg oder Misserfolg der Ausführung protokolliert.</span><span class="sxs-lookup"><span data-stu-id="b76eb-355">That [LoggingBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) class can be implemented as the following code, which logs information about the command handler being executed and whether it was successful or not.</span></span>

```csharp
public class LoggingBehavior<TRequest, TResponse>
         : IPipelineBehavior<TRequest, TResponse>
{
    private readonly ILogger<LoggingBehavior<TRequest, TResponse>> _logger;
    public LoggingBehavior(ILogger<LoggingBehavior<TRequest, TResponse>> logger) =>
                                                                  _logger = logger;

    public async Task<TResponse> Handle(TRequest request,
                                        RequestHandlerDelegate<TResponse> next)
    {
        _logger.LogInformation($"Handling {typeof(TRequest).Name}");
        var response = await next();
        _logger.LogInformation($"Handled {typeof(TResponse).Name}");
        return response;
    }
}
```

<span data-ttu-id="b76eb-356">Durch die Implementierung dieser Verhaltensklasse und ihre Registrierung in der Pipeline (im obigen Vermittlermodul) protokollieren alle über MediatR verarbeiteten Befehle Informationen zur Ausführung.</span><span class="sxs-lookup"><span data-stu-id="b76eb-356">Just by implementing this behavior class and by registering it in the pipeline (in the MediatorModule above), all the commands processed through MediatR will be logging information about the execution.</span></span>

<span data-ttu-id="b76eb-357">Der Microservice für Bestellung von eShopOnContainers wendet auch ein zweites Verhalten für grundlegende Validierungen an, und zwar die [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs)-Klasse, die auf der Bibliothek [FluentValidation](https://github.com/JeremySkinner/FluentValidation) basiert, wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="b76eb-357">The eShopOnContainers ordering microservice also applies a second behavior for basic validations, the [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs) class that relies on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, as shown in the following code:</span></span>

```csharp
public class ValidatorBehavior<TRequest, TResponse>
         : IPipelineBehavior<TRequest, TResponse>
{
    private readonly IValidator<TRequest>[] _validators;
    public ValidatorBehavior(IValidator<TRequest>[] validators) =>
                                                         _validators = validators;

    public async Task<TResponse> Handle(TRequest request,
                                        RequestHandlerDelegate<TResponse> next)
    {
        var failures = _validators
            .Select(v => v.Validate(request))
            .SelectMany(result => result.Errors)
            .Where(error => error != null)
            .ToList();

        if (failures.Any())
        {
            throw new OrderingDomainException(
                $"Command Validation Errors for type {typeof(TRequest).Name}",
                        new ValidationException("Validation exception", failures));
        }

        var response = await next();
        return response;
    }
}
```

<span data-ttu-id="b76eb-358">Das Verhalten hier löst eine Ausnahme aus, wenn die Prüfung fehlschlägt. Allerdings können Sie auch ein Ergebnisobjekt zurückgeben, das das Befehlsergebnis enthält, wenn es erfolgreich war, oder die Prüfungsnachrichten, wenn es nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b76eb-358">The behavior here is raising an exception if validation fails, but you could also return a result object, containing the command result if it succeeded or the validation messages in case it didn’t.</span></span> <span data-ttu-id="b76eb-359">Dies würde es wahrscheinlich einfacher machen, dem Benutzer die Prüfungsergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-359">This would probably make it easier to display validation results to the user.</span></span>

<span data-ttu-id="b76eb-360">Anschließend wurde auf der Grundlage der [FluentValidation](https://github.com/JeremySkinner/FluentValidation)-Bibliothek eine Validierung für die mit CreateOrderCommand übergebenen Daten erstellt, was im folgenden Code veranschaulicht wird:</span><span class="sxs-lookup"><span data-stu-id="b76eb-360">Then, based on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, we created validation for the data passed with CreateOrderCommand, as in the following code:</span></span>

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
        RuleFor(command => command.CardExpiration).NotEmpty().Must(BeValidExpirationDate).WithMessage("Please specify a valid card expiration date");
        RuleFor(command => command.CardSecurityNumber).NotEmpty().Length(3);
        RuleFor(command => command.CardTypeId).NotEmpty();
        RuleFor(command => command.OrderItems).Must(ContainOrderItems).WithMessage("No order items found");
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

<span data-ttu-id="b76eb-361">Sie können zusätzliche Überprüfungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="b76eb-361">You could create additional validations.</span></span> <span data-ttu-id="b76eb-362">Mit dieser Methode können Sie Befehlsüberprüfungen strukturiert und elegant implementieren.</span><span class="sxs-lookup"><span data-stu-id="b76eb-362">This is a very clean and elegant way to implement your command validations.</span></span>

<span data-ttu-id="b76eb-363">Auf ähnliche Weise könnten Sie andere Verhaltensweisen für zusätzliche Aspekte oder querschnittliche Belange implementieren, die Sie bei der Behandlung auf Befehle anwenden können.</span><span class="sxs-lookup"><span data-stu-id="b76eb-363">In a similar way, you could implement other behaviors for additional aspects or cross-cutting concerns that you want to apply to commands when handling them.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="b76eb-364">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b76eb-364">Additional resources</span></span>

##### <a name="the-mediator-pattern"></a><span data-ttu-id="b76eb-365">Das Vermittlermuster</span><span class="sxs-lookup"><span data-stu-id="b76eb-365">The mediator pattern</span></span>

- <span data-ttu-id="b76eb-366">**Vermittlermuster** </span><span class="sxs-lookup"><span data-stu-id="b76eb-366">**Mediator pattern** </span></span>\
  [https://en.wikipedia.org/wiki/Mediator\_pattern](https://en.wikipedia.org/wiki/Mediator_pattern)

##### <a name="the-decorator-pattern"></a><span data-ttu-id="b76eb-367">Das Decorator-Muster</span><span class="sxs-lookup"><span data-stu-id="b76eb-367">The decorator pattern</span></span>

- <span data-ttu-id="b76eb-368">**Decoratormuster** </span><span class="sxs-lookup"><span data-stu-id="b76eb-368">**Decorator pattern** </span></span>\
  [https://en.wikipedia.org/wiki/Decorator\_pattern](https://en.wikipedia.org/wiki/Decorator_pattern)

##### <a name="mediatr-jimmy-bogard"></a><span data-ttu-id="b76eb-369">MediatR (Jimmy Bogard)</span><span class="sxs-lookup"><span data-stu-id="b76eb-369">MediatR (Jimmy Bogard)</span></span>

- <span data-ttu-id="b76eb-370">**MediatR.**</span><span class="sxs-lookup"><span data-stu-id="b76eb-370">**MediatR.**</span></span> <span data-ttu-id="b76eb-371">GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="b76eb-371">GitHub repo.</span></span> \
  <https://github.com/jbogard/MediatR>

- <span data-ttu-id="b76eb-372">**CQRS with MediatR and AutoMapper (CQRS mit MediatR und AutoMapper)**  </span><span class="sxs-lookup"><span data-stu-id="b76eb-372">**CQRS with MediatR and AutoMapper** </span></span>\
  <https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/>

- <span data-ttu-id="b76eb-373">**Put your controllers on a diet: POSTs and commands. (Effiziente Controller: POSTs und Befehle)**</span><span class="sxs-lookup"><span data-stu-id="b76eb-373">**Put your controllers on a diet: POSTs and commands.**</span></span> \
  <https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/>

- <span data-ttu-id="b76eb-374">**Tackling cross-cutting concerns with a mediator pipeline (Umgang mit übergreifenden Belangen mithilfe einer Vermittlerpipeline)**  </span><span class="sxs-lookup"><span data-stu-id="b76eb-374">**Tackling cross-cutting concerns with a mediator pipeline** </span></span>\
  <https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/>

- <span data-ttu-id="b76eb-375">**CQRS and REST: the perfect match (CQRS und REST: das ideale Paar)**  </span><span class="sxs-lookup"><span data-stu-id="b76eb-375">**CQRS and REST: the perfect match** </span></span>\
  <https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/>

- <span data-ttu-id="b76eb-376">**MediatR Pipeline Examples (Beispiele für MediatR-Pipelines)**  </span><span class="sxs-lookup"><span data-stu-id="b76eb-376">**MediatR Pipeline Examples** </span></span>\
  <https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/>

- <span data-ttu-id="b76eb-377">**Vertical Slice Test Fixtures for MediatR and ASP.NET Core (Vertikale Segmenttestfixtures für MediatR und ASP.NET Core)**  </span><span class="sxs-lookup"><span data-stu-id="b76eb-377">**Vertical Slice Test Fixtures for MediatR and ASP.NET Core** </span></span>\
  <https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>

- <span data-ttu-id="b76eb-378">**MediatR Extensions for Microsoft Dependency Injection Released (Release: MediatR-Erweiterungen für die Microsoft-Abhängigkeitsinjektion)**  </span><span class="sxs-lookup"><span data-stu-id="b76eb-378">**MediatR Extensions for Microsoft Dependency Injection Released** </span></span>\
  <https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/>

##### <a name="fluent-validation"></a><span data-ttu-id="b76eb-379">Fluent-Überprüfung</span><span class="sxs-lookup"><span data-stu-id="b76eb-379">Fluent validation</span></span>

- <span data-ttu-id="b76eb-380">**Jeremy Skinner. FluentValidation.**</span><span class="sxs-lookup"><span data-stu-id="b76eb-380">**Jeremy Skinner. FluentValidation.**</span></span> <span data-ttu-id="b76eb-381">GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="b76eb-381">GitHub repo.</span></span> \
  <https://github.com/JeremySkinner/FluentValidation>

> [!div class="step-by-step"]
> <span data-ttu-id="b76eb-382">[Zurück](microservice-application-layer-web-api-design.md)
> [Weiter](../implement-resilient-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="b76eb-382">[Previous](microservice-application-layer-web-api-design.md)
[Next](../implement-resilient-applications/index.md)</span></span>
